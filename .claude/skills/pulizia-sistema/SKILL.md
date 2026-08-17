---
name: pulizia-sistema
description: Controlli meccanici sul secondo cervello (link rotti, file orfani, path stale, naming non conforme, discrepanze data macro/micro) più, a cadenza periodica, il livello di giudizio (duplicazioni di contenuto, scollamento regole↔realtà, pattern ripetuti nel feedback). Usare per "fai pulizia sistema", "controlla il sistema", "verifica il vault".
---

# Pulizia sistema

*v2.0*

Obiettivo: intercettare rotture strutturali con un controllo ripetibile invece di scoprirle per caso, più il giudizio che il solo controllo meccanico non vede. Segnala, non corregge — le correzioni si decidono con l'utente dopo il report.

## Passi

**Meccanici (1-7, deterministici — nessuna interpretazione, solo confronto tra file):**

1. **Data reale con un comando** — mai dedotta dalle ultime entry dei file.
2. **Mappa la struttura** — Glob (non Read) di tutti i `CLAUDE.md`, `memory.md`, `archive.md`, `index_*.md`/`*_index.md` del sistema, ogni livello di `10_projects/` incluso. Solo struttura, non contenuto: è la lista su cui girano i controlli sotto.
3. **Link rotti o ambigui** — per ogni wikilink `[[ ]]` o link a path nei file mappati: verifica (Glob sul nome file) che risolva a esattamente un file. Segnala sia i link a niente sia gli ambigui (più file con lo stesso nome).
4. **File orfani** — file dentro una cartella indicizzata (`02_wiki/*`, `03_skills/`, ecc.) che non compare in nessun index della sua categoria: irraggiungibile dalla cascata anche se esiste su disco (Regola 1 di `CLAUDE.md`).
5. **Path stale** — riferimenti a path che non esistono più su disco (cartelle rinominate, spostate, appiattite). Confronta i path scritti nei file con l'albero reale.
6. **Naming non conforme** — file che non rispettano le convenzioni correnti (kebab-case per note wiki, doppio livello `*_index.md`/`index_<categoria>.md` per cartelle — elenco completo in `99_system/manuale-operativo.md`).
7. **Discrepanze macro/micro** — per ogni progetto in tabella "Progetti Attivi" di `memory.md` root: confronta la data "Ultimo aggiornamento" con quella nel `memory.md` del progetto. Ogni mismatch è un candidato di propagazione mancata.

**Di giudizio (8-10, richiedono lettura e interpretazione — solo nel giro periodico, non a ogni esecuzione):**

8. **Duplicazioni di contenuto** — stesso fatto scritto in più di un `memory.md` invece che in un solo posto con puntatore altrove (Regola 4 di `CLAUDE.md`).
9. **Scollamento regole↔realtà** — confronta le regole scritte (`CLAUDE.md` a ogni livello, `99_system/manuale-operativo.md`) con la pratica osservata in `00_context/dump/` (ultimo periodo) e nei `memory.md`. Segnala dove una regola non si segue più, o dove la pratica ha superato la regola senza che questa sia stata aggiornata.
10. **Pattern ripetuti** — legge `00_context/dump/` (ultimo periodo) e `99_system/feedback_secondo_cervello.md`: correzioni o feedback che tornano più volte sullo stesso punto sono candidati a diventare regola nuova in `CLAUDE.md`, invece di restare promemoria sparso.

**Report finale** — elenco per categoria (link rotti, orfani, path stale, naming, discrepanze data, duplicazioni, scollamento regole↔realtà, pattern ripetuti), ognuno con file e riga coinvolti. Nessuna modifica applicata in questa esecuzione.

## Regole dure

- **Segnala, non corregge.** Le correzioni si decidono con l'utente dopo il report, passaggio per passaggio o in blocco — mai applicate d'iniziativa.
- **Su richiesta → solo Passi 1-7.** Il giro di giudizio (8-10) ha senso a cadenza periodica: pesa di più, richiede interpretazione e non solo confronto.
- **Prerequisito:** l'intera cartella del sistema (root) montata, non un progetto specifico. Per i Passi 8-10 servono anche `00_context/dump/` e `99_system/feedback_secondo_cervello.md` raggiungibili.
