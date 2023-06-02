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

## Docker e docker Compose

Al fine di rendere il deployment del sistema di backend più semplice, si è deciso di utilizzare **[Docker](https://www.docker.com/)** per poter caricare ed eseguire i diversi micro-servizi. 

In particolare, si è deciso di inserire ogni micro-servizio all'interno di un apposito container Docker. Un container è una _lightweight Virtual Machine_, che è in grado di contenere un'applicazione e il suo ambiente di esecuzione, vengono considerati _lightweight_, in quanto contengono solo lo stretto necessario per poter eseguire l'applicazione e utilizzano le risorse dell'host sul quale vengono istanziati, consentendoci di avere un ambiente di esecuzione isolato per ogni servizio. 

 ```dockerfile
# Use an official Node runtime as a parent image
FROM node:18.5.0-alpine

# Set the working directory to /app
WORKDIR /app

# Copy the package.json and package-lock.json files to the container
COPY package*.json ./

# Install dependencies
RUN npm install --legacy-peer-deps

# Copy the rest of the application files to the container
COPY . .

# Expose port 5173 for the application to run on
EXPOSE 5173

# Start the application
CMD ["npm", "run", "dev"]
 ```

I diversi container sono in grado di comunicare tra loro tramite una rete costruita ad-hoc; per semplicità di gestione la costruzione dei container e della rete è stata realizzata tramite la scrittura di un apposito file ``actions.yaml``. All'interno di ogni file ogni servizio viene identificato dallo stesso nome usato per la creazione della propria immagine.

```yaml
docker:
    name: Docker
    runs-on: ubuntu-latest
    needs: sonarcloud
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: Set up QEMU
        uses: docker/setup-qemu-action@v2
      - name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v2
      - name: Login to Docker Hub
        uses: docker/login-action@v2
        with:
          username: ${{ secrets.DOCKERHUB_USERNAME }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}
      - name: Build and push
        uses: docker/build-push-action@v4
        with:
          context: .
          push: true
          tags: leledallas/tracker-ui:latest
```

