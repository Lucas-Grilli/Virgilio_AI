# Primo Avvio — Procedura

*v1.0*

Prepara un sistema appena installato: intervista breve, compila `memory.md`, apre il primo progetto, mette l'utente in condizione di lavorare.

**Obiettivo della procedura:** portare l'utente da "cartella di file vuoti" a "sistema che sa chi sono e su cosa sto lavorando" in pochi minuti, senza che debba leggere documentazione.

**Quando si attiva:** all'apertura di una sessione, quando `memory.md` risulta ancora non compilato (v. Passaggio 1). L'innesco è la regola di primo avvio in `CLAUDE.md`, non un comando dell'utente.

**Prerequisiti:**
- La cartella del sistema collegata alla sessione.

## Passaggi

### 1. Verifica che serva davvero
Leggi `memory.md`. Se la sezione "Identità" contiene ancora il testo segnaposto tra parentesi quadre, il sistema è nuovo: prosegui. Se è già compilata, il sistema è in uso: non eseguire questa procedura e rispondi normalmente alla richiesta dell'utente.

### 2. Dichiara cosa stai per fare
Una frase, non un discorso: cosa fai, quante domande farai, quanto ci vuole. Poi passa alla prima domanda.

### 3. Fai tre domande, una per messaggio
Mai tutte insieme, mai più di tre in totale. Ognuna riempie una sezione precisa di `memory.md`:

1. **"Chi sei e cosa fai?"** — una riga, non un curriculum. → sezione Identità.
2. **"Su cosa stai lavorando adesso? Da una a tre cose."** → tabella Progetti Attivi.
3. **"Cosa vuoi ottenere nelle prossime due settimane? Oppure quali sono i tuoi obiettivi?"** → sezione Obiettivi.

Se una risposta è vaga, chiedi un chiarimento su quella prima di passare alla successiva. Se l'utente salta una domanda, lascia la sezione corrispondente vuota e va bene: si riempie dopo.

### 4. Compila `memory.md`
Verifica la data con un comando, mai dedurla. Scrivi Identità, Obiettivi con la finestra di date reali, e una riga in Progetti Attivi per ogni cosa citata al punto 2. Poi **mostra all'utente cosa hai scritto**: è la prima prova visibile che il sistema esiste, non un dettaglio di processo.

### 5. Spiega cosa è cambiato, senza aspettare che lo chieda
Tre righe, non un manuale. Dove va il materiale del suo lavoro (`10_projects/`), dove butta gli appunti grezzi quando non ha tempo di ordinarli (`01_raw/`), e il punto che conta: non deve organizzare niente a mano, lo stato lo tiene aggiornato l'assistente man mano che gli racconta cosa succede.

Questo passaggio non è opzionale: a questo punto l'utente ha risposto a tre domande e visto un file compilato, ma non sa ancora cosa ci guadagna. Se glielo lasci chiedere, l'hai già perso.

### 6. Apri il primo progetto
Se l'utente ha citato almeno un progetto, esegui `project-kickoff-procedure.md` per quello. Se ne ha citati più di uno, chiedi da quale partire invece di deciderlo tu.

### 7. Installa le skill
Le procedure in `03_skills/` si attivano da sole solo dopo essere state registrate come skill. **Prova a installarle tu**, se lo strumento per farlo è disponibile in questo ambiente — verifica prima quali risultano già presenti, per non duplicarle:

- `bibliotecario-procedure.md` — trasforma il materiale grezzo di `01_raw/` in note collegate nel wiki.
- `project-kickoff-procedure.md` — apre i prossimi progetti.
- `knowledge-pill-procedure.md` — distilla una competenza ricorrente in un file da richiamare.
- `pulizia-sistema-procedure.md` — controlla che il sistema non si sia rotto.
- `dump-sessione-procedure.md` — chiude una sessione registrando cosa è emerso.
- `feedback-sistema-procedure.md` — registra i problemi del sistema stesso.

Se non puoi installarle da qui, dillo chiaramente e spiega come farlo: impostazioni dell'assistente, sezione Skills, caricare questi file uno alla volta. Una volta sola.

Le procedure restano comunque file leggibili e modificabili: chi ne cambia una aggiorna la copia attiva ricaricandola.

### 8. Provoca la prova
Chiudi dicendo all'utente di chiudere questa conversazione, aprirne una nuova sulla stessa cartella e chiedere "dove eravamo". È l'unica dimostrazione che conta: in una sessione nuova, senza contesto, l'assistente sa già chi è e su cosa sta lavorando.

---

## Cose da Sapere
- Questa procedura gira una volta sola per installazione: il Passaggio 1 è la guardia che lo garantisce.
- Le note e i documenti che l'utente ha già altrove non si importano in questo giro: si mettono in `01_raw/` e si digeriscono col Bibliotecario, quando vuole. Menzionarlo al Passaggio 8 come cosa successiva possibile.
- Registro asciutto: l'utente ha appena scaricato dei file e non sa ancora se fidarsi. Le domande servono a compilare `memory.md`, non a fare conversazione.

## Log Storico
- [2026-07-26] Creazione della procedura.
- [2026-07-26] Aggiunto il Passaggio 5 ("spiega cosa è cambiato"): nel primo test reale l'utente ha dovuto chiedere da sé a cosa servisse il sistema, dopo aver completato l'intervista. Passaggio 7 riscritto: le skill si installano direttamente quando l'ambiente lo permette, invece di delegare all'utente un passaggio manuale.
