---
name: specializzazione
description: Prima di assistere su un tema dove l'intuizione di base non basta (metodo, psicologia, disciplina con letteratura propria), cerca online teorie ed evidenza, torna con competenze verificate e le cristallizza in una knowledge pill. Usare per "specializzati su X", "vai a cercare le best practice", o quando si sta per impostare un percorso o un'analisi solo sulla conoscenza generale su un tema dove esiste ricerca consolidata.
---

# Specializzazione

*v1.0*

Obiettivo: prima di assistere l'utente su un tema con letteratura propria, l'assistente si specializza invece di rispondere di intuito — cerca online, torna con competenze verificate, le cristallizza in una pillola.

## Passi

1. **Definire il gap** — elencare le 3-6 domande a cui la conoscenza di base risponderebbe con luoghi comuni. Sono quelle da verificare.
2. **Controllo asset esistenti** — leggere `00_context/knowledge_pills/index_knowledge-pills.md`: se una pillola copre già il tema, usare quella (eventualmente aggiornandola), non crearne una doppia (Regola 4 di `CLAUDE.md`).
3. **Ricerca mirata** — una ricerca per domanda, non generica: puntare a studi con autore e anno, meta-analisi, dimensioni dell'effetto. Preferire evidenza primaria o sintesi di evidenza a contenuti motivazionali; segnalare quando l'evidenza contraddice il senso comune — è il valore principale del giro.
4. **Distillare in pillola** — scrivere in `00_context/knowledge_pills/`, un paragrafo per pilastro (cosa dice l'evidenza + riga "Operativo:"), sezione errori tipici, fonti linkate. Densa, non lunga. Voce nell'indice nella stessa operazione (Regola 1). Formato dettagliato: [knowledge-pill](../knowledge-pill/SKILL.md).
5. **Tornare in chat con una posizione** — non un riassunto della ricerca: la risposta al caso concreto alla luce dell'evidenza, incluse le correzioni a ciò che si stava per fare.

## Regole dure

- Diversa da [knowledge-pill](../knowledge-pill/SKILL.md): quella distilla competenza già emersa nelle sessioni, questa la va a prendere fuori.
- Senza accesso a una ricerca esterna la skill non si esegue a memoria: si dichiara il limite e si procede dichiarando che la risposta è di intuito, non verificata.
- L'evidenza si cita, non si evoca: una pillola senza fonti linkate non è il prodotto di questa skill.
