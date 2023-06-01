---
title: Sistema di backend
parent: Design dettagliato
grand_parent: Design
has_children: false
nav_order: 2
---
# Sistema di backend

Una volta individuati i bounded context presenti all'interno del sistema di backend è necessario individuare una strategia di integrazione tale per cui i bounded context al suo interno siano il più autonomi possibili; solo in questo modo si possono evitare ad esempio dei rallentamenti o indisponibilità del sistema. A seguito dell'analisi dei requisiti e considerando l'autonomia dei bounded context, si è quindi scelto di realizzare un'architettura a micro-servizi, la quale porta con se diversi vantaggi, come: l'isolamento degli errori a singoli componenti del sistema, una maggiore scalabilità, semplicità nel deployment etc.

Come detto precedentemente, nell'introduzione del Design, sono stati individuati otto micro-servizi: Activity, Bills, Buildings, Gateway, Organization, Preferences, Renewable, Users.

I diversi micro-servizi realizzati hanno tutti caratteristiche simili, ossia:

- Connessione al database: Viene chiamata la funzione connectToDatabase() dal modulo database.service per stabilire la connessione al database. Questo modulo non è incluso nel codice fornito, ma probabilmente contiene la logica per gestire la connessione al database.

- Configurazione delle variabili di ambiente: Viene utilizzato dotenv.config() per caricare le variabili di ambiente dal file .env.

- Configurazione del server: Viene creato un'istanza di Express chiamata app. Vengono utilizzati app.use(cors()) per abilitare le richieste cross-origin e app.use(express.json()) per consentire la lettura dei dati JSON nelle richieste.

- Utilizzo delle route: Viene utilizzato app.use(router) per utilizzare le rotte definite nel modulo route. Il modulo delle rotte, che viene importato come router, gestirà le richieste in arrivo alle varie rotte dell'applicazione.

- Avvio del server: Viene chiamato il metodo app.listen(port, callback) per avviare il server. Il server ascolterà le richieste sulla porta specificata nella variabile di ambiente process.env.PORT. Quando il server è in ascolto, verrà stampato un messaggio sulla console.

- Esportazione dell'app: Viene esportato l'oggetto app, che rappresenta l'istanza di Express, in modo che possa essere utilizzato altrove nell'applicazione.

In base a quanto detto in precedenza, è possibile dedurre che un micro-servizio possa svolgere sia il ruolo di **server**, ovvero accettare le richieste provenienti da altri micro-servizi in esecuzione, sia il ruolo di **client**, ovvero inviare richieste ad altri micro-servizi con cui comunica al fine di completare le proprie attività.

## Tactical design
Per la realizzazione della componente di backend, sono state seguite le linee guida del tactical design, cercando quindi di individuare tra i concetti del dominio quali avessero il ruolo di entità, value objects o domain service.


## Interazione tra i diversi micro-servizi
