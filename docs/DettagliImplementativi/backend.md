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


Il servizio Gateway è composto da un server Express che funge da gateway per inoltrare le richieste a diversi servizi backend. Attraverso la libreria ``dotenv`` vengono gestite le variabili d'ambiente. Tramite ``cors`` vengono abilitate le richieste ``cross-origin`` e con ``http-proxy-middleware`` si genera il middleware di proxy.

Le `route` dei servizi backend vengono definite all'interno di una mappa, associando ciascuna rotta all'URL del corrispondente servizio. Il numero di porta del server viene letto dalla variabile d'ambiente ``PORT`` mentre quello relativo agli altri servizi in ``NAME_SERVICE``.

Viene creato un'app Express, a cui vengono applicati i middleware cors per consentire le richieste cross-origin e express.json() per analizzare il corpo delle richieste JSON.

Per ogni `route` definita nella mappa, viene creato un middleware di proxy utilizzando createProxyMiddleware. Questo middleware inoltra le richieste alla URL del servizio backend corrispondente, specificata come target del proxy. Viene inoltre gestita la manipolazione del percorso delle richieste mediante la funzione ``pathRewrite``.
Se la richiesta è di tipo POST o PUT e contiene un corpo, viene serializzato in JSON e inviato al servizio backend tramite il middleware di proxy.

Infine, il server Express viene avviato sulla porta specificata e viene visualizzato un messaggio di conferma.

## Microservices

