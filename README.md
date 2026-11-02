# Deficit calorico

Web app per telefono che somma il deficit calorico giorno per giorno fino all'obiettivo (di default 31.000 kcal).

## Come funziona

1. **Durante il giorno**: nella vista *Giorno* i cibi sono divisi in Colazione, Pranzo, Cena e Spuntino. Il modulo di inserimento si apre nel pasto giusto in base all'ora; «Aggiungi» su un altro pasto lo sposta lì. Per ogni cibo: nome, grammi (facoltativi) e kcal.
2. **Il mattino dopo**: in alto compare l'avviso «Chiudi ieri». Inserisci le kcal totali consumate (dallo smartwatch: attive + a riposo) e premi Salva.
3. **Deficit del giorno** = kcal consumate − kcal mangiate. Si somma al totale; un giorno in surplus lo riduce.

Regole di calcolo:
- Un giorno entra nel totale solo se ha **sia i cibi sia le kcal consumate**. Se hai digiunato, aggiungi «Digiuno» con 0 kcal.
- Contano solo i giorni dalla **data di inizio** (Impostazioni) a oggi.
- Gli equivalenti in kg usano la stima convenzionale di 7.700 kcal per 1 kg di grasso: è un'indicazione, non una misura.
- L'arrivo stimato usa la media dei giorni chiusi e compare dopo almeno 3 giorni chiusi.

### Cibi e grammi

- Ogni cibo usato viene ricordato con l'ultima porzione (es. Yogurt 150 g = 105 kcal). Quando lo riscrivi, grammi e kcal si compilano da soli.
- Se cambi i grammi, le kcal si ricalcolano in proporzione (Yogurt 200 g = 140 kcal).
- «Ho le kcal per 100 g»: scrivi i grammi e le kcal per 100 g dell'etichetta, le kcal si calcolano da sole.
- I cibi più frequenti compaiono come pulsanti: un tocco li aggiunge al pasto aperto (con «Annulla» se sbagli).
- Tocca un cibo per modificarlo (anche grammi e pasto), × per eliminarlo.

### Pasti salvati

- Sotto ogni pasto con almeno un cibo c'è **«Salva come pasto»**: dai un nome (es. «Colazione classica») e lo salvi con tutti i cibi, grammi e kcal.
- Nel modulo di inserimento compaiono i pasti salvati: un tocco aggiunge tutti i cibi al pasto aperto, con le kcal già pronte. Poi puoi modificare i singoli cibi.
- Per aggiornare un pasto salvato, salvane uno con lo stesso nome: sostituisce il vecchio. Per eliminarlo: *Impostazioni → Pasti salvati*.

### Calendario

Verde deficit, rosa surplus, tratteggiato da chiudere. Tocca un giorno per aprirlo.

## Dove sono i dati

Solo nel browser del telefono (localStorage). Il repository GitHub contiene il codice, **non i tuoi dati**.
Esporta un backup da *Impostazioni* ogni tanto, e sempre prima di cambiare telefono o cancellare i dati del browser.
Per non perderli, usa l'app installata sulla schermata Home (vedi sotto).

## Pubblicazione su GitHub Pages

1. Crea un nuovo repository pubblico, per esempio `deficit`.
2. Carica **tutti** i file mantenendo le cartelle:
   ```
   index.html
   manifest.webmanifest
   sw.js
   fonts/archivo.woff2
   fonts/OFL.txt
   icons/icon-192.png
   icons/icon-512.png
   icons/icon-maskable-512.png
   icons/apple-touch-icon.png
   ```
   (Da browser: *Add file → Upload files* e trascina il contenuto della cartella, non la cartella stessa.)
3. *Settings → Pages → Build and deployment*: Source **Deploy from a branch**, branch **main**, cartella **/ (root)**, Save.
4. Dopo 1–2 minuti l'app è su `https://<tuo-utente>.github.io/deficit/`.

Funziona anche caricando solo `index.html`, ma senza icona, font e uso offline.

## Installarla sul telefono

- **iPhone (Safari)**: apri l'indirizzo → Condividi → *Aggiungi alla schermata Home*.
- **Android (Chrome)**: apri l'indirizzo → menu ⋮ → *Installa app* (o *Aggiungi a schermata Home*).

Installata, si apre a schermo intero e funziona anche senza rete.

## Aggiornamenti

Se modifichi `index.html`, basta ricaricarlo su GitHub: l'app scarica la nuova versione alla prima apertura con rete.
Se cambi font o icone, aumenta la versione in `sw.js` (`deficit-v1` → `deficit-v2`).

## Crediti

Font Archivo (Omnibus-Type), licenza SIL Open Font License, vedi `fonts/OFL.txt`.
