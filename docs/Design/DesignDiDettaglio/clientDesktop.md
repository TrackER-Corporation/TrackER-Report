---
title: Client Desktop
parent: Design dettagliato
grand_parent: Design
has_children: false
nav_order: 3
---
# Client

Durante lo sviluppo del progetto, sono stati scelti diversi pattern React per la loro efficacia e la loro flessibilità. In particolare, sono stati utilizzati i seguenti pattern:

* **Provider Pattern**: il provider pattern è un pattern di progettazione molto utile per la condivisione di dati globali tra diversi componenti in un'applicazione React. In pratica, viene creato un componente Provider che detiene i dati e li condivide con gli altri componenti attraverso un Consumer o degli Hook personalizzati. Questo permette di semplificare la logica di gestione dei dati e garantire una maggiore efficienza nell'interazione tra i componenti. <br>
Il provider pattern è flessibile e può essere utilizzato in diversi contesti, come ad esempio per lo scambio di dati tra componenti di livello diverso o per la gestione di dati comuni a più pagine dell'applicazione. In questo modo, è possibile evitare di passare manualmente i dati da un componente all'altro attraverso le props, semplificando notevolmente il codice e rendendo l'applicazione più facile da leggere e mantenere. <br> Un esempio di utilizzo del provider pattern potrebbe essere quello di gestire lo stato globale dell'applicazione, ad esempio la lingua selezionata dall'utente o il tema dell'applicazione. In questo caso, il Provider detiene lo stato globale dell'applicazione e lo condivide con i componenti figli attraverso un Consumer o un Hook personalizzato. In questo modo, i componenti figli possono accedere allo stato globale senza doverlo passare manualmente come props attraverso ogni livello di gerarchia dei componenti.

* **Hooks**: gli hooks sono stati una rivoluzione per la progettazione dei componenti React, poiché hanno introdotto un modo semplice e diretto per i componenti di accedere a funzionalità come props, stato e contesto. Questo ha permesso di separare la logica di gestione dello stato e della logica di rendering dei componenti, semplificando il codice e rendendolo più leggibile.<br>Gli Hooks sono funzioni speciali che consentono di utilizzare funzionalità di React in componenti funzionali, che in precedenza erano disponibili solo nei componenti di classe. Ciò ha permesso ai componenti funzionali di gestire lo stato interno, utilizzare il ciclo di vita del componente e accedere al contesto senza doversi convertire in classi.<br>Inoltre, l'utilizzo degli hooks ha permesso di semplificare la gestione delle interazioni tra i componenti, poiché condividono la stessa logica di stato e di gestione degli eventi. Ciò ha reso più facile la creazione di componenti altamente modulari e riutilizzabili.<br>Infine, gli Hooks hanno fornito una maggiore flessibilità nella gestione del rendering, poiché è possibile utilizzare gli Hooks per controllare quando e come un componente viene renderizzato. Questo ha permesso di migliorare le prestazioni dell'applicazione, evitando il rendering di componenti inutili o evitando di eseguire il rendering di componenti troppo spesso.

* **Compound Pattern**: il compound pattern è un pattern avanzato che consente a più componenti di condividere stato e logica in modo semplice ed efficiente. Questo pattern si basa sull'utilizzo di un componente principale, noto come "contenitore" o "wrapper", che gestisce lo stato e la logica comune a tutti i componenti figli.<br>In pratica, il componente principale detiene lo stato e la logica comune a tutti i componenti figli e passa queste informazioni ai componenti figli come props. In questo modo, i componenti figli possono accedere allo stato e alla logica comune senza doverla gestire autonomamente.<br>Il compound pattern è molto utile quando si hanno componenti che condividono una grande quantità di stato e logica comune. In questo caso, il compound pattern semplifica notevolmente la gestione dei dati e garantisce una maggiore efficienza nella gestione delle interazioni tra i componenti.<br>Ad esempio, si potrebbe utilizzare il compound pattern per creare un componente che gestisca una lista di elementi e un componente che gestisca la singola visualizzazione di un elemento. In questo caso, il componente principale detiene lo stato della lista di elementi e la logica di gestione degli elementi, mentre il componente figlio gestisce solo la visualizzazione di un singolo elemento. Il componente principale passa le informazioni relative alla lista di elementi al componente figlio come props, semplificando notevolmente la gestione dei dati e garantendo una maggiore efficienza nella gestione delle interazioni tra i componenti.<br>Inoltre, il compound pattern è molto flessibile e può essere utilizzato in diversi contesti, come ad esempio per la gestione di modali, tooltip, form e widget complessi. In ogni caso, il compound pattern semplifica la gestione dei dati e della logica comune, garantendo una maggiore modularità e riutilizzabilità dei componenti.

* **Render props pattern**: il pattern render props è un pattern di React che consente a un componente di ricevere una funzione come prop, che a sua volta ritorna un elemento React. In pratica, invece di implementare la propria logica di rendering, il componente utilizza la funzione passata come prop per renderizzare il componente figlio.<br>Ciò consente di controllare in modo più preciso il rendering di un componente figlio, poiché la funzione passata come prop può contenere la logica di rendering e avere accesso alle props e allo stato del componente genitore.<br>Ad esempio, si potrebbe utilizzare il pattern render props per creare un componente che gestisce la visualizzazione di un tooltip. In questo caso, il componente genitore passerebbe una funzione come prop al componente figlio che gestisce la visualizzazione del tooltip. La funzione passata come prop sarebbe responsabile della logica di rendering del tooltip e avrebbe accesso alle props e allo stato del componente genitore.

* **State reducer pattern**: il pattern state reducers di React consente di gestire in modo pulito l'aggiornamento dello stato di un componente in base a diversi criteri. In pratica, il componente genitore passa una funzione come prop al componente figlio che gestisce lo stato. Questa funzione viene utilizzata per aggiornare lo stato del componente figlio, in base a diversi criteri specificati dal componente genitore.<br>Il pattern state reducers è utile quando si ha la necessità di gestire lo stato di un componente in modo complesso e personalizzato. La funzione passata come prop può contenere la logica per aggiornare lo stato in modo preciso, in base a criteri specifici, come ad esempio la validazione dei dati inseriti dall'utente o la gestione di eventi asincroni.<br>Inoltre, il pattern State Reducers consente di separare la logica di gestione dello stato dal componente figlio, semplificando il codice e rendendolo più leggibile. Ciò consente di avere un maggiore controllo sulla gestione dello stato e di garantire una maggiore flessibilità nella gestione degli aggiornamenti dello stato.<br>Il pattern state reducers è spesso utilizzato in combinazione con il pattern render props. In questo caso, la funzione passata come prop alcomponente figlio utilizza il pattern state reducers per gestire l'aggiornamento dello stato del componente figlio e la funzione Render Props per controllare il rendering del componente figlio.

- **Component-Based Architecture**: l'architettura basata sui componenti è un modello di progettazione del software che si concentra sulla costruzione di applicazioni dividendo il sistema in componenti autonomi e riutilizzabili. Ogni componente rappresenta una parte funzionale e indipendente dell'applicazione, che può essere sviluppata, testata e mantenuta separatamente.<br>
L'architettura basata sui componenti è ampiamente utilizzata in molte tecnologie e framework, incluso React. Questo modello di progettazione aiuta a creare applicazioni scalabili, modulari e facili da mantenere, favorendo la riutilizzabilità del codice e la separazione delle responsabilità.

- **Conditional Rendering Design Pattern**: è una tecnica di progettazione dell'interfaccia utente che permette di mostrare o nascondere parti dell'interfaccia in base a determinate condizioni o stati dell'applicazione. Questa tecnica si basa su condizioni definite e utilizza direttive o costrutti specifici per il rendering condizionale. Può coinvolgere la manipolazione dello stato o dei dati dell'applicazione e la creazione o il caricamento dinamico dei componenti. Il rendering condizionale viene utilizzato per adattare l'interfaccia utente in modo dinamico e offrire un'esperienza personalizzata agli utenti.

L'utilizzo di questi pattern ha consentito di sviluppare il progetto in modo modulare e flessibile, semplificando la gestione dei dati globali e la condivisione di logica e stato tra i componenti. Inoltre, l'utilizzo di Hooks e di Render props ha permesso di semplificare la gestione del ciclo di vita dei componenti e di fornire una maggiore flessibilità nella gestione del rendering. Infine, lo State reducer pattern ha permesso di gestire in modo efficace l'aggiornamento dello stato e di garantire una maggiore coerenza e pulizia del codice.

Il Client (Building Owner) si compone di sei schermate principali:
- Dashboard;
- Buildings;
- Add New Building;
- Organizations;
- Invoices;
- Profilo Personale.

Mentre il Client (Vendor) si compone di otto schermate principali:
- Dashboard;
- Electric Supplier;
- Water Supplier;
- Gas Supplier;
- Energy Resources;
- Customers;
- Edit Plan;
- Organization.

## Tactical design

Il Model fornisce una rappresentazione dei dati, rendendo più facile l’accesso e la gestione di questi da parte dei componenti del sistema. In particolare, è costituito da:

- `User`: i dati utente;
- `UserPreference`: le preferenze di un `User`;
- `Organization`: informazioni dell'organizzazione;
- `Building`: informazioni sugli immobili;
- `Bills`: informazioni riguardanti i consumi e le produzione energetiche;
- `BillsAggregated`: somma di tutte le `Bills` di tutti i `Buildings` di un `User`;
- `Activity`: informazioni sugli accessi;
- `Timestamp`: formato temporale delle `Bills`;
- `EnergyType`: tipo di risorsa rinnovabile;
- `Renewable`: quale `EnergyType` di fonte rinnovabile, a quale `Organization` appartiene e chi la sta usando; 
- `Credentials`: dati di accesso per gli `Users`.
