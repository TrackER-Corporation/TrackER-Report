---
title: Strumenti utilizzati
parent: Processo di sviluppo
has_children: false
nav_order: 1
---

## Strumenti utilizzati

Per la realizzazione del progetto sono stati utilizzati differenti tool a supporto del processo di sviluppo. Tali strumenti, hanno come obiettivo quello di agevolare gli sviluppatori durante tutta la realizzazione del progetto, cercando di automatizzarne i diversi aspetti.


### GitHub 

[GitHub](https://github.com/) è un servizio di hosting per lo sviluppo del software e gestione del _version-control_ basato su Git. Fornisce: il _distributed version control_ di Git più l'_access control_, il tracciamento dei bug, le richieste di funzionalità software, la gestione delle attività, l'integrazione continua e wiki per ogni progetto.

Per il nostro progetto abbiamo utilizzato: GitHub come servizio di hosting per il codice sorgente, le GitHub actions per promuovere il processo di _continuous integration_ e le GitHub Pages per la documentazione e spiegazione del sistema realizzato.


### Vite

[Vite](https://vitejs.dev/guide/) Il framework Vite si basa su diversi principi fondamentali per garantire prestazioni elevate e un'esperienza di sviluppo fluida. In particolare, utilizza i moduli ES nativi e le moderne API del browser per compilare il codice "on the fly" e garantire tempi di build rapidi e aggiornamenti istantanei nel browser. Inoltre, il server di sviluppo integrato in Vite è ottimizzato per il reloading rapido e la sostituzione dei moduli senza fermare l'esecuzione, consentendo agli sviluppatori di vedere in tempo reale le modifiche apportate al codice senza dover aggiornare l'intera pagina.

Vite implementa anche il caricamento "lazy" dei moduli, consentendo di migliorare le prestazioni dell'applicazione, soprattutto per quelle di grandi dimensioni, e di garantire un caricamento iniziale più rapido per gli utenti. Inoltre, utilizza tecniche come il "tree-shaking" e il "code splitting" per rimuovere il codice inutilizzato dall'applicazione e dividere il codice in sezioni più piccole, migliorando ulteriormente le prestazioni.


### Vitest

Per il progetto si è deciso di utilizzare il framework [Vitest](https://vitest.dev/) per la realizzazione di test automatizzati sul codice che ha permesso di implementare tutti i vari test necessari per garantire la qualità del codice e analizzare la coverage del progetto, con la possibilità di eseguire i test su browser tramite un'interfaccia grafica.


### MongoDB

[MongoDB](https://www.mongodb.com/) è un database non relazionale _open source_, in grado di elaborare dati strutturati, semi-strutturati e non strutturati. Si tratta di un database orientato ai documenti che sfrutta un linguaggio di query non strutturato.

MongoDB, quindi, si allontana dalla struttura tradizionale basata su tabelle dei database relazionali in favore di documenti in stile JSON, rendendo l'integrazione di alcuni tipi di dati più facile e veloce.


### Docker
[Docker](https://www.docker.com/) è una piattaforma _open-source_ per lo sviluppo, il rilascio e l’esecuzione di applicazioni. Esso consente di separare le applicazioni dall'infrastruttura dell’host, in modo da poter fornire il software rapidamente.

Docker consente di racchiudere un’applicazione in un ambiente isolato chiamato container. È possibile eseguire più container isolati all’interno di uno stesso host. I Container sono _lightweight_ e pensati per fornire solo il necessario ad eseguire l’applicazione che essi contengono.


### npm
[Npm](https://www.npmjs.com/) npm è il package manager per la piattaforma Node JavaScript. Mette i moduli al loro posto in modo che node possa trovarli e gestisce in modo intelligente i conflitti di dipendenza. È estremamente configurabile per supportare un'ampia varietà di casi d'uso. Più comunemente, viene utilizzato per pubblicare, scoprire, installare e sviluppare programmi node.