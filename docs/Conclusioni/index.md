---
title: Conclusioni
has_children: false
nav_order: 10
---

# Conclusioni

L'obiettivo del progetto era quello di effettuare un porting di un vecchio progetto per migliorarlo sotto diversi aspetti, partendo dal semplice refactor del codice fino alla divisione e implementazione di un server con un'architettura diversa da quella originale. L'applicazione Web deve funzionare sia logicamente che graficamente sia da Desktop che da Mobile, permettendo a qualsiasi utente di collegarsi e di usufruire del servizio. 

Per realizzare l'obiettivo è stata effettuata un'analisi del dominio, che ha portato alla verifica e al miglioramento dei diversi requisiti già individuati precedentemente. 

Una volta che tutta la parte precendente è stata risolta è stato possibile procedere all'implementazione dell'applicazione, partendo dal refactor del Server in microservizi per poi concludere con il porting della grafica. Il progetto terminato rispecchia tutti gli obiettivi che il gruppo si era fissato inizialmente.

L'adozione della metodologia SCRUM ha permesso di procedere velocemente, dividendo il progetto in diversi task e dividendo il carico di lavoro uniformemente tra i componenti, l'utilizo di tecnologia per la Continous Integration ha permesso di identificare possibile problematiche prima che venissiro immesse in produzione, permettendo la riduzione di bug solving e velocizzando anche l'andamento generale, infine l'utilizzo della metodologia di Pair Programming ha portato alla conclusione anticipata di diversi task e ha aumentato sia la velocità di produzione che la qualità del codice.

Riteniamo che la realizzazione di questo progetto abbia aumentato le nostre competenze in quanto:

- Ci ha permesso di consolidare la metodologia SCRUM essendo il nostro secondo approccio a questa tecnica;
- Ci ha avvicinato alla strategia DevOps e abbiamo approfondito alcuni strumenti messi a disposizione da GitHub;
- Ci ha dato la possibilità di lavorare con un sistema distribuito e di poter utilizzare container Docker;
- Ci ha dato un'idea dell'approccio di Domain Driver Design.

## Sviluppi futuri
Possibili funzionalità aggiuntive che possono essere realizzate in futuro, in aggiunta a quelle già presenti, grazie alla modularità del sistema, possono essere le seguenti:

- Aggiunta di un sistema di notifica capace di informare i diversi utenti sullo stato di consumo o errori;
- Supporto email per problemi, eventi e promemoria;
- Personalizzazione dell'interfaccia, facendo decidere al'utente quali grafici visualizzare.
