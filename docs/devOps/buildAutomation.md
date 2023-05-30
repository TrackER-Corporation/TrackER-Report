---
title: Build automation
parent: Pratiche devOps
has_children: false
nav_order: 1
---
# Build automation

Una volta definiti i bounded context e l'architettura del progetto, si è proseguito andando a definirene la struttura e l'organizzazione. È stata predisposta un'organizzazione di base su GitHub ed è stata chiamata **TrackER**. All'interno di questa sono stati predisposti nove repository principali:
- **Activity**, che si occupa di registrare le diverse attività d'accesso;
- **Bills**, che si occupa di registrare i valori di consumo;
- **Buildings**, che si occupa di gestire gli edifici registrati;
- **Gateway**, che si occupa di smistare le connessioni;
- **Organization**, che si occupa di gestire le diverse organizzazioni;
- **Preferences**, che si occupa di salvare le preferenze degli utenti;
- **Renewable**, che si occupa di gestire i dispositivi rinnovabili;
- **Users**, che si occupa di salvare le registrazioni degli utenti.

Tutti i repository sono stati strutturati utilizzando il build tool **npm**, permettendo di gestire in modo semplice ed efficace la _build automation_ e quindi le dipendenze ed i _plugin_ di ogni componente.

## Task personalizzati
Per ogni progetto e sottoprogetto sono stati creati dei task personalizzati. Per eseguire i task basterà eseguire il seguente comando ``npm run nomeComando`` dentro la cartella principale, sostituendo **nomeComando** con il nome del task presente nel progetto.

In particolare per ogni progetto sono stati creati:

- un task ``dev`` che permette di lanciare il servizio.

- un task ``test``, che permette di far partire tutti i test automatici.

- un task ``coverage``, che permette di far partire tutti i test e di calcolare la copertura dei test rispetto al codice. Questo comando ha anche l'opzione _:UI_ che permette di visualizzare la coverage da browser.
