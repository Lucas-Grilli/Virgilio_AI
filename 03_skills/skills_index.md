# skills — indice

> Le procedure del sistema: file `.md` che si leggono ed eseguono. Ognuna porta in testa un blocco YAML con nome e descrizione, quindi si carica direttamente come skill dalle impostazioni dell'assistente per attivarsi da sola a comando.
> Da qui parte la cascata verso tutto ciò che sta in `03_skills/`.

## Procedure

- **[onboarding-procedure.md](onboarding-procedure.md)** — primo avvio: conduce 3+1 domande, compila `memory.md`, apre il primo progetto. Si innesca dalla regola di primo avvio in `CLAUDE.md` quando il sistema è ancora vuoto: è l'unica che non va caricata come skill.
- **[bibliotecario-procedure.md](bibliotecario-procedure.md)** — smista `01_raw/` tra conoscenza e progetti: note atomiche nel wiki, cartelle e stato in `10_projects/`, indici aggiornati, originali archiviati in `_processed/` e contraddizioni segnalate invece che sovrascritte.
- **[project-kickoff-procedure.md](project-kickoff-procedure.md)** — apre un progetto nuovo: cartella, `CLAUDE.md`, `memory.md`, riga nella tabella dei progetti attivi e voce nell'indice.
- **[knowledge-pill-procedure.md](knowledge-pill-procedure.md)** — distilla una competenza ricorrente in un file operativo da richiamare, salvato in `00_context/knowledge_pills/`.
- **[pulizia-sistema-procedure.md](pulizia-sistema-procedure.md)** — controlli meccanici sul sistema: link rotti, file orfani, path stale, naming, discrepanze di data.
- **[dump-sessione-procedure.md](dump-sessione-procedure.md)** — chiude un blocco di lavoro scrivendo una voce datata nel registro di automiglioramento.
- **[feedback-sistema-procedure.md](feedback-sistema-procedure.md)** — scrive subito in `99_system/feedback_secondo_cervello.md` quando emerge un problema della struttura del sistema.

---
*Modificando una procedura si aggiorna la copia attiva ricaricandola dalle impostazioni: il file resta l'unica fonte, la skill ne è il canale di attivazione.*
