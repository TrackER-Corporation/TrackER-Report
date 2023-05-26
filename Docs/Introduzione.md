---
title: Introduzione
has_children: false
nav_order: 2
---

# Introduzione

Per il progetto di Laboratorio di Sistemi Software, si è pensato di utilizzare il progetto realizato per Applicazioni e Servizi Web e di modernizzarlo applicando gli insegnamenti visti nel corso, ovvero si vuole effettuare un refactor del server (dividendolo in più microservizi indipendenti) e un cambio di tecnologie per la realizzazione. Inoltre si vuole anche migliorare il codice e correggere gli errori presenti, ad esempio la mancanza di test o funzioni troppo complesse, il tutto seguendo i processi di Domain-Driven-Design, Continuos Integration e DevOps.

Il progetto nasce come proposta nel creare una soluzione software web-based di gestione, tracciamento e vendita dell’energia sia dal punto di vista dei venditori (Vendors) sia per gli utenti consumatori (buildings owner).
L’obiettivo primario è quello di consentire a ciascun utente di poter visionare e gestire i propri edifici per quanto riguarda la produzione (tramite fonti rinnovabili) e il consumo di risorse.

La web application si compone di due principali interfacce: una relativa al Vendor e una al Building Owner. 
E’ possibile raggiungere queste interfacce soltanto dopo essersi registrati al sistema.
Da questa è possibile aggiungere edifici da monitorare, comprare diversi contratti, installare dispositivi rinnovabili e visualizzare tutta la mole di dati prodotti dalle precedenti tecnologie; inoltre è possibile per un’azienda registrare i propri servizi personalizzando tutti i costi e le specifiche risorse da fornire.

Il sistema sarà caratterizzato da due componenti: due tipologie di Client e un server diviso in 7 microsevizi più un gateway.
In particolare, grazie alla flessibilità di React, è possibile collegarsi al sito sia tramite un client Desktop che tramite un client Mobile; entrambi gli approcci consentono di visualizzare e gestire gli stessi dati.

