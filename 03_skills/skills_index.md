# skills — indice

> Le procedure del sistema: una cartella per skill, `<nome>/SKILL.md` con un blocco YAML in testa (nome e descrizione). Questa è la fonte leggibile e modificabile. Claude Code non scansiona `03_skills/`: scopre le skill da `.claude/skills/`, che nel pacchetto è già una copia pronta delle stesse sei cartelle (verificato a freddo il 07/08) — su Claude Code funzionano quindi senza nessun passaggio dell'utente. Su claude.ai/app, che non legge `.claude/`, si installano copiando il contenuto di ogni `SKILL.md` in una nuova skill dalle impostazioni.
> Da qui parte la cascata verso tutto ciò che sta in `03_skills/`.

## Procedure

- **[onboarding/SKILL.md](onboarding/SKILL.md)** — primo avvio: conduce 3+1 domande, compila `memory.md`, apre il primo progetto. Si innesca dalla regola di primo avvio in `CLAUDE.md` quando il sistema è ancora vuoto: è l'unica che non va installata come skill a parte.
- **[bibliotecario/SKILL.md](bibliotecario/SKILL.md)** — smista `01_raw/` tra conoscenza e progetti: note atomiche nel wiki, cartelle e stato in `10_projects/`, indici aggiornati, originali archiviati in `_processed/` e contraddizioni segnalate invece che sovrascritte.
- **[project-kickoff/SKILL.md](project-kickoff/SKILL.md)** — apre un progetto nuovo: cartella, `CLAUDE.md`, `memory.md`, riga nella tabella dei progetti attivi e voce nell'indice.
- **[knowledge-pill/SKILL.md](knowledge-pill/SKILL.md)** — distilla una competenza ricorrente in un file operativo da richiamare, salvato in `00_context/knowledge_pills/`.
- **[pulizia-sistema/SKILL.md](pulizia-sistema/SKILL.md)** — controlli meccanici sul sistema: link rotti, file orfani, path stale, naming, discrepanze di data.
- **[dump-sessione/SKILL.md](dump-sessione/SKILL.md)** — chiude un blocco di lavoro scrivendo una voce datata nel registro di automiglioramento.
- **[feedback-sistema/SKILL.md](feedback-sistema/SKILL.md)** — scrive subito in `99_system/feedback_secondo_cervello.md` quando emerge un problema della struttura del sistema.

---
*Modificando una procedura si modifica qui, in `03_skills/<nome>/SKILL.md`: è l'unica fonte. Per farla arrivare a Claude Code va anche ricopiata sulla cartella gemella in `.claude/skills/<nome>/` (non è un link automatico); per claude.ai/app si ricarica dalle impostazioni.*
