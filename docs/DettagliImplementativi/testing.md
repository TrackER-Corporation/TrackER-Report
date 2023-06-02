---
title: Testing
parent: Dettagli implementativi
has_children: false
nav_order: 4
---

# Testing

Per verificare il corretto comportamento del sistema e l’efficacia del prodotto realizzato si è proceduto a testare le diverse componenti del sistema sia tramite test manuali, che mediante test automatici. Nelle seguenti sezioni verranno definiti con maggiore dettaglio i test realizzati.

## Testing del Server

Nel progetto del Server sono stati effettuati test automatici con **Vitest** per garantire la qualità del codice e verificare che tutte le funzionalità siano correttamente implementate. 

Qusta libreria include anche un contesto di testing per le esecuzioni asincrone. In tal modo, è possibile avviare i singoli servizi in modo asincrono e tramite l’effettuazione di richieste HTTP automatiche, è possibile verificare le risposte restituite dal servizio in modo semplice e agevole. 

Si è cercato di testare la maggior parte dei componenti in tutti i microservizi, ottenendo una coverage complessiva di: 

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#3c9d17">80.40</span> | <span style="color:#f4bd01">78.48</span> | <span style="color:#3c9d17">97.475 | <span style="color:#3c9d17">80.40</span> |

In particolare, di seguito verrà rappresentata la coverage per ogni singolo servizio:

Activity

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#3c9d17">97.02</span> | <span style="color:#3c9d17">88.23</span> | <span style="color:#3c9d17">100 | <span style="color:#3c9d17">97.02</span> |

Bills

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#f4bd01">65.15</span> | <span style="color:#3c9d17">87.5</span> | <span style="color:#3c9d17">87.5 | <span style="color:#f4bd01">65.15</span> |

Buildings

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#f4bd01">67.85</span> | <span style="color:#f4bd01">58.13</span> | <span style="color:#3c9d17">100 | <span style="color:#f4bd01">67.85</span> |

Gateway

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#3c9d17">96.29</span> | <span style="color:#3c9d17">87.5</span> | <span style="color:#3c9d17">100 | <span style="color:#3c9d17">96.29</span> |

Organization

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#f4bd01">74.01</span> | <span style="color:#f4bd01">72.41</span> | <span style="color:#3c9d17">100 | <span style="color:#f4bd01">74.01</span> |

Preferences

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#3c9d17">89.92</span> | <span style="color:#3c9d17">87.09</span> | <span style="color:#3c9d17">100 | <span style="color:#3c9d17">89.92</span> |

Renewable

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#3c9d17">86.79</span> | <span style="color:#3c9d17">81.08</span> | <span style="color:#3c9d17">100 | <span style="color:#3c9d17">86.79</span> |

Users

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#f4bd01">66.18</span> | <span style="color:#f4bd01">65.9</span> | <span style="color:#3c9d17">92.3 | <span style="color:#f4bd01">66.18</span> |


Oltre ai test automatici, sono stati eseguiti anche test manuali per verificare il corretto funzionamento del sistema nel suo insieme, includendo la comunicazione con i clients.

## Testing del Client

Anche per il Client sono stati realizzati dei test automatici per verificare il corretto funzionamento dell'applicazione. In particolare è stato utilizzato sempre **Vitest** per testare sia la logica che le interfacce.

Tuttavia, siccome il sistema è distribuito, non è stato possibile testare tutte le funzionalità dell'applicazione in quanto richiede che i micro-servizi siano attivi e in esecuzione. La coverage finale ottenuta (con 250 test) è la seguente:

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#3c9d17">89.33</span> | <span style="color:#3c9d17">84.04</span> | <span style="color:#f4bd01">70.77 | <span style="color:#3c9d17">89.33</span> |

In conclusione, sono stati eseguiti test manuali su piattaforme MacOS e Windows al fine di verificare il corretto funzionamento dell'applicazione. Inizialmente, sono stati eseguiti test sulle singole pagine per accertarsi che le richieste al server fossero gestite correttamente e che tutte le informazioni necessarie venissero visualizzate all'utente. Inoltre, è stato verificato che l'aggiornamento dei dati funzionasse correttamente. Successivamente, sono state integrate le diverse schermate per garantire che il comportamento complessivo dell'applicazione rimanesse invariato. Infine, è stato verificato che l'interfaccia fosse responsiva alle azioni dell'utente, mantenendo tutte le altre funzionalità.

<div align="center">
<img src="img/coverageUI.png" alt="coverage client" id="fig2">
 <p align="center">Coverage ottenuta per il Client</p>
</div>