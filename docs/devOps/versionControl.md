---
title: Version control
parent: Pratiche devOps
has_children: false
nav_order: 3
---
# Version control

Per software versioning si intende il processo di assegnare un identificatore univoco a uno stato del software. L'identificativo che viene associato è di norma una sequenza alfanumerica di caratteri separati da punti, _slashes_ o _dashes_.

Nel nostro caso, per poter distinguere le diverse versioni del software, si è deciso di seguire le linee guida proposte dal [Semantic Versioning](https://semver.org/). La versione del software, di conseguenza, è rappresentata da tre numeri separati da un punto: MAJOR.MINOR.PATCH.

L'incremento di uno di questi tre numeri viene eseguito attraverso queste regole:

- **MAJOR**, quando vengono effettuate delle modifiche incompatibili con le diverse API prodotte;
- **MINOR**, quando vengono aggiunte delle funzionalità che sono retrocompatibili con versioni precedenti del sistema;
- **PATCH**, quando vengono aggiornati dei bug mantenendo una retrocompatibilità.

Il team, ha inoltre deciso, di promuovere il processo di semantic versioning in modo automatico, sfruttando per questo le action di GitHub. In particolare, la determinazione della versione corretta da associare allo stato del software viene fatta sula base dei commit salvati, che sono stati scritti seguendo l'approccio [Conventional Commit](https://www.conventionalcommits.org/en/v1.0.0/). Un commit viene pertanto scritto seguendo il seguente formato:

```bash
<type>[optional scope]: <description>
```

I tipi di commit che sono stati adottati, nel nostro caso, sono i seguenti: 

- **chore**, in caso di cambiamenti che non riguardano il codice di produzione;
- **docs**, per cambiamenti che riguardano solo la documentazione;
- **feat**, in caso di aggiunta di una nuova feature;
- **fix**, quando un bug viene corretto;
- **refactor**, in caso di cambiamenti del codice che non riguardano né la correzione di un bug né l'aggiunta di una nuova feature (e.g. spostare un metodo da una classe ad un’altra);
- **style** per cambiamenti che non impattano sul senso del codice (e.g. rimozione di spazi bianchi, formatting, ecc…);
- **test** per l'aggiunta di nuovi test o correzione di test già esistenti.

Di conseguenza, associando ai commit i tipi precedenti e impostando opportunamente le GitHub actions, è stato possibile far si che il sistema fosse in grado di riconoscere automaticamente quale versione associare al software, sulla base delle operazioni effettuate e documentate.