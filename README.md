# Vandamme – Esplorazione, Passive e Trappole

Modulo per **Foundry VTT v14** con **dnd5e 5.x**.

## Installazione

**Da server ospitato (consigliato).** Nel setup di Foundry: *Add-on Modules → Install Module*, incolla il Manifest URL e premi *Install*.

- Vandamme: `https://github.com/N3mesis89/Vandamme-foundry/releases/latest/download/module.json`
- Libreria trappole: `https://github.com/N3mesis89/Vandamme-foundry/releases/download/libreria-1.0.0/vandamme-libreria.json`

Poi apri il mondo e attiva i due moduli in *Gestisci moduli*. Al primo avvio da GM viene creata la cartella macro **Vandamme** con tutti i comandi. "Cerca trappole" e "Disinnesca trappola" sono già visibili ai giocatori: fagliele trascinare nella barra rapida.

**Gli aggiornamenti** di Vandamme si installano dal setup con *Aggiorna*. La libreria non si aggiorna mai: è lì che restano i tuoi template.

Prima di usarlo in sessione, provalo in un mondo di test (o in una copia del mondo) con un account giocatore di prova aperto in un'altra finestra del browser.

---

## 1. Percezione e Indagare passivi

**Preparazione**
1. Disegna una Region sulla zona (stanza, corridoio, altare…).
2. Aggiungi il Behavior **Vandamme: Percezione passiva**.
3. Compila fino a 4 righe. Ogni riga ha l'abilità passiva, la CD e il contenuto. Per ignorare una riga lascia vuota la CD.

**Il contenuto può essere:**
- **Testo incollato dalla guida.** Il giocatore vede un popup e trova lo stesso testo in chat, sussurrato a lui, così può rileggerlo.
- **L'UUID di un diario.** Il giocatore riceve il permesso di lettura su quel diario, che si apre sul suo schermo. Se il diario ha un pin sulla mappa, il pin gli compare e riceve un ping. Può riaprirlo quando vuole con un doppio clic sul pin, senza che la zona si riattivi.

**Handout con pin: come prepararli**
- Crea **un diario per ogni punto d'interesse** e incollaci il testo della guida.
- Trascina il diario sulla mappa nel punto preciso (graffi, altare, quadro…).
- Lascia il permesso dei giocatori su *Nessuno*: il pin resta invisibile finché la passiva non lo sblocca.
- Per copiare l'UUID: apri il diario e fai clic destro sull'icona dell'ID nell'intestazione.

Ogni riga scatta una sola volta per personaggio. Se la passiva cresce (per esempio con un livello o un oggetto), le righe non ancora superate possono scattare in seguito.

---

## 2. Interagibili (prova su richiesta, una volta per PG)

Servono per gli indizi che la passiva non basta a capire. Esempio: la passiva nota il disordine; un'Indagare riuscita capisce che c'è stata una colluttazione.

1. Crea il diario con la descrizione visibile e mettine il pin sulla mappa.
2. Esegui la macro **Configura interagibile** e scegli il diario.
3. Imposta la prova, la CD, l'invito ("Vuoi esaminare più da vicino?") e il risultato per successo e fallimento. Il risultato può essere testo o l'UUID di un altro diario, per esempio una rivelazione con il suo pin.

Quando un giocatore fa doppio clic sul pin (con il proprio token selezionato), il diario si apre e compare la richiesta di prova. Ogni PG tira una sola volta. Ai clic successivi rilegge soltanto il proprio esito.

Puoi combinarlo con la passiva: se la riga passiva punta al diario interagibile, la passiva fa comparire il pin e il clic chiama la prova.

---

## 3. Prove di gruppo

1. Seleziona i token dei PG trascinando un'area. Se non selezioni nulla, partecipano tutti i PG in scena.
2. Esegui la macro **Prova di gruppo**.
3. Scegli le abilità ammesse, la CD (facoltativa) e chi vede i risultati.

Ogni giocatore riceve un popup in cui sceglie l'abilità e tira con svantaggio, normale o vantaggio, oppure passa. In chat compare **un solo riquadro**, che si aggiorna man mano che arrivano i risultati.

---

## 4. Trappole

Disegna una Region sulla trappola e aggiungi il Behavior **Vandamme: Trappola**.

- **Ad area** (piastra, filo): la Region copre le caselle che la fanno scattare.
- **Unitaria** (runa, serratura, porta): la Region copre la sola casella dell'oggetto. Si scopre solo da una casella adiacente.

### Ricerca attiva: macro "Cerca trappole" (giocatore)

- Tira in segreto Percezione e Indagare. Solo il GM vede i risultati, in un messaggio cieco.
- In chat compare un messaggio d'atmosfera e il token riceve l'icona dell'occhio.
- **Qualsiasi altra prova** del personaggio interrompe la ricerca e il giocatore riceve un avviso. Per ricominciare deve riattivare il comando.
- Usata di nuovo mentre è attiva, la macro la spegne.

### Scoperta

Il punteggio del PG è il migliore tra la ricerca attiva e, se l'opzione è attiva, il valore passivo. Viene confrontato con la CD di scoperta:
- quando il PG arriva entro la **distanza di rilevamento** (per le unitarie, la casella adiacente);
- oppure quando ci mette piede sopra: in quel caso il token si ferma subito.

Se la scopre, il gioco va in pausa, la Region diventa rossa e visibile a tutti. Il giocatore riceve il **testo di scoperta** (campo della trappola) e la proposta di disinnesco, e può tentare subito o lasciar stare.

### Disinnesco

La prova si sceglie nel Behavior: arnesi da scasso, un'abilità (per esempio Arcano per una runa) o una caratteristica.
- Se riesce, la trappola si disattiva e la Region diventa verde.
- Se fallisce di almeno il valore impostato (5 di default), la trappola scatta.
- Per riprovare più tardi c'è la macro **Disinnesca trappola**.

### Innesco

Se nessuno l'ha scoperta, il token si ferma e il gioco va in pausa. Poi compare la descrizione dell'effetto e ogni coinvolto riceve la richiesta del tiro salvezza. I danni vengono tirati e applicati in automatico, dimezzati se il tiro salvezza riesce.

Se un giocatore non risponde entro il tempo impostato, il TS parte in automatico.

**Porte e serrature:** disattiva "scatta quando un token ci entra". Se aprono senza disinnescare, la fai scattare tu con la macro **Fai scattare trappola**, che colpisce i token selezionati.

---

## 5. Libreria trappole (template)

Serve il modulo **Vandamme – Libreria trappole** attivo. I template stanno nel suo compendio, condiviso fra tutti i mondi del server.

**Aprire la libreria:** pulsante con il teschio negli strumenti delle Region, oppure la macro **Libreria trappole**.

**Piazzare una trappola**
1. Nella libreria premi **Piazza** su un template, oppure **Trappola vuota**.
2. Disegna l’area sulla mappa con uno strumento delle Region (rettangolo, celle…), della misura che vuoi. Esc annulla.
3. La Region nasce con la trappola già compilata e la scheda si apre: controlla o cambia CD, abilità, distanza, TS e danni.

**Salvare come template:** nella scheda della trappola premi **Salva come template** (salva prima le modifiche e poi crea il template). In alternativa, seleziona la Region ed esegui la macro **Salva trappola come template**. Se il nome esiste già, ti chiede se sovrascrivere.

Il template è una copia: se lo modifichi o lo elimini, le trappole già piazzate non cambiano.

**Esporta / Importa:** dalla libreria, per salvare tutti i template in un file JSON o caricarli da un file. Tienine una copia di sicurezza.

**Esempi inclusi:** Trappola a filo esempio, Fossa nascosta esempio, Piastra del gas esempio, Runa sulla serratura esempio.

---

## Macro

| Macro | Chi | Comando |
|---|---|---|
| Cerca trappole | giocatori | `Vandamme.cercaTrappole();` |
| Disinnesca trappola | giocatori | `Vandamme.disinnesca();` |
| Prova di gruppo | GM | `Vandamme.provaGruppo();` |
| Configura interagibile | GM | `Vandamme.configuraInteragibile();` |
| Fai scattare trappola | GM | `Vandamme.scattaTrappola();` |
| Reset Vandamme | GM | `Vandamme.reset();` |
| Libreria trappole | GM | `Vandamme.libreriaTrappole();` |
| Salva trappola come template | GM | `Vandamme.salvaTemplate();` |

**Reset Vandamme** riarma le trappole della scena e dimentica passive, interagibili e ricerche dei PG. È pensata per i test.

## Impostazioni

- **Attesa risposta dei giocatori**: 120 secondi di default.
- **Mostra ai giocatori i pin dei diari**: attiva per i giocatori la visualizzazione delle note sulla mappa.

## Se qualcosa non funziona

Apri la console con F12, riproduci il problema e copia gli errori rossi, soprattutto quelli che contengono `vandamme`.
