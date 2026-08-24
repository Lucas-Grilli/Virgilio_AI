---
name: dump-sessione
description: Chiude un blocco di lavoro scrivendo una voce breve e datata nel dump mensile (00_context/dump/AAAA-MM.md) e restituisce lo stesso recap in chat. Usare per "dumpamelo", "fai il dump", "scrivi nel dump", "chiudi la sessione", "riassumi cosa abbiamo fatto".
---

# Dump sessione

*v2.0*

Obiettivo: non perdere feedback, decisioni e cose fatte che restano solo nella conversazione o nella memoria automatica dell'assistente, invisibile all'utente.

## Passi

1. **Determina lo scope ("da quando")** — guarda a ritroso nella conversazione e individua dove inizia il blocco tematico attivo: di solito l'ultimo cambio netto di argomento, o l'ultimo dump già fatto in questa sessione, quale dei due è più recente. Se ambiguo, proponi lo scope in una riga ("Riassumo da X, giusto?") e aspetta conferma prima di scrivere.
2. **Filtra, poi categorizza** — una riga è giustificata solo se conta per il futuro: un comportamento da ripetere/evitare, una decisione da rileggere, un fatto che cambia lo stato di un progetto. Dettagli di processo interni alla sessione non qualificano anche se veri. Nel dubbio, 1-2 righe, non 4. Categorie: `[feedback]` (correzione/preferenza che cambia il comportamento futuro), `[recap]` (cosa è stato fatto/deciso/prodotto), `[altro]` (thread aperto senza risposta).
3. **Scrivi nel dump del mese corrente** — data reale con un comando prima di nominare il file. `00_context/dump/AAAA-MM.md`, crea il file se il mese non esiste con l'intestazione già in uso. Formato: `- **AAAA-MM-GG [categoria]:** contenuto in 1-2 righe.`
4. **Restituisci il recap in chat** — incolla le stesse righe appena scritte, senza riformattarle né espanderle. Niente preamboli.

## Regole dure

- Non funziona su una chat vuota o già chiusa: serve una conversazione in corso da cui estrarre il blocco.
- Se per costruire il recap si leggono messaggi lunghi o più file, dichiarare una stima dei token usati e un'alternativa più economica se esiste.
- Trigger manuale, mai automatico. Se un giorno lo diventa: va validato su 2-3 usi manuali prima (un trigger troppo sensibile scrive rumore che l'utente deve poi filtrare), e coordinato con la Regola 14 di `CLAUDE.md` (registro di automiglioramento) per non scrivere la stessa riga due volte.
