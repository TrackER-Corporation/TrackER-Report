---
title: Testing
parent: Dettagli implementativi
has_children: false
nav_order: 4
---

# Testing

Per verificare il corretto comportamento del sistema e l’efficacia del prodotto realizzato si è proceduto a testare le diverse componenti del sistema sia tramite test manuali, che mediante test automatici. 
Nelle seguenti sezioni verranno definiti con maggiore dettaglio i test realizzati.

## Testing del Server

Durante la progettazione Server sono stati effettuati test automatici tramite la libreria **Vitest** per verificare la qualità del codice e tutte le funzionalità. 

Vitest ha permesso di effettuare test sulle API implementate ed esposte dai vari microservizi, verificando che i vari endpoint rispondessero correttamente alle richieste e restituissero i dati attesi. Inoltre, è stato possibile testare la gestione degli errori e la validazione dei dati in input.

Si è cercato di testare la maggior parte dei componenti in tutti i microservizi, ottenendo una coverage complessiva di: 

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#3c9d17">80.40</span> | <span style="color:#f4bd01">78.48</span> | <span style="color:#3c9d17">97.475 | <span style="color:#3c9d17">80.40</span> |

Di seguito verrà rappresentata la coverage per ogni singolo servizio:

#### Activity

Servizio| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: | :---: |
|Activity| <span style="color:#3c9d17">97.02</span> | <span style="color:#3c9d17">88.23</span> | <span style="color:#3c9d17">100 | <span style="color:#3c9d17">97.02</span> |
|Bills| <span style="color:#f4bd01">65.15</span> | <span style="color:#3c9d17">87.5</span> | <span style="color:#3c9d17">87.5 | <span style="color:#f4bd01">65.15</span> |
| Buildings| <span style="color:#f4bd01">67.85</span> | <span style="color:#f4bd01">58.13</span> | <span style="color:#3c9d17">100 | <span style="color:#f4bd01">67.85</span> |
| Gateway| <span style="color:#3c9d17">96.29</span> | <span style="color:#3c9d17">87.5</span> | <span style="color:#3c9d17">100 | <span style="color:#3c9d17">96.29</span> |
| Organization| <span style="color:#f4bd01">74.01</span> | <span style="color:#f4bd01">72.41</span> | <span style="color:#3c9d17">100 | <span style="color:#f4bd01">74.01</span> |
| Preferences| <span style="color:#3c9d17">89.92</span> | <span style="color:#3c9d17">87.09</span> | <span style="color:#3c9d17">100 | <span style="color:#3c9d17">89.92</span> |
| Renewable| <span style="color:#3c9d17">86.79</span> | <span style="color:#3c9d17">81.08</span> | <span style="color:#3c9d17">100 | <span style="color:#3c9d17">86.79</span> |
| Users| <span style="color:#f4bd01">66.18</span> | <span style="color:#f4bd01">65.9</span> | <span style="color:#3c9d17">92.3 | <span style="color:#f4bd01">66.18</span> |


## Testing del Client

Anche per il Client sono stati realizzati dei test automatici per verificare il corretto funzionamento dell'applicazione utilizzato sempre **Vitest** per testare sia la logica che le interfacce.

Tuttavia, siccome il sistema è distribuito, non è stato possibile testare tutte le funzionalità dell'applicazione in quanto richiede che i micro-servizi siano attivi e in esecuzione. La coverage finale ottenuta (con **250 test**) è la seguente:

| Stmts | Branch | Funcs | Lines |
| :---: | :---: | :---: | :---: |
| <span style="color:#3c9d17">89.33</span> | <span style="color:#3c9d17">84.04</span> | <span style="color:#f4bd01">70.77 | <span style="color:#3c9d17">89.33</span> |

In conclusione, sono stati eseguiti test manuali su piattaforme MacOS e Windows al fine di verificare il corretto funzionamento dell'applicazione. Inizialmente, sono stati eseguiti test sulle singole pagine per accertarsi che le richieste al server fossero gestite correttamente e che tutte le informazioni necessarie venissero visualizzate all'utente. Inoltre, è stato verificato che l'aggiornamento dei dati funzionasse correttamente. Successivamente, sono state integrate le diverse schermate per garantire che il comportamento complessivo dell'applicazione rimanesse invariato. Infine, è stato verificato che l'interfaccia fosse responsive alle azioni dell'utente, mantenendo tutte le altre funzionalità.

<div align="center">
<img src="img/coverageUI.png" alt="coverage client" id="fig2">
 <p align="center">Coverage ottenuta per il Client</p>
</div>