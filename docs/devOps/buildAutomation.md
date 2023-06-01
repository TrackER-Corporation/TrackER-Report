---
title: Build automation
parent: Pratiche devOps
has_children: false
nav_order: 1
---
# Build automation

Una volta definiti i bounded context e l'architettura del progetto, si è proseguito andando a definirene la struttura e l'organizzazione. È stata predisposta un'organizzazione di base su GitHub ed è stata chiamata **TrackER**. All'interno di questa sono stati predisposti nove repository principali:
- **Activity**: registra le diverse attività d'accesso;
- **Bills**: registra i valori di consumo;
- **Buildings**: gestisce gli edifici registrati;
- **Gateway**: gestisce le richieste degli endpoints;
- **Organization**: gestisce le diverse organizzazioni;
- **Preferences**: salva le preferenze degli utenti;
- **Renewable**: gestisce i dispositivi rinnovabili;
- **Users**: salva i dati degli utenti.

Tutti i repository sono stati strutturati utilizzando il build tool **npm**, permettendo di gestire in modo semplice ed efficace la _build automation_ e quindi le dipendenze ed i _plugin_ di ogni componente.

## Script personalizzati
Per ogni progetto e sottoprogetto sono stati creati degli script personalizzati. Per eseguire uno script basterà eseguire il seguente comando ``npm run nomeScript`` dentro la cartella principale, sostituendo **nomeComando** con il nome dello script presente nel progetto.

In particolare per ogni progetto sono stati creati i seguenti script:

- ``dev``: avvia il servizio.

- ``test``: esegue tutti i test automatici.

- ``test:ui``: esegue i test tramite un'interfaccia grafica interattiva.

- ``coverage``: esegue tutti i test e calcola la copertura dei test rispetto al codice..
