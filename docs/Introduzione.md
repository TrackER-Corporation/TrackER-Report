---
title: Introduzione
has_children: false
nav_order: 2
---

# Introduzione

Per il progetto di Laboratorio di Sistemi Software, si è utilizzato il progetto realizato per Applicazioni e Servizi Web ([TrackER](https://github.com/DallasCorporation/TrackER)) cercando di modernizzarlo applicando gli insegnamenti visti durante il corso.

Le operazioni che si vogliono effettuare seguendo i processi di Domain-Driven-Design, Continuos Integration e DevOps sono le seguenti:
- Scomposizione dell'architettura monolitica del Server in più servizi indipendenti;
- Utilizzo di tecnologie più recenti e performanti;
- Utilizzo dei principi di progettazione del software DRY, KISS e SOLID;
- Utilizzo di TypeScript per la tipizzazione statica e il rilevamento degli errori durante la compilazione;
- Aggiunta di test per garantire la correttezza  e aumentare la qualità del codice.


## Descrizione in dettaglio
Il progetto nasce come proposta nel creare una soluzione software web-based di gestione, tracciamento e vendita dell’energia sia dal punto di vista dei venditori **Vendors** sia per gli utenti consumatori **Buildings owner**.
L’obiettivo primario è quello di consentire a ciascun utente di poter visionare e gestire i propri edifici per quanto riguarda la produzione (tramite fonti rinnovabili) e il consumo di risorse.

La web application si compone di due principali interfacce: Vendor e Building Owner. 
E’ possibile raggiungere queste interfacce soltanto dopo essersi registrati al sistema.
All'interno dell'applicazione, è possibile aggiungere edifici, monitorare i loro consumi, siglare diversi contratti, installare dispositivi rinnovabili, visualizzare i consumi e guadagni maturati e registrare i propri servizi personalizzando i vari costi e le specifiche risorse fornite.

Il sistema sarà caratterizzato da due componenti: 
- Web Application: raggiungibile da qualsiasi dispositivo connesso a internet;
- Web Server: composto da microservizi.
