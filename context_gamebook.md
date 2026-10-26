# Regole d'Oro di Game Design Narrativo e Architettura Librogame: Dimensione Avventura

Questo documento definisce le linee guida architetturali, narrative e sistemiche per il librogame interattivo *Dimensione Avventura* (ispirato ai classici Fighting Fantasy).

---

## 1. Architettura a Grafo e Integrità dei Percorsi
- **Nessun vicolo cieco involontario:** Ogni nodo non terminale deve possedere almeno un'uscita valida (`choices`, `on_victory`, o branching condizionale).
- **Controllo Raggiungibilità:** Tutti i nodi della storia devono essere raggiungibili da almeno un percorso valido a partire dal Nodo 1.
- **Risoluzione dei Cicli e Anti-Respawn:** I grafi contenenti biforcazioni esplorative bidirezionali (es. 18 <-> 22, 17 <-> 19) devono tracciare i nemici già abbattuti (`gameState.defeated_enemies[nodeId] = true`) affinché un mostro non respawni all'infinito costringendo a un'ingiusta usura di PF.
- **Prevenzione del "Loop Indietro":** I nodi di arrivo avanzati verso il climax non devono contenere scelte che riportano a nodi iniziali privi di senso geografico.

---

## 2. Significatività delle Scelte e Bivii Reali
- **Bivii di Stato (State-Driven Choices):** Le scelte devono riflettere l'inventario e le statistiche del personaggio:
  - Armi pesanti (Spadone) vs leggere (Stocco): influiscono su nuoto, cunicoli stretti e travestimenti furtivi.
  - Oggetti di utilità (es. Corda da Viaggio): permettono di superare baratri e calarsi da altezze senza subire danni fatali.
- **Fail Forward vs Sudden Death:**
  - Evitare le morti istantanee prive di indizi o possibilità di reazione ("Save-or-Die").
  - Quando l'eroe compie una scelta azzardata (es. arrendersi a una pattuglia o attraversare un ponte pericolante), trasformare il fallimento in una complicazione narrativa:
    - *Resa alle guardie:* invece di Game Over istantaneo, l'eroe viene gettato nelle Prigioni (Nodo 21), dove può unirsi ai ribelli e tentare l'evasione.
    - *Crollo del ponte:* una caduta frenata sulle cenge (perdita di PF) che devia il percorso verso i sotterranei (Nodo 4).
  - L'indovinello del bardo: sbagliare la risposta non uccide, ma forza una fuga rocambolesca sui tetti.

---

## 3. Gestione dell'Economia e dell'Inventario
- **Economia Attiva dell'Oro:** Ogni moneta raccolta deve avere uno scopo:
  - Ristoro e guarigione nelle locande (es. Locanda del Cinghiale Cieco).
  - Corruzione di guardie e sentinelle per evitare scontri o sbloccare scorciatoie.
- **Reliquie con Poteri Attivabili su Richiesta:**
  - Le reliquie ancestrali non devono sprecare le loro proprietà curative al momento della raccolta se l'eroe è a piena salute.
  - Il potere curativo (es. *Luce del Prisma* per il Prisma di Stella) può essere attivato dal giocatore quando ne ha reale necessità dalla scheda del personaggio o durante il viaggio.
  - Il Sigillo dei Sovrani conferisce vigore massimo o benedizione permanente; l'Egida d'Argento offre protezione passiva leggendaria.
- **Utilizzo Pratico degli Oggetti:**
  - Nessun oggetto iniziale (es. *Corda da Viaggio*) deve rimanere inerte nello zaino: deve avere almeno 2 occasioni contestuali in cui il suo impiego risolve un dilemma o apre un percorso alternativo.

---

## 4. Bilanciamento del Combattimento e Fairness
- **Tiro dei Dadi (2d6 vs 2d6):**
  - Mostri standard infliggono danno con il 6.
  - Il Boss Finale (Malakor l'Ombromante), essendo un potente stregone oscuro, colpisce con 5 e 6 (`enemy_hits_on_5: true`).
  - La presenza di Roland al fianco dell'eroe riduce di 1 i danni nemici a round (`hero_buff: true`), fornendo una ricompensa tangibile per averlo salvato.
  - Se l'eroe è costretto ad affrontare Malakor da solo (dopo aver ucciso Roland al Nodo 28), deve poter trovare un ristoro o pozione tra le spoglie per non arrivare allo scontro finale con 1-2 PF.

---

## 5. Illustrazioni e Coerenza Visiva
- **Scena di Caduta/Morte Universale (Nodo 34 e 37):**
  - **Sfondo Neutro e Atmosferico:** La scena di sconfitta non deve mai mostrare architetture distintive specifiche (es. colonne di castello, volte di cattedrale, sale del trono o formazioni carsiche), poiché l'eroe può cadere in battaglia in luoghi eterogenei (caverne, vicoli, bastioni, torri). Lo sfondo deve essere puramente atmosferico, composto da nebbia, fumo e ombre calanti.
  - **Dinamismo di Genere/Avatar:** L'illustrazione della caduta si adatta dinamicamente all'avatar e genere selezionato all'inizio dell'avventura (`elyan`, `elysia`, `elen`), garantendo piena immedesimazione per ogni eroe.

