---
name: project-kickoff
description: Apre un progetto nuovo nel secondo cervello — cartella, CLAUDE.md, memory.md, riga in tabella "Progetti Attivi" e voce nell'indice, garantendo che sia subito raggiungibile dal Router. Usare per "apri un progetto nuovo", "kick-off progetto", o ogni volta che nasce un nuovo filone di lavoro in 10_projects/.
---

# Project kickoff

*v2.0*

Obiettivo: evitare che un progetto nasca senza `CLAUDE.md`/`memory.md` o senza riga in tabella root — i due buchi più frequenti.

## Passi

1. **Verifica che non esista già** — Grep/Glob su nome, sinonimi, dominio. Se qualcosa di vicino copre già lo stesso bisogno, proporlo prima di creare da zero.
2. **Valuta il peso** — una domanda sola: questo progetto accumulerà nel tempo decisioni e stato che servirà rileggere tra una settimana?
   - No (routine che produce solo output ripetuti, niente decisioni da rileggere) → salta i Passi 3-4, basta il file operativo con 2 righe in testa. Se così leggero, valutare se appartenga a `03_skills/` come procedura invece che a `10_projects/` come progetto.
   - Sì (clienti, canali attivi, decisioni che cambiano) → schema pieno.
3. **Cartella + CLAUDE.md** — copia `99_system/templates/claude-template.md` in `10_projects/<nome>/CLAUDE.md`: ruolo in una riga, perimetro (cosa entra, cosa no e dove va il resto), struttura interna solo se non ovvia, regole ereditate da root esplicitate.
4. **memory.md** — copia `99_system/templates/memory-template.md` in `10_projects/<nome>/memory.md`, compila l'header, cancella le sezioni che restano vuote.
5. **Riga in tabella "Progetti Attivi"** di `memory.md` root — path corretto, stato "Attivo", prossimo step in una frase. Stessa sessione, è macro. Vale anche per i progetti leggeri del Passo 2.
6. **Voce in `10_projects/projects_index.md`** — stessa operazione. Senza questa il progetto esiste su disco ma è irraggiungibile dalla cascata (Regola 1). Due scritture distinte: la tabella porta lo stato, l'indice la raggiungibilità.
7. **`archive.md` — solo quando serve.** Non crearlo al kick-off: nasce alla prima volta che uno stato in `memory.md` viene sostituito, non aggiunto. Non si applica ai progetti leggeri.

## Regole dure

- Kick-off sempre nella chat root, mai in una chat di progetto.
- Se il progetto nasce spostando o fondendo contenuto già esistente altrove, non basta l'impalcatura: applicare anche "link sempre, mai path a testo libero" e verificare (grep) ogni riferimento al vecchio path.
- Se non è chiaro in una frase cosa fa il nuovo progetto, si chiede prima di procedere.
