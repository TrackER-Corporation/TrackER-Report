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

<div align="center">
<img src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png" width="200" alt="icona github" id="fig1">
</div>

### React

[React](https://react.dev/) è una libreria JavaScript per la creazione di interfacce utente. È progettata per sviluppare applicazioni web interattive, consentendo agli sviluppatori di costruire componenti riutilizzabili che si aggiornano in modo efficiente in base ai cambiamenti dei dati. React utilizza un approccio basato su componenti e un modello di programmazione dichiarativo, semplificando lo sviluppo e la gestione dello stato dell'applicazione. Grazie al suo approccio al virtual DOM, React ottimizza le prestazioni dell'applicazione, consentendo una user experience fluida e reattiva. È ampiamente utilizzato e supportato da una vasta comunità di sviluppatori.

<div align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/1150px-React-icon.svg.png" width="200" alt="icona react" id="fig2">
</div>

### Vite

Il framework [Vite](https://vitejs.dev/guide/) si basa su diversi principi fondamentali per garantire prestazioni elevate e un'esperienza di sviluppo fluida. In particolare, utilizza i moduli ES nativi e le moderne API del browser per compilare il codice "on the fly" e garantire tempi di build rapidi e aggiornamenti istantanei nel browser. Inoltre, il server di sviluppo integrato in Vite è ottimizzato per il reloading rapido e la sostituzione dei moduli senza fermare l'esecuzione, consentendo agli sviluppatori di vedere in tempo reale le modifiche apportate al codice senza dover aggiornare l'intera pagina.

Vite implementa anche il caricamento "lazy" dei moduli, consentendo di migliorare le prestazioni dell'applicazione, soprattutto per quelle di grandi dimensioni, e di garantire un caricamento iniziale più rapido per gli utenti. Inoltre, utilizza tecniche come il "tree-shaking" e il "code splitting" per rimuovere il codice inutilizzato dall'applicazione e dividere il codice in sezioni più piccole, migliorando ulteriormente le prestazioni.

<div align="center">
<img src="https://vitejs.dev/logo-with-shadow.png" width="200" alt="icona vite" id="fig3">
</div>


### Vitest

Per il progetto si è deciso di utilizzare il framework [Vitest](https://vitest.dev/) per la realizzazione di test automatizzati sul codice che ha permesso di implementare tutti i vari test necessari per garantire la qualità del codice e analizzare la coverage del progetto, con la possibilità di eseguire i test su browser tramite un'interfaccia grafica.

<div align="center">
<img src="https://vitest.dev/logo-shadow.svg" width="200" alt="icona vitest" id="fig4">
</div>

### Ant Design

[Ant Design](https://ant.design/) è una libreria di componenti UI (User Interface) reattivi e moderni per lo sviluppo di applicazioni web. Offre un'ampia gamma di componenti predefiniti, che vanno dai componenti di base come pulsanti, campi di input e tabelle, a componenti più complessi come menu, modali, grafici e molto altro. Questi componenti sono progettati con una forte attenzione all'usabilità, all'accessibilità e alla coerenza visiva, fornendo una solida base per la creazione di interfacce utente attraenti e funzionali.

<div align="center">
<img src="https://static-00.iconduck.com/assets.00/ant-design-icon-512x512-ncocfg8e.png" width="200" alt="icona Ant Design" id="fig5">
</div>

### MongoDB

[MongoDB](https://www.mongodb.com/) è un database non relazionale _open source_, in grado di elaborare dati strutturati, semi-strutturati e non strutturati. Si tratta di un database orientato ai documenti che sfrutta un linguaggio di query non strutturato.

MongoDB, quindi, si allontana dalla struttura tradizionale basata su tabelle dei database relazionali in favore di documenti in stile JSON, rendendo l'integrazione di alcuni tipi di dati più facile e veloce.

<div align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/MongoDB_Logo.svg/2560px-MongoDB_Logo.svg.png" width="200" alt="icona vitest" id="fig6">
</div>

### Docker
[Docker](https://www.docker.com/) è una piattaforma _open-source_ per lo sviluppo, il rilascio e l’esecuzione di applicazioni. Esso consente di separare le applicazioni dall'infrastruttura dell’host, in modo da poter fornire il software rapidamente.

Docker consente di racchiudere un’applicazione in un ambiente isolato chiamato container. È possibile eseguire più container isolati all’interno di uno stesso host. I Container sono _lightweight_ e pensati per fornire solo il necessario ad eseguire l’applicazione che essi contengono.

<div align="center">
<img src="https://www.docker.com/wp-content/uploads/2022/03/vertical-logo-monochromatic.png" width="200" alt="icona vitest" id="fig7">
</div>

### npm
[Npm](https://www.npmjs.com/) è il package manager per la piattaforma Node JavaScript. Mette i moduli al loro posto in modo che node possa trovarli e gestisce in modo intelligente i conflitti di dipendenza. È estremamente configurabile per supportare un'ampia varietà di casi d'uso. Più comunemente, viene utilizzato per pubblicare, scoprire, installare e sviluppare programmi node.

<div align="center">
<img src="https://static-00.iconduck.com/assets.00/npm-icon-2048x2048-8sw7kisf.png" width="200" alt="icona vitest" id="fig8">
</div>