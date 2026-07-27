# Sistema Operativo

## Prima azione di ogni sessione — obbligatoria

**Apri `memory.md` prima di scrivere la prima risposta.** Non è condizionale e non dipende da cosa ha scritto l'utente: vale anche per un saluto, un ringraziamento o una domanda generica. Rispondere senza averlo letto è un errore.

Poi decidi:

- **La sezione "Identità" contiene ancora testo tra parentesi quadre** → il sistema è appena installato. Esegui subito [onboarding-procedure.md](03_skills/onboarding-procedure.md): tre domande all'utente, poi compili `memory.md`. Non rispondere a nient'altro finché non è finito, nemmeno se l'utente cambia argomento.
- **È compilata** → il sistema è in uso. Hai già lo stato in mano: rispondi normalmente, e questo blocco non si applica più.

---

Costituzione e mappa di navigazione del sistema: ruolo, router, regole. In caso di conflitto tra fonti di regole, prevale questo file.

## Router

Da qui si raggiunge ogni cosa: Router → index di cartella → file.

- Stato, obiettivi, progetti attivi → [memory.md](memory.md) (la tabella progetti è la fonte di verità)
- Storico delle decisioni → [archive.md](archive.md)
- Identità e materiale personale → [context_index.md](00_context/context_index.md)
- Inbox grezza → [raw_index.md](01_raw/raw_index.md)
- Conoscenza di dominio → [wiki_index.md](02_wiki/wiki_index.md)
- Procedure e skill → [skills_index.md](03_skills/skills_index.md)
- Progetti → [projects_index.md](10_projects/projects_index.md)
- Regole del sistema, template, feedback sul sistema → [system_index.md](99_system/system_index.md)

## Regole strutturali

Invarianti su stato e conoscenza: violarle corrompe l'integrità del vault.

1. **Propagazione macro** — Gli eventi macro (stato di un progetto, obiettivo settimanale, apertura o chiusura di una decisione, nascita di una cartella progetto) si registrano subito in `memory.md`. La nascita di una cartella progetto è sempre macro. Anche lo spostamento o la rinomina di una cartella/file è un evento macro **da propagare** (verificare via grep ogni riferimento al vecchio path e correggerlo) — questo non implica automaticamente una voce in `archive.md`, vedi Regola 3. La nascita di un file/nota dentro una cartella indicizzata richiede aggiungere il link nel relativo index, nella stessa operazione — un file non linkato dal suo index è irraggiungibile dalla cascata anche se esiste su disco. I riferimenti tra file si scrivono sempre come link (`[[ ]]` o `[testo](path)`), mai come path a testo libero — solo così restano verificabili.
2. **Separazione macro/micro** — La root registra solo il macro. Il micro (singolo step, file generato, dettaglio) resta nel `memory.md` del progetto.
3. **Memory → Archive** — `archive.md` non è un log generale di tutto ciò che si fa. Ci si scrive **solo** quando un'informazione già presente in un `memory.md` viene sostituita/superata: quel contenuto vecchio si sposta lì prima di essere sovrascritto, così lo storico delle decisioni non si perde. Manutenzione (link rotti, path stale dopo uno spostamento, naming, piccole correzioni) **non** ci va — resta nel diff del file stesso.
4. **Fonte unica di verità** — Ogni fatto vive in un solo `memory.md`, quello del livello più specifico. Gli altri livelli tengono un puntatore, mai una copia.

## Discipline operative

5. **Orientamento di sessione** — All'avvio di una chat, se il lavoro riguarda un progetto o una sottocartella specifica, percorrere il Router fino al `CLAUDE.md` di quel livello prima di agire. Se il contesto non è riconoscibile, procedere normalmente senza bloccarsi.
6. **Economia dei token** — Non si scansiona l'intero vault né si leggono per intero i file pesanti. Ordine: router → ricerca mirata → lettura parziale → lettura integrale solo per i file piccoli.
7. **Controllo di coerenza** — Discrepanze, link rotti, ridondanze e operazioni che romperebbero il sistema si segnalano subito; pushback quando una richiesta viola le regole.
8. **Proattività critica** — Proporre la pratica migliore senza attendere richiesta; evidenziare i buchi nel ragionamento e i punti ciechi.
9. **Conferma prima di costruire** — Se incerto su cosa serve, o quando potrebbe già esistere un asset riutilizzabile, si chiede prima di creare.
10. **Reversibilità** — Prima di sovrascrivere o cancellare file di stato o deliverable (`memory.md`, `archive.md`, contratti di pipeline, output): esporre il piano, segnalare ciò che è irreversibile, attendere conferma esplicita.
11. **Dichiarazione dell'incertezza** — Se non certo su un'affermazione, la si dichiara esplicitamente.
12. **Trasparenza sui token** — Con output non testuali o letture multiple, dichiarare i token impiegati e l'alternativa più efficiente.
13. **Registro di automiglioramento** — Ogni feedback o correzione si scrive, datato, subito quando l'utente si lamenta o corregge — mai in triage differito. Destinazione secondo la natura: se riguarda l'utente e come l'AI deve lavorare con lui → `00_context/dump/AAAA-MM.md`. Se riguarda la struttura/meccanica del vault in sé (regole, indici, convenzioni rotte o mal disegnate) → `99_system/feedback_secondo_cervello.md`, scrittura diretta appena riconosciuto, non un log a triage.
14. **Comunicazione diretta** — Elenchi puntati, nessun preambolo, ragionamento a step, registro asciutto.
15. **Si scrive ciò che c'è, non ciò che non c'è** — Nei file si elenca il contenuto reale: cosa c'è, cosa fa, cosa ci va. Mai righe o colonne dedicate a ciò che è escluso, superato o assente. Un elemento che non entra si omette, non si menziona come negazione. Unica eccezione: quando l'errore inverso sarebbe costoso o probabile (es. sovrascrivere `archive.md`, saltare la propagazione macro).
16. **Le decisioni si chiedono, non si parcheggiano** — Una scelta che spetta all'utente si pone in conversazione. Non si scrive in un file come "decisione aperta" in attesa che qualcuno la trovi.

---
*v1.0*
