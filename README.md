# ⚔️ Le Cronache di Aldergàrdia: L'Ombra del Crepuscolo

> **Un librogame interattivo dark fantasy per browser ispirato ai grandi classici della letteratura a bivi (*Fighting Fantasy*, *Lupo Solitario*).**

---

### 🏛️ Crediti e Paternità dell'Opera
* **Storia, Worldbuilding e Progettazione Narrativa:** **Genny84**
* **Sistema di Gioco:** Motore originale a bivi con combattimento a dadi 2d6, gestione dello stato, economia dell'oro e reliquie ancestrali.
* **Stile Visivo:** Illustrazioni xilografiche d'epoca su pergamena medievale con rendering adattivo in base al personaggio.

---

### 📖 Sinossi
Cinque anni dopo il colpo di stato in cui il tiranno **Malakor l'Ombromante** assassinò il Re d'Aldergàrdia gettando il regno nell'oscurità, il giovane erede esule fa ritorno alla roccaforte avito. Tra passaggi segreti, sotterranei dimenticati, mercati presidiati e antiche reliquie, dovrai farti strada fino alla Sala del Trono per compiere il tuo destino o perire nelle ombre.

---

### 🎲 Caratteristiche del Progetto
* **Architettura a Grafo Avanzata:** Oltre 40 nodi narrativi interconnessi senza vicoli ciechi ingiusti (*fail-forward* design).
* **Tre Protagonisti Selezionabili:**
  * **Elyan** (Principe Ramingo)
  * **Elysia** (Principessa Esule)
  * **Elen** (Erede Guardiano)
  Con accordi di genere dinamici nei testi e **illustrazioni di morte/sconfitta personalizzate** per ciascun eroe.
* **Combattimento Tattico 2d6:**
  * Round dinamici a turni con tiro dadi animato, colpi critici (doppio 6) e modalità *Combattimento Rapido*.
  * Armi con modificatori e ingombro (*Spadone del Crociato*, *Stocco Reale*, *Ascia da Guerra*, *Spada dei Raminghi*).
  * Il Boss Finale (Malakor) attacca con magia oscura e infligge danno su 5 e 6.
* **Economia Attiva e Risorse:**
  * Gestione di Monete d'Oro per rifocillarsi in locanda (+PF) o corrompere le sentinelle ai posti di blocco.
  * Uso tattico della *Corda da Viaggio* per superare baratri e calarsi da muraglie.
  * **Reliquie Ancestrali con Poteri Attivabili:**
    * 💎 *Prisma di Stella:* Guarigione su richiesta (+5 PF quando serve, con protezione da spreco a salute massima).
    * 💍 *Sigillo dei Sovrani:* Potenziamento permanente di Resistenza Massima (+2 PF Max).
    * 🛡️ *Egida d'Argento:* Difesa passiva leggendaria (-1 danno sui colpi pesanti nemici).
* **Tre Finali Alternativi:**
  * 🌟 **Finale Ottimo:** Rinascimento di Aldergàrdia (Roland salvato e Malakor annientato).
  * 👑 **Finale Amaro:** Il Trono Solitario (Roland caduto, il regno è libero ma a caro prezzo).
  * 🛡️ **Finale Buono II:** L'Alleanza dell'Alba.
* **PWA & Mobile-First:** Single Page Application ultra-leggera, nessun framework pesante, salvataggio automatico progressi in `localStorage` e precaricamento asincrono delle illustrazioni.

---

### 🛠️ Esecuzione Locale e Deploy
Essendo sviluppato in Vanilla JavaScript, HTML5 semantico e Tailwind CSS compilato:
1. Apri `index.html` direttamente in qualsiasi browser desktop o mobile.
2. Il deploy in produzione è gestito in modalità CI/CD continua tramite **Cloudflare Pages**.
