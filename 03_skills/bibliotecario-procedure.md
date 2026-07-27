---
name: Bibliotecario
description: Trasforma il materiale grezzo in 01_raw/ in note atomiche collegate nel wiki, aggiorna gli indici e archivia gli originali. Usare per "fai il bibliotecario", "svuota la inbox", "processa i raw".
---

# Bibliotecario — Procedura

*v1.0*

Fa il ponte tra le due zone della conoscenza: `01_raw/` è la inbox caotica, `02_wiki/` la biblioteca ordinata. Estrae valore dai file grezzi e lo trasforma in note atomiche, collegate e tracciabili.

**Obiettivo della procedura:** svuotare la inbox producendo conoscenza riutilizzabile, senza perdere la fonte e senza far esplodere il costo di lettura.

**Quando si attiva:** quando l'utente chiede di processare la inbox, o quando segnala di avere documenti e appunti accumulati da trasformare in conoscenza strutturata.

**Prerequisiti:**
- Materiale in `01_raw/`.

## Passaggi

### 1. Estrai il testo pulito
I file in `01_raw/` possono includere HTML pesante e PDF: leggerli interi brucia il contesto. Estrai prima il testo con gli strumenti disponibili nell'ambiente — un comando di conversione, o uno script breve scritto sul momento — e lavora sull'estratto.

I file `.txt`, `.md` e `.csv` sotto i 50 KB si leggono direttamente, senza passaggi intermedi.

Se un file non si lascia estrarre, lascialo dov'è, segnalalo nel report finale e prosegui con gli altri.

### 2. Identifica i concetti
Individua i concetti distinti che meritano una nota propria: framework, checklist, procedure, intuizioni, terminologia, dati.

**Atomicità — un concetto, un file.** Se un documento tocca più argomenti separati, produce più note. Meglio cinque note piccole che una enorme. La domanda che decide: "su cosa vorrò cercare questa informazione tra sei mesi?" — ogni risposta diversa è una nota diversa.

**Soglia di valore:** entra solo ciò che è azionabile, informativo o citabile. Restano fuori navigazione, piè di pagina, disclaimer, ripetizioni.

**Cosa non appartiene al wiki:** un modello di pensiero riutilizzabile a prescindere dall'argomento (una struttura di copywriting, un metodo di vendita) non è conoscenza di dominio — è un framework, e vive in `00_context/`. Segnalalo all'utente invece di crearlo qui.

**Contraddizioni:** se una fonte nuova smentisce — non integra — un'affermazione già scritta in una nota esistente, non sovrascrivere. Aggiungi un callout in cima alla sezione toccata e lascialo lì: la risoluzione spetta all'utente, non a te.

```
> [!contraddizione] [1 riga: cosa si contraddice]
> Vecchia affermazione ([fonte]): ...
> Nuova affermazione ([fonte]): ...
```

### 3. Crea le note
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

### 4. Aggiorna gli indici, entrambi i livelli
**Indice di categoria** (`02_wiki/<categoria>/index_<categoria>.md`) — qui va l'elenco vero: aggiungi la voce sotto il macro-argomento giusto (crealo se manca) e aggiorna l'intestazione, contatore note e data. Se l'indice della categoria non esiste ancora, crealo:

```markdown
# Master Index — <Categoria>

> N note | Ultimo aggiornamento: AAAA-MM-GG

### [Macro-argomento]
- [[nome-nota]] — descrizione in una riga
```

**Indice di root** (`02_wiki/wiki_index.md`) — solo due operazioni ammesse. Se hai creato una categoria nuova, aggiungi la sua riga sotto "Categorie". Se la categoria esisteva già, aggiorna solo il contatore delle note. L'indice di root non elenca mai i singoli file.

### 5. Archivia gli originali
Sposta in `01_raw/_processed/` i file elaborati con successo. Gli originali non si cancellano mai: è il backup che rende reversibile ogni digestione. Restano in `01_raw/` solo i file che hanno dato problemi.

### 6. Report finale
Conciso: note create e dove, file archiviati, file rimasti indietro con il motivo, indici aggiornati.

---

## Cose da Sapere
- Se il materiale in `01_raw/` appartiene chiaramente a un solo progetto e non è conoscenza di dominio generale, chiedi all'utente se preferisce archiviarlo nella cartella di quel progetto invece che nel wiki.

## Log Storico
- [2026-07-26] Creazione della procedura.
