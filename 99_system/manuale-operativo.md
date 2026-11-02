# Manuale Operativo — Struttura e Regole

> Solo regole e struttura: è il riferimento che le procedure di manutenzione usano per sapere cos'è "giusto" nel sistema.
> **Gerarchia:** se questo file contraddice `CLAUDE.md` root, vince `CLAUDE.md`.

---

## 1. Struttura

```
sistema/
├── CLAUDE.md            ← regole + router
├── memory.md            ← stato attuale
├── archive.md           ← storico
├── 00_context/          ← identità e materiale personale
├── 01_raw/              ← inbox grezza (+ _processed/)
├── 02_wiki/             ← conoscenza consolidata
├── 03_skills/           ← skill globali, divise in atomiche/ e flusso/
├── 10_projects/         ← progetti
└── 99_system/           ← manuali, template, feedback di sistema
```

Root contiene solo governo: nessun lavoro operativo. Ogni progetto in `10_projects/` replica il pattern dei tre file di governo.

**Progetto o skill?** Due nature diverse, e confonderle è l'errore che costa di più:

- **Progetto** — ha un traguardo con cui si misura il successo, e finisce. Vive in `10_projects/`.
- **Skill** — l'esecuzione: un'operazione ripetibile che qualcuno invoca. Vive in `03_skills/`.

## 2. I tre file di governo

| File | Contiene | Cambia |
|---|---|---|
| `CLAUDE.md` | regole, router, perimetro | quasi mai |
| `memory.md` | stato attuale, thread aperti, prossimo passo | sempre |
| `archive.md` | ciò che è stato sostituito, con data | solo aggiunte |

- Le regole non contengono stato: se un'affermazione può scadere, va in `memory.md` e il router la referenzia.
- `archive.md` riceve solo informazioni che escono da un `memory.md` perché sostituite. Non è un log di manutenzione.
- `archive.md` nasce alla prima sostituzione, non al kick-off.

## 3. Propagazione

- **Micro** (uno step, un dettaglio): solo nel `memory.md` del progetto.
- **Macro** (stato di un progetto, obiettivo chiuso, decisione aperta/chiusa, nascita di un progetto, spostamento/rinomina di cartelle): subito anche in `memory.md` root, nella stessa sessione. Chi lavora nel progetto scrive lui stesso in root.
- Uno spostamento o una rinomina richiede di verificare (ricerca testuale) ogni riferimento al vecchio path e correggerlo.

## 4. Fonte unica di verità

Ogni fatto vive in un solo `memory.md`, quello del livello più specifico. Gli altri livelli tengono un puntatore, mai una copia.

## 5. Indice a due livelli

- Indice principale (`nomecartella_index.md`): solo categorie/sottocartelle, con descrizione e contatore. Mai elenchi di singoli file.
- Indice di categoria (`index_<tema>.md`, dentro la sottocartella): l'elenco dei file. Unica fonte di verità per quella categoria.
- Indice dedicato quando la sottocartella supera indicativamente 4-5 file o si annida ulteriormente; sotto quella soglia, link diretto dall'indice madre.
- Ogni file nato in una cartella indicizzata va aggiunto al relativo indice nella stessa operazione.

## 6. Convenzioni di scrittura

- **Scopo in apertura:** 1-2 righe in cima a ogni file che dicono a cosa serve.
- **Riferimenti come link,** mai path a testo libero. Se il nome non è univoco, aggiungere il path reale tra parentesi.
- **Descrizione ≠ storico:** entry di indice, passaggi di procedura e note operative dicono solo cosa è e cosa fa una cosa oggi. Date, rinomine e versioni vivono solo nel changelog/log storico del file.
- **Si scrive ciò che c'è, non ciò che non c'è:** nei file si elenca il contenuto reale — cosa c'è, cosa fa, cosa ci va. Mai righe o colonne dedicate a ciò che è escluso, superato o assente: un elemento che non entra si omette.
- **"Non fare X"** si scrive solo se l'errore inverso sarebbe costoso o probabile.
- **Date assolute** in ogni file che persiste.
- **Naming:** `kebab-case.md` per le note, `NN-nome.md` per stadi in sequenza, prefisso `_` per cartelle di servizio.
- **Schema esterno** (colonne di un foglio, campi di un CRM, risposta di un'API): verificarlo dal vivo a ogni esecuzione. Se non coincide e l'interpretazione è certa al 90%+, procedere e aggiornare il file; altrimenti fermarsi e chiedere.
- **Contraddizioni:** se una fonte nuova smentisce (non integra) un'affermazione già scritta, segnalarla inline con un callout e lasciarla lì. Non sovrascrivere: la risoluzione è dell'utente.

## 7. Economia di lettura

Ordine di costo crescente: router → ricerca mirata → lettura parziale → lettura integrale (solo file piccoli). Mai scansionare l'intero sistema. I file pesanti si distillano in markdown prima di entrare; le cartelle che li contengono lo dichiarano e puntano alle versioni distillate.

## 8. Dove va cosa

| Contenuto | Destinazione |
|---|---|
| Ritaglio o appunto grezzo | `01_raw/` |
| Ricerca distillata su un dominio | `02_wiki/<categoria>/` |
| Framework o metodo riutilizzabile ovunque | `00_context/` |
| Materiale specifico di un progetto | `10_projects/<progetto>/resources/` o `inputs/` |
| Deliverable finito | `10_projects/<progetto>/outputs/` |
| Operazione ripetibile senza decisioni dentro | `03_skills/atomiche/<nome>/` |
| Sequenza che ordina il lavoro e finisce in un verdetto | `03_skills/flusso/<nome>/` |
| Idea su cui non hai ancora lavorato | thread aperto in `memory.md`. Una cartella progetto nasce quando il lavoro inizia, non quando l'idea arriva |
| Procedura eseguibile di un solo progetto | cartella locale del progetto |
| Metodo per parlare con un servizio esterno | la guida delle connessioni esterne, in `99_system/` |
| Promemoria, cosa-da-fare | thread aperto in `memory.md`. Mai un file vuoto su disco |
| Decisione presa, stato cambiato | `memory.md` del livello giusto (+ `archive.md` se sostituisce) |

Test di ammissione al wiki: "resta utile se cambio progetto o cliente?" Sì → `02_wiki/`. No → resta materiale del progetto.

Ogni file che l'utente vorrà ritrovare ha anche la sua riga in «Dove trovi cosa», nel `memory.md` del progetto (Regola 23 di `CLAUDE.md`): la cartella dice dove sta un file, quella sezione lo fa ritrovare senza cercarlo.

## 9. Skill

**Ogni skill nasce dichiarando la propria natura**, prima che venga scritta una riga:

- **Atomica** — un ingresso, un'uscita, nessuna decisione dentro. Non sa niente del contesto in cui gira, quindi è richiamabile da qualunque flusso. Porta dentro di sé le regole del proprio mestiere (limiti di spesa, parametri, controlli), così chi la usa non deve ricordarsele.
- **Di flusso** — una sequenza che ordina il lavoro e lo consegna a un verdetto dell'utente. Il suo valore è l'ordine e i cancelli, non il lavoro: punta alle atomiche invece di rispiegare come si fa ogni passaggio.

Vive nella cartella corrispondente, `03_skills/atomiche/` o `03_skills/flusso/`, come cartella `<nome>/` con dentro `SKILL.md`.

**Criterio d'ingresso per una nuova atomica:** l'operazione è già stata fatta a mano almeno due volte, oppure porta una regola che, dimenticata, costa soldi o danni. Il secondo caso è il più importante: una regola che dipende dal ricordarsela non regge, va agganciata al passaggio che la esegue — e per un'operazione ripetibile quel passaggio è la skill.

**La descrizione è ciò che la fa partire**, non il nome: deve contenere le parole che l'utente usa nel momento del bisogno, non il nome tecnico di cosa fa.

**Installazione.** `03_skills/` è la fonte leggibile e modificabile; `.claude/skills/` è la posizione da cui l'assistente scopre le skill, e resta **piatta** anche quando la fonte è divisa in atomiche e flusso. Le due non sono collegate in automatico: dopo aver modificato una skill, la copia gemella va riallineata, altrimenti gira ancora la versione vecchia. Vale la regola che un fix non propagato non esiste.

**Procedura in incubazione.** Un metodo che ha già una forma ma non ha ancora superato il criterio d'ingresso vive come cartella `<nome>/` alla radice di `03_skills/`, fuori da entrambe. Diventa skill quando il criterio è soddisfatto, dichiarando la natura.

## 10. Glossario

| Termine | Significato |
|---|---|
| Router | Sezione di `CLAUDE.md` che dice dove vive ogni cosa |
| Propagazione | Portare un evento al livello giusto: micro → progetto, macro → root |
| Nota atomica | Un concetto, un file, con fonte citata e collegamenti |
| Macro / micro | Eventi che cambiano lo stato generale / dettagli interni a un progetto |
| Skill atomica | Un ingresso, un'uscita, nessuna decisione dentro: richiamabile da qualunque flusso |
| Skill di flusso | Una sequenza con cancelli, che finisce in un verdetto dell'utente |

---
*v1.2 — §8: ogni file da ritrovare ha la sua riga in «Dove trovi cosa» del `memory.md` del progetto (Regola 23).*
*v1.1 — §1: `03_skills/` divisa in atomiche/flusso, e la distinzione progetto/skill come prima cosa da stabilire. §8: destinazioni per skill atomica, skill di flusso e connessioni esterne; l'idea su cui non si è ancora lavorato non prende una cartella. §9 riscritta da capo: la natura della skill si dichiara prima di scriverla, criterio d'ingresso, la descrizione come innesco, e il modello sorgente/copia gemella reso esplicito. Glossario esteso.*
