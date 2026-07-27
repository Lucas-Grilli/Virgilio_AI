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
├── 03_skills/           ← procedure e skill
├── 10_projects/         ← progetti
└── 99_system/           ← manuali, template, feedback di sistema
```

Root contiene solo governo: nessun lavoro operativo. Ogni progetto in `10_projects/` replica il pattern dei tre file di governo.

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
| Procedura eseguibile globale | `03_skills/` |
| Procedura eseguibile di un solo progetto | cartella locale del progetto |
| Promemoria, cosa-da-fare | thread aperto in `memory.md`. Mai un file vuoto su disco |
| Decisione presa, stato cambiato | `memory.md` del livello giusto (+ `archive.md` se sostituisce) |

Test di ammissione al wiki: "resta utile se cambio progetto o cliente?" Sì → `02_wiki/`. No → resta materiale del progetto.

## 9. Procedure e skill

- **Procedura (`.md`):** si modifica direttamente, effetto immediato alla lettura successiva. Va usata di default.
- **Skill impacchettata:** la copia che si attiva è installata separatamente dal sorgente. Modificare il sorgente non aggiorna la copia installata: serve una reinstallazione esplicita. Un fix non reinstallato non esiste.
- Ciclo di aggiornamento di una skill: modifica sorgente → aggiorna changelog in testa → reinstalla → verifica che la versione attesa compaia alla prima esecuzione.

## 10. Glossario

| Termine | Significato |
|---|---|
| Router | Sezione di `CLAUDE.md` che dice dove vive ogni cosa |
| Propagazione | Portare un evento al livello giusto: micro → progetto, macro → root |
| Nota atomica | Un concetto, un file, con fonte citata e collegamenti |
| Macro / micro | Eventi che cambiano lo stato generale / dettagli interni a un progetto |
| Deploy di una skill | Reinstallare dopo aver modificato il sorgente |
