---
title: TrackER
has_children: false
nav_order: 1
---

# TrackER

Il progetto ha come obiettivo quello di reimplementare un'architettura client-server classica dividendo il server in diversi micro servizi indipendenti.


## Scenario
L'applicazione ha due tipi di utenti: 
- I **Vendor**, che mettono a disposizione i loro servizi
- I **Consumer**, che aggiungono i propri edifici e comprano i servizi

Per poter accedere con entrambe le categorie è necessario prima registrarsi tramite il relativo form, nel quale bisogna specificare se ci stiamo registrando come cliente o come venditore. Dopo aver effettuato la registrazione con successo è possibile fare il login sempre con l'apposito form. 

Dopo aver fatto il login è possibile gestire i propri edifici, in particolare il Consumer potrà accedere, modificare, aggiungere o eliminare i suoi edifici personali mentre il Vendor potrà accedere e monitorare gli edifici che sono sotto contratto con lui.
Per ogni edificio è possibile andare a visualizzare i consumi e le spese di gas, corrente eletrica e acqua; inoltre si può monitorare la produzione di energia nel caso siano installate delle tecnologie rinnovabili. Se il Vendor lo permette, è possibile installare una o più risorse rinnovabili come il pannello solare o la turbina eolica.

## Componenti del sistema
<p>Server diviso in microsevizi</p>

Il server originale è nato come un unico blocco con tutti i servizi al suo interno, per migliorare e rispettare il Single-responsibility principle il server è stato diviso in più microservizi.

<p>Sito (frontend)</p>

L'applicazione permette agli utenti di interagire con tutto il sistema, partendo dalla gestione del proprio profilo, la visualizzazione degli edifici e dei consumi, la modifica dei servizi.

<div align="center">
<img src="img/Tracker Logo.png" alt="TrackER Logo"  width="220px" height="210px">
<p align="center">TrackER Logo</p>
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

#### Client
- [Client Desktop/Mobile](https://github.com/TrackER-Corporation/TrackER-UI)
