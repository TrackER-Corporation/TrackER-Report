---
title: TrackER
has_children: false
nav_order: 1
---

# TrackER

Il progetto si propone di realizzare un'applicazione web completa e intuitiva per la gestione e il monitoraggio delle utenze degli edifici. 

L'applicazione sarà progettata per consentire agli utenti di registrare e tenere traccia dei consumi energetici, nonché dei relativi guadagni derivanti dalla produzione di energia rinnovabile, come ad esempio l'energia solare.

## Scenario
Gli utenti potranno registrare i propri edifici consentendo loro di tenere sotto controllo le spese energetiche. Inoltre essi potranno installare impianti di produzione di energia rinnovabile, come pannelli solari o turbine eoliche, per monitorare la quantità di energia generata e i risparmi ottenuti.

L'applicazione offrirà funzionalità avanzate per analizzare i dati e visualizzazioni grafiche intuitive, consentendo agli utenti di identificare le aree di consumo e di adottare misure di efficienza energetica.

Per i fornitori di energie, l'applicazione offrirà una piattaforma dedicata per la gestione degli utenti e delle tariffe, consentendo loro di monitorare il consumo energetico e calcolare i guadagni derivanti dai servizi forniti. Potranno anche cambiare i piani tariffari relativi ai consumi di energia elettrica, acqua e gas e potranno anche inserire nuovi prodotti rinnovabili sul mercato.


## Componenti del sistema
<b>Web Server</b>

Il web server è progettato come un'architettura a microservizi, costituito da componenti modulari e indipendenti che lavorano insieme per fornire funzionalità specifiche. Questa struttura modulare permette una maggiore scalabilità, resilienza e facilità di manutenzione dell'applicazione. I microservizi interagiscono tra loro attraverso interfacce ben definite, consentendo una comunicazione efficiente e flessibile tra i diversi componenti. Ogni microservizio si focalizza su una specifica responsabilità funzionale, garantendo una separazione chiara delle preoccupazioni e una migliore gestione del codice. Questa architettura favorisce una maggiore agilità nello sviluppo, consentendo di implementare e rilasciare modifiche in modo indipendente per ciascun microservizio senza influire sugli altri.

<b>Web Application</b>

Tramite un'interfaccia utente intuitiva, gli utenti possono gestire il proprio profilo e aggiornando le informazioni personali.

Una delle funzionalità principali dell'applicazione è la visualizzazione degli edifici registrati, consentendo agli utenti di accedere alle informazioni dettagliate su ciascun edificio, come le informazioni di contatto, la posizione geografica e i consumi energetici registrati. Inoltre, gli utenti possono visualizzare grafici e report che mostrano i consumi energetici nel corso del tempo, consentendo loro di monitorare l'andamento e individuare eventuali picchi o anomalie.

I venditori possono aggiornare e personalizzare le tariffe energetiche offerte agli utenti. Possono aggiungere nuovi dispositivi energetici nel mercato. Possono inserire le informazioni tecniche e le specifiche dei dispositivi, consentendo agli utenti di visualizzare e selezionare i dispositivi di gestione energetica. Questa funzionalità permette ai venditori di energia di espandere la gamma di servizi e prodotti offerti agli utenti, offrendo una maggiore flessibilità e scelta.

Complessivamente, l'applicazione offre una piattaforma completa che permette sia agli utenti che ai venditori di energia di interagire e gestire in modo efficace il sistema di monitoraggio e gestione delle utenze energetiche degli edifici, fornendo funzionalità specifiche per le esigenze di entrambe le parti.

<div align="center">
<img src="img/Logo.png" alt="TrackER Logo"  width="220px" height="210px">
</div>

### Componenti del gruppo
- Emanuele Dall'Ara  - <emanuele.dallara@studio.unibo.it>
- Nicholas Ricci  - <nicholas.ricci@studio.unito.it>

### Repository
- [Organizzazione TrackER](https://github.com/TrackER-Corporation)
- [Report](https://github.com/TrackER-Corporation/TrackER-Report)

#### Microservices
- [Activity](https://github.com/TrackER-Corporation/tracker-activity-service)
- [Bills](https://github.com/TrackER-Corporation/tracker-bills-service)
- [Buildings](https://github.com/TrackER-Corporation/tracker-buildings-service)
- [Gateway](https://github.com/TrackER-Corporation/tracker-gateway-service)
- [Organization](https://github.com/TrackER-Corporation/tracker-organization-service)
- [Preferences](https://github.com/TrackER-Corporation/tracker-preferences-service)
- [Renewable](https://github.com/TrackER-Corporation/tracker-renewable-service)
- [Users](https://github.com/TrackER-Corporation/tracker-users-service)

#### Web Application
- [Web Application](https://github.com/TrackER-Corporation/TrackER-UI)
