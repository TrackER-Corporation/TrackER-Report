---
title: Deployment
parent: Dettagli implementativi
has_children: false
nav_order: 5
---
# Deployment
In questa sezione verrà discusso il processo di Deployment delle varie componenti del sistema.

## Docker 

Al fine di rendere il deployment di tutte le parti del sistema il più semplice ed efficente possibile, si è utilizzato **[Docker](https://www.docker.com/)**.
In particolare, si è deciso di separare la componente client da quella server mediante un apposito `container` Docker. 

Un `container` è una _lightweight Virtual Machine_, che è in grado di contenere un'applicazione e il suo ambiente di esecuzione, vengono considerati _lightweight_, in quanto contengono solo lo stretto necessario per poter eseguire l'applicazione e utilizzano le risorse dell'host sul quale vengono istanziati, consentendoci di avere un ambiente di esecuzione isolato per ogni componente del sistema. 

I diversi container sono in grado di comunicare tra loro tramite una rete costruita ad-hoc. Per semplicità la costruzione dei container e della rete è stata realizzata tramite la scrittura di un apposito file `actions.yaml` invocato automaticamente durante la fase di `release`. 

```yaml
docker:
      name: Docker
      runs-on: ubuntu-latest
      needs: sonarcloud
      steps:
      -
        name: Checkout
        uses: actions/checkout@v3
      -
        name: Set up QEMU
        uses: docker/setup-qemu-action@v2
      -
        name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v2
      -
        name: Login to Docker Hub
        uses: docker/login-action@v2
        with:
          username: ${{ secrets.DOCKERHUB_USERNAME }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}
      -
        name: Build and push
        uses: docker/build-push-action@v4
        with:
          context: .
          push: true
          tags: leledallas/tracker-server:nomeServizio
```

Container consultabili:
- **[tracker-ui](https://hub.docker.com/repository/docker/leledallas/tracker-ui/general)**
- **[tracker-server](https://hub.docker.com/repository/docker/leledallas/tracker-server/general)**

Per il deployment in locale si può utilizzare il file `Dockerfile` presente in ciascun servizio definito come segue: 

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

Per 'dockerizzare' un componente dell'applicazione bisognerà eseguire il seguente comando: `docker build -t nome-servizio`
