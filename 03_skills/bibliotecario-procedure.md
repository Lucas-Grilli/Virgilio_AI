---
name: Bibliotecario
description: Smista il materiale grezzo in 01_raw/ tra conoscenza e progetti - crea note atomiche nel wiki, apre o alimenta le cartelle di progetto, aggiorna gli indici e archivia gli originali. Usare per "fai il bibliotecario", "svuota la inbox", "processa i raw", "ho buttato dentro della roba".
---

# Bibliotecario — Procedura

*v1.1*

Fa il ponte tra il materiale grezzo e il sistema ordinato: `01_raw/` è la inbox caotica dove l'utente butta le cose senza pensarci, `02_wiki/` la biblioteca della conoscenza, `10_projects/` la casa dei progetti. Estrae valore dai file grezzi e lo manda dove serve.

**Obiettivo della procedura:** svuotare la inbox producendo conoscenza riutilizzabile *e* impalcatura di progetto, senza perdere la fonte e senza far esplodere il costo di lettura.

**Quando si attiva:** quando l'utente chiede di processare la inbox, o quando segnala di avere documenti e appunti accumulati da trasformare in qualcosa di strutturato.

**Prerequisiti:**
- Materiale in `01_raw/`.

## Passaggi

### 1. Estrai il testo pulito
I file in `01_raw/` possono includere HTML pesante e PDF: leggerli interi brucia il contesto. Estrai prima il testo con gli strumenti disponibili nell'ambiente — un comando di conversione, o uno script breve scritto sul momento — e lavora sull'estratto.

I file `.txt`, `.md` e `.csv` sotto i 50 KB si leggono direttamente, senza passaggi intermedi.

Se un file non si lascia estrarre, lascialo dov'è, segnalalo nel report finale e prosegui con gli altri.

### 2. Smista prima di digerire
Il materiale grezzo non è tutto della stessa natura, e mandarlo tutto nel wiki è l'errore più comune. Prima di creare qualsiasi cosa, dividi ciò che hai letto in tre mucchi:

- **Conoscenza di dominio** — resta utile anche se l'utente cambia progetto o cliente. Va nel wiki: Passaggi 3-5.
- **Materiale di progetto** — ha senso solo dentro un lavoro specifico: brief, decisioni, requisiti, stato, materiale di un cliente. Va in `10_projects/`: Passaggio 6.
- **Contesto personale** — come lavora l'utente, preferenze, vincoli stabili, framework di pensiero riutilizzabili a prescindere dall'argomento (una struttura di copywriting, un metodo di vendita). Va in `00_context/`, non nel wiki: segnalalo all'utente invece di crearlo tra le note.

Il test che decide tra i primi due: **"resta utile se cambio progetto o cliente?"** Sì → conoscenza. No → progetto.

Un singolo file può alimentare più mucchi: un dump di lavoro contiene spesso sia lo stato del progetto sia una tecnica riutilizzabile. Si divide, non si sceglie.

Se un mucchio è ambiguo, chiedi — una volta sola, con la tua proposta già pronta, non una domanda aperta per ogni file.

### 3. Identifica i concetti
Sul solo materiale finito nel mucchio "conoscenza". Individua i concetti distinti che meritano una nota propria: framework, checklist, procedure, intuizioni, terminologia, dati.

**Atomicità — un concetto, un file.** Se un documento tocca più argomenti separati, produce più note. Meglio cinque note piccole che una enorme. La domanda che decide: "su cosa vorrò cercare questa informazione tra sei mesi?" — ogni risposta diversa è una nota diversa.

**Soglia di valore:** entra solo ciò che è azionabile, informativo o citabile. Restano fuori navigazione, piè di pagina, disclaimer, ripetizioni.

**Contraddizioni:** se una fonte nuova smentisce — non integra — un'affermazione già scritta in una nota esistente, non sovrascrivere. Aggiungi un callout in cima alla sezione toccata e lascialo lì: la risoluzione spetta all'utente, non a te.

```
> [!contraddizione] [1 riga: cosa si contraddice]
> Vecchia affermazione ([fonte]): ...
> Nuova affermazione ([fonte]): ...
```

### 4. Crea le note
Un file `.md` per concetto, in `02_wiki/` o nella sottocartella tematica giusta. Verifica quali categorie esistono davvero prima di assumerlo; creane una nuova solo se il tema è genuinamente diverso da quelle presenti.

Nome file: `kebab-case-descrittivo.md`.

```markdown
# [Titolo del Concetto]

[Sintesi densa e diretta: punti chiave, numeri concreti, tecniche specifiche.
Solo ciò che è esplicitamente nella fonte — mai inferenze presentate come fatti.
Elenchi puntati invece di paragrafi lunghi.]

## Connessioni
- [[nota-correlata]]

---
**Fonte:** `nome-del-file-originale`
```

La sezione Connessioni si mette solo se esistono davvero note a cui questa si lega. Nessun link inventato per riempire.

### 5. Aggiorna gli indici del wiki, entrambi i livelli
**Indice di categoria** (`02_wiki/<categoria>/index_<categoria>.md`) — qui va l'elenco vero: aggiungi la voce sotto il macro-argomento giusto (crealo se manca) e aggiorna l'intestazione, contatore note e data. Se l'indice della categoria non esiste ancora, crealo:

```markdown
# Master Index — <Categoria>

> N note | Ultimo aggiornamento: AAAA-MM-GG

### [Macro-argomento]
- [[nome-nota]] — descrizione in una riga
```

**Indice di root** (`02_wiki/wiki_index.md`) — solo due operazioni ammesse. Se hai creato una categoria nuova, aggiungi la sua riga sotto "Categorie". Se la categoria esisteva già, aggiorna solo il contatore delle note. L'indice di root non elenca mai i singoli file.

### 6. Costruisci o alimenta i progetti
Sul materiale finito nel mucchio "progetto". Per ogni progetto riconosciuto nel materiale grezzo:

**Il progetto non esiste ancora** → esegui `project-kickoff-procedure.md`, che crea la cartella, le regole, il file di stato, la riga in tabella e la voce nell'indice. Non improvvisare una struttura di cartelle tua: la procedura di kick-off esiste per questo, e garantisce che il progetto nasca raggiungibile invece che orfano.

Poi versa il materiale nella cartella appena creata: quello che descrive lo stato attuale va nel `memory.md` del progetto, i documenti veri e propri restano come file dentro la cartella.

**Il progetto esiste già** → non ricrearlo. Aggiorna il suo `memory.md` con quello che il materiale grezzo dice di nuovo, e aggiungi i documenti nella sua cartella. Se il materiale sostituisce uno stato precedente invece di aggiungersi, il contenuto vecchio va in `archive.md` prima di essere sovrascritto.

**Riconoscere un progetto che non è mai stato dichiarato:** un dump può contenere un lavoro di cui l'utente non ti ha mai parlato. Se il materiale descrive qualcosa con un obiettivo, delle decisioni e uno stato che evolve, è un progetto anche se nessuno l'ha chiamato così. Proponilo all'utente prima di crearlo — un progetto nato per errore costa più di uno mancato.

**Quando fermarsi:** se dal materiale emergono più di tre progetti nuovi in un colpo solo, non aprirli tutti. Presenta l'elenco e fatti dire da quali partire.

### 7. Archivia gli originali
Sposta in `01_raw/_processed/` i file elaborati con successo. Gli originali non si cancellano mai: è il backup che rende reversibile ogni digestione. Restano in `01_raw/` solo i file che hanno dato problemi.

### 8. Report finale
Conciso, diviso per destinazione: note create e dove, progetti aperti o aggiornati, materiale mandato in `00_context/`, file archiviati, file rimasti indietro con il motivo, indici aggiornati.

---

## Cose da Sapere
- Lo smistamento del Passaggio 2 è ciò che rende questa procedura utile su un dump reale: l'utente butta dentro tutto quello che ha, senza dividerlo, e si aspetta che il sistema capisca dove va ogni cosa.
- Un file che alimenta sia il wiki sia un progetto si archivia comunque una volta sola, alla fine.

## Log Storico
- [2026-07-26] Creazione della procedura.
- [2026-08-04] Aggiunto lo smistamento a monte (Passaggio 2) e la costruzione dei progetti (Passaggio 6). Prima la procedura sapeva produrre solo note nel wiki, e il caso "l'utente scarica in `01_raw/` un dump legato ai suoi progetti" finiva in una domanda all'utente invece che in un'azione: il materiale di progetto non aveva nessuna strada per diventare impalcatura.
