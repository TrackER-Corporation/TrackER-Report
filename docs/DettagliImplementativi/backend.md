---
title: Dettagli implementativi Backend
parent: Dettagli implementativi
has_children: false
nav_order: 2
---

# Dettagli implementativi sistema di backend

Durante lo sviluppo del sistema backend si è cercato di utilizzare il più possibile un approccio basato sui micro-servizi e di raffinare sempre di più la soluzione adottata, per poter sfruttare al meglio i vantaggi che questo approccio offre.

Il presente documento descrive in dettaglio l'implementazione del sistema di backend per un'applicazione React basata su microservizi. Il sistema è stato sviluppato utilizzando il framework Express e il modulo http-proxy-middleware per creare un'architettura a microservizi che consente la comunicazione tra il frontend React e i servizi backend tramite un gateway.

Di seguito sono riportati i dettagli implementativi del sistema di backend.

## Gateway

Il servizio Gateway è un componente essenziale all'interno di un'architettura a microservizi.
Svolge il ruolo di intermediario tra l'applicazione client e i diversi servizi backend. 
Il servizio Gateway viene implementato utilizzando `Express.js`, framework per Node.js che semplifica lo sviluppo di applicazioni web e semplifica la definizione di`route`, e sfruttando il concetto di proxy per inoltrare le richieste ai servizi appropriati.
Per la sua realizzazione, sono state utilizzate le seguenti librerie:

- ``dotenv`` vengono gestite le variabili d'ambiente.
- ``cors`` vengono abilitate le richieste ``cross-origin``;
- ``http-proxy-middleware`` si genera il middleware di proxy.

Le `route` dei servizi backend vengono definite all'interno di una mappa, associando ciascuna rotta all'URL del corrispondente servizio. 

Dopo aver letto la porta del server dalla variabile d'ambiente `PORT`, viene creato un'app Express e vengono applicati i middleware cors e express.json(). 
Il middleware cors consente le richieste cross-origin, mentre express.json() permette di analizzare il corpo delle richieste JSON in arrivo.

Per ogni `route` definita nella mappa, viene creato un middleware di proxy utilizzando `createProxyMiddleware`. Questo middleware inoltra le richieste alla URL del servizio backend corrispondente, specificata come target del proxy.
Viene inoltre gestita la manipolazione del percorso delle richieste mediante la funzione ``pathRewrite``.
Se la richiesta è di tipo POST o PUT e contiene un corpo, viene serializzato in JSON e inviato al servizio backend tramite il middleware di proxy.

Di seguito il codice prodotto per il servizio gateway

``` ts
import express from 'express';
import dotenv from 'dotenv';
import cors from 'cors';
import { createProxyMiddleware } from 'http-proxy-middleware';

dotenv.config();

const routes = new Map<string, any>()
routes.set("users", process.env.USER_SERVICE)
routes.set("buildings", process.env.BUILDINGS_SERVICE)
routes.set("bills", process.env.BILLS_SERVICE)
routes.set("renewable", process.env.RENEWABLE_SERVICE)
routes.set("organization", process.env.ORGANIZATION_SERVICE)
routes.set("activity", process.env.ACTIVITY_SERVICE)
routes.set("preference", process.env.PREFERENCE_SERVICE)

const port = process.env.PORT;

const app = express();
app.use(cors());
app.use(express.json());

routes.forEach((service_port: any, route: string) => {
  console.log(`/api/${route}`, `http://localhost:${service_port}`)
  app.use(
    `/api/${route}`,
    createProxyMiddleware({
      target: `http://localhost:${service_port}`,
      changeOrigin: true,
      secure: false,
      pathRewrite: function (path, req) { return path.replace(`/api/${route}`, '') },
      onProxyReq: (proxyReq, req, res) => {
        if ((req.method == "POST" || req.method == "PUT") && req.body) {
          let body = req.body;
          let newBody = '';
          delete req.body;

          try {
            newBody = JSON.stringify(body);
            proxyReq.setHeader('content-length', Buffer.byteLength(newBody, 'utf8'));
            proxyReq.write(newBody);
            proxyReq.end();
          } catch (e) {
            console.log('Stringify err', e)
          }
        }
      },
    })
  );
})

app.listen(port, () => console.info(`tracker-gateway is running`));

export default app
```

## Microservices

Per lo sviluppo dei microservizi, si sono utilizzate le stesse tecnologie del servizio Gateway.

In linea generale il funzionamento e il codice dei servizi è lo stesso: 
- Si definiscono le route del servizio tramite `express`;
- Vengono applicati i middleware cors() e express.json() per gestire il supporto CORS e il parsing dei dati JSON nelle richieste;
- Il servizio si connette al Database di interesse indicato sulla variabile d'ambiente `DB_CONN_STRING`;
- Il servizio si mette in ascolto sulla porta definita nella variabile d'ambiente `PORT`.

Di seguito viene illustrato il collegamento al database di un servizio 

``` ts
import * as mongoDB from "mongodb";
import * as dotenv from "dotenv";

export const collections: { collectionName?: mongoDB.Collection } = {}

export async function connectToDatabase() {
  dotenv.config();

  try {
    const client: mongoDB.MongoClient = new mongoDB.MongoClient(process.env.DB_CONN_STRING!);

    await client.connect();

    const db: mongoDB.Db = client.db(process.env.DB_NAME);

    const collectionName: mongoDB.Collection = db.collection(process.env.COLLECTION!);

    collections.activity = collectionName;

    console.log(`Successfully connected to database: ${db.databaseName} and collection: ${collectionName.collectionName}`);
  } catch (error) {
    console.error(error);
  }
}
```

Codice principale di un servizio

``` ts
import express from 'express';
import dotenv from 'dotenv';
import cors from 'cors';
import { connectToDatabase } from './db/services/database.service';
import router from './db/route/route';

dotenv.config();

const port = process.env.PORT;

const app = express();
app.use(cors());
app.use(express.json());

app.use(router)

connectToDatabase()
app.listen(port, () => console.info(`tracker-name-service is running`));

export default { app }
```