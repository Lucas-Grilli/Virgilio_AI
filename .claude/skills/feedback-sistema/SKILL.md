---
name: feedback-sistema
description: Scrive subito nel registro dei problemi strutturali quando l'utente si lamenta di regole, indici o convenzioni del secondo cervello, e corregge la regola alla fonte.
---

# Feedback Sistema — Procedura

*v1.0 — 2026-07-26: creazione.*

Riconosce un reclamo o una correzione dell'utente sulla struttura/meccanica del vault in sé e lo scrive subito in `feedback_secondo_cervello.md` — nessun passaggio di triage o accumulo per revisione differita.

**Obiettivo della procedura:** far sì che un reclamo sulla meccanica del vault diventi voce scritta nella stessa interazione in cui viene espresso, invece di dipendere dalla memoria della chat.

**Quando si attiva:** l'utente si lamenta o corregge qualcosa che riguarda regole, indici, convenzioni o procedure del vault — non il lavoro di un progetto specifico (resta nel `memory.md` di quel progetto) e non una preferenza personale su di lui/come lavorare con lui (quello è [[dump-sessione-procedure]]).

**Prerequisiti:**
- Nessun framework di riferimento necessario.
- Saper distinguere il reclamo dal caso dump — v. `CLAUDE.md` Regola 14 e header di `feedback_secondo_cervello.md`.

## Passaggi

### 1. Classifica il reclamo
Riguarda la struttura/meccanica del vault (regole, indici, convenzioni, procedure)? Prosegui qui. Riguarda invece l'utente stesso o come l'AI deve lavorare con lui? Non è questa procedura — vai a [[dump-sessione-procedure]].

### 2. Scrivi la entry, subito
Verifica la data con un comando (mai dedotta). Aggiungi in `feedback_secondo_cervello.md`, formato: `- **AAAA-MM-GG:** [1-2 righe: cosa non va o manca, cosa è stato corretto]`.

### 3. Scrivi la regola nella sua sede naturale, nella stessa operazione
Se il reclamo richiede una regola nuova o modificata: `CLAUDE.md` se è un invariante strutturale, `99_system/manuale-operativo.md` se è una convenzione. Non basta loggare l'intenzione — la regola va scritta subito, altrimenti il reclamo si ripete.

### 4. Correggi i file già esistenti che violano la regola
Se sono pochi e individuabili, corretti nella stessa operazione. Se la portata è ampia (molti file, ricerca vault-wide), segnala l'entità prima di procedere — non lanciare una pulizia massiva senza conferma.

### 5. Fermati
Nessun'altra modifica oltre a quanto sopra senza una richiesta nuova.

## Risorse Opzionali
- [[manuale-operativo]] (`99_system/manuale-operativo.md`) — dove vivono le convenzioni corrette al Passaggio 3.
- `CLAUDE.md` root — dove vivono le regole strutturali corrette al Passaggio 3.

## Cose da Sapere
- Nessun passaggio di triage: riconoscimento e scrittura avvengono nella stessa interazione in cui il reclamo viene espresso.
- Resta procedura, non skill: non ha ancora il volume che giustifichi il pacchettamento (YAGNI).

## Log Storico
- 2026-07-26 Creazione della procedura.
