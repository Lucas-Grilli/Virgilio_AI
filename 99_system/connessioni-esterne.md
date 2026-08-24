# Connessioni esterne — guida

> Cos'è: per ogni servizio esterno con cui un progetto ha già dovuto parlare, il metodo giusto già deciso — e perché. Si consulta prima di scrivere una nuova integrazione (script su API, scraping, browser automation): se il servizio è già mappato, si usa quello, non se ne inventa uno nuovo.
> Non è l'inventario dei connettori disponibili nella sessione — quello lo dichiara l'ambiente ad ogni avvio e cambia nel tempo. Qui vivono solo le decisioni prese, che restano vere anche se il roster cambia.
> **Si aggiorna nello stesso momento in cui una chat impara il metodo giusto per un servizio nuovo, o ne trova uno migliore di uno già scritto qui — specialmente dopo un errore che è costato soldi.** Stessa disciplina della Regola 14, applicata a questo dominio.

## Ordine di ricerca, quando il servizio non è ancora in tabella

1. **Chi ha davvero il dato o l'azione che serve?** Non tutte le fonti coprono la stessa cosa: un connettore generico e uno script sull'API ufficiale spesso non sono sostituti, danno dati diversi. Prima di scegliere il mezzo, stabilire chi possiede la cosa.
2. **Tra le fonti che ce l'hanno, qual è già collegata *e viva*?** Collegato non vuol dire funzionante: un account può autenticarsi e rispondere comunque "abbonamento scaduto" sulle chiamate che contano. Verificare con una chiamata reale prima di costruirci sopra.
3. **Se nessuna fonte dedicata esiste:** un aggregatore di connettori (copertura ampia ma non esaustiva — verificare che copra il caso reale) prima di un servizio di scraping a consumo (va preventivato) prima di uno script diretto sull'API ufficiale (quando serve controllo pieno, o i dati sono privati e un intermediario è un rischio inutile).
4. **Browser automation, ultima risorsa.** Solo quando non esiste nessuna API praticabile o l'azione richiede davvero un'interfaccia (login interattivo, captcha, pannelli senza API). È il metodo più lento e più fragile. **Eccezione da riconoscere:** per alcune azioni non esiste proprio un'API a monte — lì il browser non è ripiego, è l'unica strada, e va scritto in tabella come metodo primario.
5. **Ogni run a consumo si annuncia prima**, con tetto di spesa esplicito, e parte solo dopo conferma. Dove il servizio lo permette, il tetto si blinda con un parametro che ferma il lavoro da solo, invece di affidarsi a un limite tenuto a mano.

## Casi decisi

Una riga per servizio, aggiunta quando il metodo è stato provato davvero — non quando è stato ipotizzato.

| Servizio / bisogno | Metodo | Perché | Dove è stato collaudato |
|---|---|---|---|
| | | | |

## Attenzione: collegato non vuol dire funzionante

Un connettore che compare nella lista degli strumenti disponibili non è una garanzia. Prima di progettare un lavoro attorno a una fonte, verificarla con una chiamata reale sul dato che serve: capita che l'autenticazione funzioni e i dati rispondano con un errore di piano scaduto o di permesso mancante. Quando succede, la riga va in questa sezione — non cancellata dalla tabella, perché il fatto che *non* si possa usare è un'informazione che serve al prossimo giro.
