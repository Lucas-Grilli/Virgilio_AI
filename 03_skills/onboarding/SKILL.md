# Primo Avvio — Procedura

*v1.1*

Prepara un sistema appena installato: conduce una conversazione breve, compila `memory.md`, apre il primo progetto, mette l'utente in condizione di lavorare.

**Obiettivo della procedura:** portare l'utente da "cartella di file vuoti" a "sistema che sa chi sono, su cosa sto lavorando e cosa mi serve davvero" in pochi minuti, senza che debba leggere documentazione e senza che debba capire come è fatto dentro.

**Quando si attiva:** all'apertura di una sessione, quando `memory.md` risulta ancora non compilato (v. Passaggio 1). L'innesco è la regola di primo avvio in `CLAUDE.md`, non un comando dell'utente.

**Prerequisiti:**
- La cartella del sistema collegata alla sessione.

## Come si sta in questa conversazione

Vale per tutti i passaggi che seguono, prima ancora dei passaggi stessi.

**Conduci tu.** L'utente ha appena scaricato dei file, non sa cosa aspettarsi e non sa ancora se fidarsi: non è nella posizione di guidare, e se gli lasci il volante si ferma. Chiedi una cosa alla volta, sapendo già dove stai andando, e porta tu la conversazione al passaggio successivo. Non chiedere il permesso di procedere ("vuoi che ti faccia qualche domanda?") — procedi.

**Fatti capire.** In questa conversazione non esistono nomi di cartelle, nomi di file, "indici", "propagazione", "router". Esistono: le sue cose, i suoi progetti, quello che gli serve. Il vocabolario tecnico si offre, non si impone (v. Passaggio 6).

**Ascolta davvero.** Se una risposta apre qualcosa di più interessante della domanda successiva, seguila per un turno prima di tornare in carreggiata. Un questionario compilato bene è comunque un questionario: quello che deve restare all'utente è la sensazione di essere stato capito.

**Non riproporre mai questa procedura a chi l'ha già fatta.** V. Passaggio 1: è la guardia che lo garantisce, e non si salta.

## Passaggi

### 1. Verifica che serva davvero
Leggi `memory.md`. Se la sezione "Identità" contiene ancora il testo segnaposto tra parentesi quadre, il sistema è nuovo: prosegui.

Se è già compilata, l'onboarding è già stato fatto: **non eseguire questa procedura e non nominarla**. Rispondi normalmente alla richiesta dell'utente. Riproporre l'onboarding a chi ha già il sistema in uso è l'errore più grave che questa procedura possa produrre: significa aver perso lo stato di chi si fidava.

### 2. Apri, senza chiedere permesso
Due righe: cosa stai per fare, quanto ci vuole, cosa ci guadagna. Poi vai dritto alla prima domanda, nello stesso messaggio.

Non elencare le domande in anticipo e non annunciare la struttura della conversazione: l'utente non deve prepararsi a un modulo da compilare.

### 3. Le tre domande, una per messaggio
Mai tutte insieme. Ognuna riempie una parte precisa di `memory.md`, ma questo riguarda te, non lui: all'utente non si dice quale casella sta riempiendo.

1. **"Chi sei e cosa fai?"** — una riga, non un curriculum. → sezione Identità.
2. **"Su cosa stai lavorando adesso? Da una a tre cose."** → tabella Progetti Attivi.
3. **"Cosa ti aspetti da me? E qual è oggi il tuo punto dolente — nell'organizzarti, o nel modo in cui usi l'AI?"** → sezione Obiettivi, dopo che l'hai tradotto (v. sotto).

La terza è la più importante delle tre e va trattata come tale: non liquidarla con un "ricevuto". La risposta arriva quasi sempre come lamentela ("perdo tempo", "mi dimentico le cose", "ogni volta ricomincio da capo"), e il tuo lavoro è **restituirgliela tradotta in un obiettivo concreto**, chiedendo conferma:

> *"Quindi il problema vero non è prendere appunti, è che ogni conversazione riparte da zero. L'obiettivo diventa: non rispiegare mai più il contesto. Ci siamo?"*

È qui che l'utente capisce se ha davanti qualcosa che ha capito il suo problema o un questionario travestito. Se la risposta è vaga, chiedi un esempio concreto di una volta in cui è successo, invece di passare oltre.

Se l'utente salta una domanda, lascia la sezione corrispondente vuota e va bene: si riempie dopo.

### 4. La domanda aperta
Una sola, dopo le tre:

> **"Ultima, e la più libera: dimmi tutto quello che un assistente dovrebbe sapere di te per aiutarti al meglio. Come lavori, cosa ti fa perdere tempo, cosa non sopporti, come vuoi che ti parli. Anche disordinato — ci penso io a metterlo in ordine."**

Serve a raccogliere ciò che le tre domande strutturate non possono prevedere: preferenze, vincoli, modo di lavorare, contesto personale. Non ha un limite di lunghezza e non va interrotta.

Quello che arriva si smista così: ciò che è operativo e cambia nel tempo entra in `memory.md`; ciò che descrive *come è fatto* l'utente — preferenze stabili, modo di lavorare, cose da non fare mai — diventa una nota in `00_context/`, che è il posto da cui verrà riletto in ogni sessione futura. Se la risposta è ricca, dillo esplicitamente: quello che ha appena scritto una volta non lo dovrà riscrivere mai più.

### 5. Compila `memory.md`
Verifica la data con un comando, mai dedurla. Scrivi Identità, Obiettivi con la finestra di date reali, e una riga in Progetti Attivi per ogni cosa citata alla domanda 2. Poi **mostra all'utente cosa hai scritto**: è la prima prova visibile che il sistema esiste, non un dettaglio di processo.

Compilando sparisce il testo segnaposto — ed è quello, e solo quello, che impedisce a questa procedura di ripartire in futuro (v. Passaggio 1).

### 6. Spiega cosa è cambiato, senza aspettare che lo chieda
Tre righe, in italiano, senza nominare cartelle né file: da adesso quello che gli racconta resta; non deve organizzare niente a mano; quando riapre una conversazione nuova il sistema sa già dove eravate rimasti.

Poi, una riga sola, offri il livello tecnico invece di imporlo:

> *"Se ti interessa sapere dove finiscono fisicamente le cose e come è fatto dentro, te lo spiego in due minuti. Altrimenti funziona lo stesso e non ti serve saperlo."*

Se dice di sì, allora — e solo allora — nomina le cartelle e cosa fa ognuna. Se dice di no, non tornarci sopra.

Questo passaggio non è opzionale: a questo punto l'utente ha risposto a quattro domande e visto un file compilato, ma non sa ancora cosa ci guadagna. Se glielo lasci chiedere, l'hai già perso.

### 7. Apri il primo progetto
Se l'utente ha citato almeno un progetto, esegui `project-kickoff/SKILL.md` per quello. Se ne ha citati più di uno, chiedi da quale partire invece di deciderlo tu.

### 8. Le skill: già pronte, o da installare a mano
Se sei su Claude Code, le sei skill sono già attive: `.claude/skills/` ne contiene una copia pronta all'uso, non serve fare niente. Se non sei sicuro di essere su Claude Code, verificalo con il meccanismo di discovery delle skill invece di dedurlo.

Se non lo sei (claude.ai, app), dillo chiaramente all'utente e proponi di installarle: apri il file `SKILL.md` dentro ciascuna delle sei cartelle in `03_skills/` (tutte tranne questa), copiane il contenuto, e incollalo in Impostazioni → Competenze → "Scrivi le istruzioni della skill". Una volta sola, una skill alla volta:

- `bibliotecario/` — prende il materiale grezzo che l'utente butta dentro e lo trasforma in conoscenza ordinata e in progetti.
- `project-kickoff/` — apre i prossimi progetti.
- `knowledge-pill/` — distilla una competenza ricorrente in un file da richiamare.
- `specializzazione/` — va a cercare fuori l'evidenza su un tema, invece di rispondere di intuito.
- `pulizia-sistema/` — controlla che il sistema non si sia rotto.
- `dump-sessione/` — chiude una sessione registrando cosa è emerso.

Le procedure restano comunque file leggibili e modificabili in `03_skills/`, che è la fonte: chi ne cambia una su Claude Code deve poi ricopiarla anche in `.claude/skills/` (non è collegata in automatico), su claude.ai/app la ricarica dalle impostazioni.

### 9. Provoca la prova
Chiudi dicendo all'utente di chiudere questa conversazione, aprirne una nuova sulla stessa cartella e chiedere "dove eravamo". È l'unica dimostrazione che conta: in una sessione nuova, senza contesto, l'assistente sa già chi è e su cosa sta lavorando.

Se ha materiale già suo da qualche altra parte — appunti, documenti, thread salvati — è il momento di dirgli che può buttarlo dentro così com'è, senza ordinarlo: ci pensa il Bibliotecario a smistarlo tra conoscenza e progetti.

---

## Cose da Sapere
- Questa procedura gira una volta sola per installazione: il Passaggio 1 è la guardia che lo garantisce, e il Passaggio 5 è ciò che la rende definitiva.
- Le note e i documenti che l'utente ha già altrove non si importano in questo giro: si mettono in `01_raw/` e si digeriscono col Bibliotecario, quando vuole. Menzionarlo al Passaggio 9 come cosa successiva possibile.
- Registro asciutto ma non freddo: le domande servono a capire l'utente, non a fare conversazione — e nemmeno a riempire caselle.

## Log Storico
- [2026-07-26] Creazione della procedura.
- [2026-07-26] Aggiunto il Passaggio 5 ("spiega cosa è cambiato"): nel primo test reale l'utente ha dovuto chiedere da sé a cosa servisse il sistema, dopo aver completato l'intervista. Passaggio 7 riscritto: le skill si installano direttamente quando l'ambiente lo permette, invece di delegare all'utente un passaggio manuale.
- [2026-08-04] Riscrittura dopo la prima demo dal vivo. Aggiunta la sezione "Come si sta in questa conversazione": il sistema conduceva poco e compilava molto. Terza domanda sostituita (era "cosa vuoi ottenere nelle prossime due settimane", troppo generica) con aspettative + punto dolente, e con l'obbligo di restituire il problema tradotto in obiettivo. Aggiunta la domanda aperta finale (Passaggio 4). Passaggio 6: i nomi di cartelle e file non si nominano più d'ufficio, si offrono. Passaggio 1 rinforzato sul divieto di riproporre l'onboarding a chi l'ha già fatto.
