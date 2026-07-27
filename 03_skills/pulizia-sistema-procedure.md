---
name: Pulizia Sistema
description: Controlli meccanici sul secondo cervello: link rotti, file orfani, path stale, naming non conforme, date non propagate. Usare per "controlla il sistema", "fai pulizia", "verifica il vault".
---

# Pulizia Sistema — Procedura

*v1.0 — 2026-07-26: creazione, sostituisce l'idea parcheggiata "lint" (nome inglese) con un nome italiano.*

Scansiona il vault per rotture meccaniche e deterministiche — link rotti, orfani, path stale, naming non conforme, date propagate male — senza entrare nel merito organizzativo.

**Obiettivo della procedura:** intercettare rotture strutturali con un controllo ripetibile, invece di scoprirle per caso.

**Quando si attiva:** on demand ("fai pulizia sistema", "controlla il vault"), oppure richiamata come prima fase da una procedura di revisione più ampia.

**Prerequisiti:**
- L'intera cartella `Virgilio/` (root) montata — non un progetto specifico.
- Nessun framework di riferimento necessario.

## Passaggi

### 1. Verifica la data
`date` reale via comando, mai dedotta dalle ultime entry dei file — serve a datare ogni voce del report.

### 2. Mappa la struttura
Glob (non Read) di tutti i `CLAUDE.md`, `memory.md`, `archive.md`, `index_*.md`/`*_index.md` del vault, a ogni livello di `10_projects/` incluso. È la lista su cui girano i controlli sotto — solo struttura, non contenuto.

### 3. Link rotti o ambigui
Per ogni wikilink `[[ ]]` o link a path incontrato nei file mappati: verifica (Glob sul nome file) che risolva a esattamente un file. Segnala sia i link a niente sia gli ambigui (più file con lo stesso nome nel vault).

### 4. File orfani
File dentro una cartella indicizzata (`02_wiki/*`, `03_skills/`, ecc.) che non compare in nessun index della sua categoria — irraggiungibile dalla cascata anche se esiste su disco (Regola 1 di `CLAUDE.md`). Segnala.

### 5. Path stale
Riferimenti a path che non esistono più su disco (cartelle rinominate, spostate, flattenate). Confronta i path scritti nei file con l'albero reale (`ls`/Glob).

### 6. Naming non conforme
File che non rispettano le convenzioni correnti (kebab-case per note wiki, doppio livello `*_index.md`/`index_<categoria>.md` per cartelle, ecc. — l'elenco vive in `99_system/manuale-operativo.md` §6).

### 7. Discrepanze macro/micro (date)
Per ogni progetto in tabella "Progetti Attivi" di `memory.md` root: confronta la data "Ultimo aggiornamento" con quella nel `memory.md` del progetto stesso. Segnala ogni mismatch — candidato di propagazione mancata.

## Report finale
Elenco per categoria (link rotti, orfani, path stale, naming, discrepanze data), ognuno con file e riga coinvolti. **Nessuna modifica applicata in questa esecuzione — solo segnalazione.** Le correzioni si decidono con l'utente, passaggio per passaggio o in blocco.

---

## Cose da Sapere
- Solo controlli meccanici e deterministici, zero giudizio organizzativo: valutazioni come "questa cartella sta crescendo, valuta un indice dedicato" o "questi progetti sono fermi" non appartengono a questa procedura.
- Segnala, non corregge: le correzioni si decidono con l'utente dopo il report.

## Log Storico
- 2026-07-26 Creazione della procedura.
