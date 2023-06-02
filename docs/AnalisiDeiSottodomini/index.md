---
title: Analisi dei sottodomini
has_children: true
nav_order: 6
---
# Analisi dei sottodomini

Nel Domain Driven Design per poter meglio gestire la complessità del dominio che si vuole analizzare si consiglia di esplorare a fondo il problem-domain individuando sottodomini che siano più semplici da gestire, inoltre, è importante associare ad ognuno di questi sotto-domini individuati un’importanza: core, generic, support, in modo da aiutare gli sviluppatori a comprendere meglio quali sono gli aspetti principali su cui ci si dovrà concentrare. 

Per il problema in esame il tema di sviluppo a seguito del processo di knowledge crunching e di analisi del dominio che è stata eseguita, è riuscito ad individuare tre sotto-domini principali:

- **System Management**, il quale racchiude gli elementi per la gestione di utenti e risorse;
- **Web Application**, il quale racchiude le funzionalità principali dell'applicazione;
- **Client**, che comprende i diversi elementi necessari all'accesso e all'utilizzo dell'applicazione da parte degli utenti (sia Vendor che Building Owner).

Una volta individuati i seguenti sotto-domini, il team ha cercato di individuare l’importanza strategica che questi possiedono per il business, aiutandosi attraverso l’utilizzo dei domain charts.

<div align="center">
<img src="img/core-domain.jpg" alt="Core Domain Chart" width="70%">
<p align="center" id="fig1">Core Domain Chart</p>
</div>

Come si può vedere dal grafico, il sub-domain: System Management, è stato classificato come **supporting domain,** in quanto, racchiude al suo interno tecnologie e sistemi che possono essere utilizzati come supporto per le funzionalità principali di gestione del sistema e della sua mole di dati. Inoltre, il modello che si intende realizzare non ha una complessità molto elevata e una Business Differentiation buona, ma non così alta da renderlo un core domain. 

Web Application è stato identificato come **core-domain**. Il modello che si intende realizzare per questo dominio è abbastanza complesso, per di più se le funzionalità che si vogliono realizzare vengono gestite in modo opportuno si può ottenere un buon livello di business differentiation per l’organizzazione.

Infine, il sub-domain client è stato classificato come **generic-domain**, in quanto non comprende elementi che possono contribuire a un’elevata differenziazione del business e il modello che si vuole realizzare, non è molto complesso.
