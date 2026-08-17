---
name: knowledge-pill
description: Distilla una competenza ricorrente — non conoscenza di dominio — in un file operativo denso salvato in 00_context/knowledge_pills/, da richiamare invece di rispiegare. Usare per "fammi una pillola su X", "crea una cartuccia", o quando ci si accorge di aver rispiegato la stessa cosa più volte in sessioni diverse.
---

# Knowledge pill

*v2.0*

Obiettivo: smettere di ricostruire lo stesso ragionamento a ogni sessione. Una pillola è competenza in prestito: si richiama, si applica, si mette via.

## Passi

1. **Verifica che sia davvero una pillola** — un metodo riutilizzabile a prescindere dall'argomento (struttura di copywriting, metodo di vendita, modo di condurre un'intervista), non ricerca o dati su un dominio specifico (quello vive in `02_wiki/`). Test: "resta utile se cambio completamente progetto o cliente?" Sì → pillola. No → wiki. Se esiste già una pillola vicina, proporre di estenderla invece di crearne una seconda.
2. **Raccogli le fonti** — documenti, ricerche, trascrizioni, appunti reali. Una pillola scritta a memoria vale quanto un'opinione. Se le fonti non ci sono, dirlo e fermarsi invece di riempire di generalità.
3. **Distilla, non riassumere** — un riassunto racconta cosa dice la fonte, una pillola dice cosa fare. Struttura del file: titolo, 1-2 righe su a cosa serve e quando richiamarla, `## Quando si applica` (situazioni concrete, almeno un esempio legato al lavoro reale dell'utente), `## Come si fa` (metodo denso, niente introduzioni o contesto storico), `## Errori tipici` (solo quelli che costano davvero), footer `**Fonti:**`.
4. **Salva e indicizza** — `00_context/knowledge_pills/<nome>.md` in kebab-case. Voce nell'indice della cartella nella stessa operazione: una pillola non indicizzata non verrà mai richiamata.
5. **Verifica di chiarezza** — prima di chiudere, spiega a parole tue (non incollando il file) cosa fa la pillola, quando si applica, come si attiva, con un esempio legato al contesto reale. Se l'utente non ha capito, il file va rivisto, non solo rispiegato a voce.
6. **Dichiara come si usa** — chiudi con la frase esatta per richiamarla in futuro (es. "leggi la pillola su X e applicala a questo testo").

## Regole dure

- Una pillola sostituisce un ragionamento ripetuto, non un documento di riferimento. Oltre le 2-3 pagine, probabilmente sono due pillole.
- Le pillole invecchiano: quando una si rivela imprecisa, si corregge subito invece di aggirarla in conversazione.
- **L'attivazione non è mai automatica.** Una pillola resta muta finché l'utente, o una skill che la richiama esplicitamente, non chiede di leggerla e applicarla. Notare un pattern che meriterebbe una pillola durante una conversazione è proattività di conversazione (Regola 9 di `CLAUDE.md`), non un meccanismo della pillola stessa.
