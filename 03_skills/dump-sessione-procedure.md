---
name: Dump Sessione
description: Chiude un blocco di lavoro scrivendo una voce datata nel registro di automiglioramento. Usare per "dumpamelo", "fai il dump", "chiudi la sessione", "riassumi cosa abbiamo fatto".
---

# Dump Sessione — Procedura

*v1.1 — 2026-07-26: registro reso impersonale, puntatore alle logiche generali corretto.*

Chiude un blocco di lavoro scrivendo una entry breve e datata nel dump mensile e restituendo lo stesso recap in chat.

**Obiettivo della procedura:** non perdere feedback, decisioni e cose fatte che restano solo nella conversazione o nella memoria automatica dell'assistente, invisibile all'utente.

**Quando si attiva:** trigger manuale, a fine di un blocco di lavoro — "dumpamelo", "fai il dump", "scrivi nel dump", "chiudi la sessione", "riassumi cosa abbiamo fatto".

**Prerequisiti:**
- Accesso in scrittura a `00_context/dump/`.
- Una conversazione in corso da cui estrarre il blocco da riassumere: questa procedura non funziona su una chat vuota o già chiusa.

## Passaggi

### 1. Determina lo scope ("da quando")
Guarda a ritroso nella conversazione corrente e individua dove inizia il blocco tematico attivo — di solito l'ultimo cambio netto di argomento, o l'ultimo dump già fatto in questa sessione, quale dei due è più recente. Se il confine è ambiguo (più argomenti mischiati, nessun punto di rottura chiaro), proponi lo scope individuato in una riga ("Riassumo da [X], giusto?") e aspetta conferma prima di scrivere.

### 2. Filtra, poi categorizza
Prima la soglia, poi la lista. Una riga è giustificata solo se conta per il futuro: un comportamento da ripetere o evitare, una decisione che servirà rileggere, un fatto che cambia lo stato di un progetto. I dettagli di processo interni alla sessione (dove è stato salvato un file, quale formato è stato scelto per una lista, passaggi tecnici della costruzione) non qualificano anche se veri. Nel dubbio, una sessione produce 1-2 righe, non 4.

Per ogni fatto che supera la soglia, assegna una categoria: `[feedback]` (correzione o preferenza che cambia come il sistema si comporta in futuro), `[recap]` (cosa è stato fatto, deciso o prodotto, senza implicazioni future), `[altro]` (thread aperto, domanda rimasta senza risposta).

### 3. Scrivi nel dump del mese corrente
Verifica la data con un comando prima di nominare il file. File: `00_context/dump/AAAA-MM.md` — crea il file se il mese non esiste ancora, con la stessa intestazione già in uso. Formato riga: `- **AAAA-MM-GG [categoria]:** contenuto in 1-2 righe.`

### 4. Restituisci il recap in chat
Incolla in chat le stesse righe appena scritte, senza riformattarle né espanderle — è la stessa informazione, non un secondo riassunto. Niente preamboli.

---

## Risorse Opzionali
- [[manuale-operativo]] (`99_system/manuale-operativo.md`) — solo se serve ripassare le regole generali del sistema, non a ogni esecuzione.

## Cose da Sapere
- Se per costruire il recap si leggono messaggi lunghi o più file, dichiarare una stima dei token usati e segnalare se esiste un modo più economico per ottenere lo stesso risultato.
- Un eventuale trigger automatico va validato su 2-3 usi manuali prima di essere introdotto: un trigger troppo sensibile scrive rumore nel dump (voci deboli o mal categorizzate) che l'utente deve poi ripulire a mano — il costo si sposta da "l'AI scrive troppo poco" a "l'utente deve filtrare di più".
- Se diventa automatica, va coordinata con la Regola 13 di `CLAUDE.md` (scrittura simultanea nella memoria automatica dell'assistente), altrimenti la stessa riga rischia di essere scritta due volte.

## Log Storico
- [2026-07-23] Creazione della procedura.
- [2026-07-23] Fix su Passaggio 2: il primo test reale ha prodotto 4 righe per una sessione che ne valeva 1 (dettagli di processo interni loggati come se contassero). Aggiunta la soglia di rilevanza prima della categorizzazione.
- [2026-07-26] Registro reso impersonale. Corretto il puntatore alle regole generali, che indicava un path non più valido.
