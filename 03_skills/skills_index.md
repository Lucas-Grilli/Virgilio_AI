# skills — indice

> Le skill del sistema, divise per natura in **atomiche/** e **flusso/**. Una cartella per skill, `<nome>/SKILL.md` con un blocco YAML in testa (nome e descrizione). Questa è la fonte leggibile e modificabile. Claude Code non scansiona `03_skills/`: scopre le skill da `.claude/skills/`, che nel pacchetto è già una copia pronta delle stesse cartelle e resta **piatta** (è la posizione di esecuzione, non di lettura) — su Claude Code funzionano quindi senza nessun passaggio dell'utente. Su claude.ai/app, che non legge `.claude/`, si installano copiando il contenuto di ogni `SKILL.md` in una nuova skill dalle impostazioni.
> Da qui parte la cascata verso tutto ciò che sta in `03_skills/`.

## Come si divide

- **Atomica** — un ingresso, un'uscita, nessuna decisione dentro. Non sa niente del contesto in cui gira, quindi è richiamabile da qualunque flusso. Porta dentro di sé le regole del proprio mestiere (limiti di spesa, parametri, controlli), così chi la usa non deve ricordarsele.
- **Di flusso** — una sequenza che ordina il lavoro e lo consegna a un verdetto dell'utente. Il suo valore è l'ordine e i cancelli, non il lavoro: punta alle atomiche invece di rispiegare come si fa ogni passaggio.

Il verdetto finale dell'utente **non** è ciò che distingue le due: quasi tutto finisce con una sua decisione. La linea è se l'unità è richiamabile da altri flussi.

**Criterio d'ingresso per una nuova atomica:** l'operazione è già stata fatta a mano almeno due volte, **oppure** porta una regola che, dimenticata, costa soldi o danni. Il secondo caso è il più importante: una regola che dipende dal ricordarsela non regge, va agganciata al passaggio che la esegue — e per un'operazione ripetibile quel passaggio è la skill.

**La descrizione è ciò che fa partire la skill**, non il nome: deve contenere le parole che usi nel momento del bisogno, non il nome tecnico di cosa fa. `"analisi dei numeri"` non combacia con niente; nel momento del bisogno si dice *"quanto traffico fa"*, *"che margine ho"*.

Una procedura che ha già una forma ma non ha ancora superato il criterio d'ingresso vive come cartella piatta `<nome>/` alla radice di `03_skills/`, senza finire in nessuna delle due: è l'incubazione.

## Atomiche

- **[knowledge-pill/SKILL.md](atomiche/knowledge-pill/SKILL.md)** — distilla una competenza ricorrente in un file operativo da richiamare, salvato in `00_context/knowledge_pills/`.
- **[dump-sessione/SKILL.md](atomiche/dump-sessione/SKILL.md)** — chiude un blocco di lavoro scrivendo una voce datata nel dump mensile.

## Di flusso

- **[onboarding/SKILL.md](flusso/onboarding/SKILL.md)** — primo avvio: conduce 3+1 domande, compila `memory.md`, apre il primo progetto. Si innesca dalla regola di primo avvio in `CLAUDE.md` quando il sistema è ancora vuoto: è l'unica che non va installata come skill a parte.
- **[bibliotecario/SKILL.md](flusso/bibliotecario/SKILL.md)** — smista `01_raw/` tra conoscenza e progetti: note atomiche nel wiki, cartelle e stato in `10_projects/`, indici aggiornati, originali archiviati in `_processed/` e contraddizioni segnalate invece che sovrascritte.
- **[project-kickoff/SKILL.md](flusso/project-kickoff/SKILL.md)** — apre un progetto nuovo: cartella, `CLAUDE.md`, `memory.md`, riga nella tabella dei progetti attivi e voce nell'indice.
- **[specializzazione/SKILL.md](flusso/specializzazione/SKILL.md)** — prima di assistere su un tema con letteratura propria, cerca evidenza esterna e la cristallizza in una pillola, invece di rispondere di intuito. Chiama [knowledge-pill](atomiche/knowledge-pill/SKILL.md).
- **[pulizia-sistema/SKILL.md](flusso/pulizia-sistema/SKILL.md)** — controlli meccanici sul sistema (link rotti, file orfani, path stale, naming, discrepanze di data) più, a cadenza periodica, il livello di giudizio: duplicazioni, scollamento regole↔realtà, pattern ripetuti nel feedback.

---
*Modificando una skill si modifica qui, in `03_skills/<natura>/<nome>/SKILL.md`: è l'unica fonte. Per farla arrivare a Claude Code va anche ricopiata sulla cartella gemella in `.claude/skills/<nome>/`, che resta piatta (non è un link automatico); per claude.ai/app si ricarica dalle impostazioni.*
