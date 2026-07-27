---
name: Kick-off Progetto
description: Apre un progetto nuovo nel secondo cervello: cartella, regole, file di stato, riga in tabella e voce nell'indice. Usare quando si vuole iniziare un nuovo progetto o filone di lavoro.
---

# Nascita di un Progetto — Procedura

*v1.0 — 2026-07-24: creazione.*

Crea lo scheletro minimo di governo per un nuovo progetto in `10_projects/`, in chat root, garantendo che sia subito raggiungibile dal Router e coerente con le regole di propagazione.

**Obiettivo della procedura:** evitare che un progetto nasca senza `CLAUDE.md`/`memory.md` (visto su più progetti nel vault) o senza riga in tabella root — i due buchi osservati più spesso.

**Quando si attiva:** trigger manuale, ogni volta che nasce un nuovo progetto in `10_projects/` — sempre in chat root, mai in una chat di progetto.

**Prerequisiti:**
- Sessione aperta in chat root (kick-off sempre lì, mai in una chat di progetto).
- Chiaro in una frase cosa fa il nuovo progetto — se non lo è, chiedere prima di procedere.

## Passaggi

### 1. Verifica che non esista già
Cerca (Grep/Glob su nome, sinonimi, dominio) se un progetto o una sottocartella esistente copre già lo stesso bisogno. Se trovi qualcosa di vicino, proponilo prima di creare da zero.

### 2. Valuta il peso
Una domanda sola: **questo progetto accumulerà nel tempo decisioni/stato che servirà rileggere tra una settimana?**
- No (una routine che produce solo output ripetuti, senza decisioni da rileggere) → salta i Passaggi 3-4: basta il file operativo stesso, con 2 righe in testa che spiegano cos'è. Se è così leggero, valuta se appartenga a `03_skills/` come procedura invece che a `10_projects/` come progetto.
- Sì (qualsiasi cosa con clienti, canali attivi, decisioni che cambiano) → prosegui con lo schema pieno.

### 3. Crea la cartella e il CLAUDE.md
Copia [[claude-template]] (`99_system/templates/claude-template.md`) in `10_projects/<nome>/CLAUDE.md`: ruolo in una riga, perimetro (cosa entra qui, cosa no e dove va a finire il resto), struttura interna solo se non ovvia, regole ereditate da root esplicitate (soprattutto: quando questa chat può scrivere su root per eventi macro).

### 4. Crea il memory.md
Copia [[memory-template]] (`99_system/templates/memory-template.md`) in `10_projects/<nome>/memory.md`, compila l'header e cancella le sezioni che restano vuote.

### 5. Riga in tabella "Progetti Attivi"
Aggiungi la riga in `memory.md` root: path corretto, stato "Attivo", prossimo step in una frase. Nella stessa sessione — è un evento macro, non si rimanda. Vale anche per i progetti "leggeri" del Passaggio 2 (no CLAUDE.md/memory.md): la riga in tabella root c'è comunque.

### 6. Voce in `10_projects/projects_index.md`
Aggiungi la voce nell'indice dei progetti, nella stessa operazione. Senza questa, il progetto esiste su disco ma è irraggiungibile dalla cascata Router → indice → file (Regola 1). Sono due scritture distinte e servono entrambe: la tabella del Passaggio 5 porta lo *stato*, l'indice porta la *raggiungibilità*.

### 7. archive.md — solo quando serve
Non crearlo al kick-off. Nasce alla prima volta che uno stato in `memory.md` viene sostituito, non aggiunto. Non si applica ai progetti leggeri (non hanno memory.md da sostituire).

## Risorse Opzionali
- [[claude-template]] — scheletro da copiare al Passaggio 3.
- [[memory-template]] — scheletro da copiare al Passaggio 4.
- [[manuale-operativo]] (`99_system/manuale-operativo.md`) — se serve ripassare le regole generali di nascita progetto.

## Cose da Sapere
- Se il progetto nasce spostando/fondendo contenuto già esistente altrove nel vault, questo non basta da solo: applicare anche la regola "link sempre, mai path a testo libero nei riferimenti" e verificare (grep) ogni riferimento al vecchio path prima di considerare la nascita conclusa.

## Log Storico
- [2026-07-24] Creazione della procedura. Nata da un caso reale: più progetti in `10_projects/` senza `CLAUDE.md`/`memory.md`, e una tabella "Progetti Attivi" con path non più esistenti su disco.
- [2026-07-26] Aggiunto il Passaggio 6 (voce in `projects_index.md`): mancava del tutto, quindi un progetto creato seguendo la procedura alla lettera nasceva orfano dall'indice pur avendo la riga di stato in root. Rilevato su un caso reale (`virgilio-v1`, creato lo stesso giorno e non indicizzato).
