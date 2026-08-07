---
name: knowledge-pill
description: Distilla una competenza ricorrente in un file operativo denso da richiamare quando serve, salvato in 00_context/knowledge_pills/. Usare per "fammi una pillola su X", "crea una cartuccia".
---

# Knowledge Pill — Procedura

*v1.1*

Trasforma una competenza che serve ripetutamente in un unico file operativo, da passare all'assistente quando quella competenza serve — invece di rispiegarla ogni volta.

**Obiettivo della procedura:** smettere di ricostruire lo stesso ragionamento a ogni sessione. Una pillola è competenza in prestito: si richiama, si applica, si mette via.

**Quando si attiva:** quando l'utente chiede una pillola su un tema, oppure quando ci si accorge di aver rispiegato la stessa cosa più volte in sessioni diverse.

**Prerequisiti:**
- Un tema definito e almeno una fonte reale da cui distillare — un documento, una ricerca, un manuale, un insieme di appunti.

## Passaggi

### 1. Verifica che sia davvero una pillola
Una pillola è un **metodo riutilizzabile a prescindere dall'argomento**: una struttura di copywriting, un metodo di vendita, un modo di condurre un'intervista. Se invece è ricerca o dati su un dominio specifico (un mercato, un algoritmo, un settore), non è una pillola: è conoscenza di dominio e vive in `02_wiki/`.

Il test: "questa cosa resta utile se cambio completamente progetto o cliente?" Sì → pillola. No → wiki.

Se esiste già una pillola vicina, proponi di estenderla invece di crearne una seconda.

### 2. Raccogli le fonti
Documenti, ricerche, trascrizioni, appunti. Una pillola scritta a memoria vale quanto un'opinione: serve materiale reale da cui distillare. Se le fonti non ci sono, dillo e fermati invece di riempire il file di generalità.

### 3. Distilla, non riassumere
Un riassunto racconta cosa dice la fonte. Una pillola dice **cosa fare**. La differenza è tra "l'autore sostiene che le obiezioni vanno anticipate" e "elenca le tre obiezioni più probabili prima di presentare il prezzo".

Struttura del file:

```markdown
# [Nome della competenza]

[1-2 righe: a cosa serve questa pillola e quando richiamarla.]

## Quando si applica
[Le situazioni concrete in cui questa competenza serve — non generiche: almeno un esempio legato al lavoro reale dell'utente, non solo la categoria astratta.]

## Come si fa
[Il metodo in passaggi o principi operativi. Densa: niente introduzioni,
niente ripetizioni, niente contesto storico. Solo ciò che si esegue.]

## Errori tipici
[Solo quelli che costano davvero — non un elenco esaustivo.]

---
**Fonti:** [da cosa è stata distillata]
```

### 4. Salva e indicizza
File in `00_context/knowledge_pills/`, nome in `kebab-case.md`. Aggiungi la voce nell'indice della cartella nella stessa operazione: una pillola non indicizzata non verrà mai richiamata, e una pillola mai richiamata non esiste.

### 5. Verifica di chiarezza
Prima di chiudere, spiega a parole tue — non incollando il file — cosa fa la pillola, quando si applica e quando si attiva, con un esempio legato al contesto reale dell'utente. Non è un passaggio pro forma: se l'utente dice di non aver capito, il file va rivisto (esempio troppo astratto, "quando si applica" non concreto), non solo rispiegato a voce.

### 6. Dichiara come si usa
Chiudi dicendo all'utente la frase esatta con cui richiamarla in una sessione futura — per esempio "leggi la pillola su X e applicala a questo testo". Una pillola vale solo se l'utente sa come innescarla.

---

## Cose da Sapere
- Una pillola sostituisce un ragionamento ripetuto, non un documento di riferimento. Se supera le due o tre pagine, probabilmente sono due pillole.
- Le pillole invecchiano: quando una viene usata e si rivela imprecisa, si corregge subito invece di aggirarla nella conversazione.
- **L'attivazione non è mai automatica.** Una pillola non si autoinvoca: resta muta finché l'utente (o una skill che la richiama esplicitamente) non chiede di leggerla e applicarla. Se durante una conversazione si nota un pattern ripetuto che meriterebbe una pillola (esistente o nuova), è proattività di conversazione (Regola 9 di CLAUDE.md) — non un meccanismo della pillola stessa.

## Log Storico
- [2026-07-26] Creazione della procedura.
- [2026-07-27] v1.1 — Aggiunto Passaggio 5 "Verifica di chiarezza" (l'utente non aveva capito cosa faceva/quando si applicava una pillola creata a partire da testo denso senza esempio concreto). Template: "Quando si applica" ora richiede un esempio legato al contesto reale, non solo la categoria astratta. Chiarito in "Cose da Sapere" che l'attivazione di una pillola non è mai automatica — solo su richiamo esplicito o proattività di conversazione.
