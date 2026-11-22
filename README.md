# Moviola

App per analizzare frame per frame i video dei tuoi atleti, pensata per iPad: disegni sul video, giunti e angoli rilevati in automatico, traiettoria del bilanciere, confronto con il tuo video e diapositive da mostrare mentre registri lo schermo.

Gira tutta sull'iPad: niente server, niente account, niente Claude. I video e le analisi restano sul dispositivo.

## Installarla sull'iPad (una volta sola, circa 5 minuti)

Safari deve scaricare l'app da un indirizzo la prima volta. Per averne uno gratis si usa GitHub Pages: serve solo come punto di installazione. Nessun video viene caricato lì.

**1. Prepara i file**
Apri lo zip `moviola.zip` nell'app **File** dell'iPad: si crea una cartella con 7 file.

**2. Crea il repository**
Su [github.com](https://github.com) accedi (o crea un account gratis), poi tocca **+ → New repository**. Nome: `moviola`. Lascialo **Public** (GitHub Pages gratis funziona solo così: dentro c'è solo il codice dell'app). Tocca **Create repository**.

**3. Carica i file**
Nella pagina del repository tocca **uploading an existing file** (oppure **Add file → Upload files**), poi **choose your files**: entra nella cartella del punto 1, tocca **Seleziona**, scegli tutti i file e tocca **Apri**. Infine tocca **Commit changes**.

**4. Attiva il link**
Vai in **Settings → Pages**. In *Source* scegli **Deploy from a branch**, branch **main**, cartella **/ (root)**, poi **Save**. Dopo un paio di minuti in alto compare il link: `https://TUO-NOME.github.io/moviola/`.

**5. Aggiungila alla schermata Home**
Apri il link in **Safari**, tocca **Condividi → Aggiungi alla schermata Home → Aggiungi**. Da qui in poi apri Moviola dall'icona: si apre a tutto schermo e funziona anche senza internet.

Due cose da sapere:
- Usala sempre dall'icona: le analisi fatte nella scheda di Safari restano separate da quelle dell'app sulla schermata Home.
- Fai la prima **Analizza movimento** quando sei connesso: il modello dei giunti (da 6 a 30 MB secondo la precisione) si scarica una volta e poi resta sull'iPad.

## Come si usa

1. **Atleta**: carica il video che ti ha mandato l'atleta (rullino o File).
2. Fermati sui frame importanti con le frecce o trascinando la timeline. Con un dito scorri i frame, con due dita fai zoom.
3. Disegna linee, frecce, angoli, cerchi, testi e linee guida (con la Apple Pencil o con il dito). Il frame su cui disegni diventa un **punto chiave**.
4. Pannello **Corpo → Analizza movimento**: giunti e angoli su ogni frame. Puoi mostrare 33, 17, 13 o 9 giunti.
5. Pannello **Punti chiave → Suggerisci fasi**, poi controlla le fasi e accendi le luci sui punti della tua scheda: rossa = errore, bianca = corretto.
6. Pannello **Bilanciere**: tocca il centro del disco e trascina fino al bordo per tracciare la traiettoria.
7. **Coach**: carica il tuo video con il movimento corretto e analizzalo allo stesso modo.
8. **Confronto**: i due video affiancati e sincronizzati, fase per fase.
9. **Diapositive**: una per fase, con il frame dell'atleta accanto al tuo, i punti e gli angoli.
10. **+ Link**: apri esempi da YouTube, Instagram, TikTok o altri siti in una nuova scheda. I siti che non si lasciano mostrare dentro l'app, come le pagine di Claude, si aprono nel browser.
11. **Presenta** nasconde i comandi di modifica: avvia la registrazione dello schermo dal Centro di controllo e parla sopra mentre passi da una scheda all'altra.

Le **schede tecniche** (strappo, girata, slancio, squat, stacco, panca) si modificano nel pannello **Scheda**. Con **Importa da testo** puoi incollare le note che hai già scritto (una riga con `#` per ogni fase, sotto i punti) o creare schede per altri gesti.

## Esportazioni

- **Video annotato** (MP4) con fermo immagine sui punti chiave, fase e punti in sovrimpressione. Anche il confronto affiancato.
- **Diapositive in PDF**.
- **Immagine** del frame, del confronto o della diapositiva.
- **File dell'analisi** (`.moviola`): copia completa con i video, da riaprire su un altro iPad o sul computer con **Le mie analisi → Importa**.

## Da sapere

- Gli angoli sono misurati sull'immagine: per valori affidabili riprendi di profilo, con il telefono fermo all'altezza dei fianchi.
- Le misure del bilanciere sono stime basate sul diametro del disco (45 cm di default, modificabile).
- Il riconoscimento dell'alzata e delle fasi è un suggerimento: controllalo sempre.
- Se cancelli i dati di Safari o disinstalli l'icona, le analisi si perdono: per tenerne una copia usa **Esporta → File dell'analisi**.
- Il video MP4 richiede iPadOS 16.4 o successivo.

## Aggiornare l'app

Se un giorno ricevi una versione nuova di `index.html`, caricala nel repository al posto della vecchia (**Add file → Upload files → Commit changes**). L'iPad la prende alla prima apertura con internet.

## Componenti di terze parti

- [MediaPipe Tasks Vision](https://github.com/google-ai-edge/mediapipe) di Google, licenza Apache 2.0. La libreria si carica da `cdn.jsdelivr.net`, i modelli da `storage.googleapis.com`.
- [mp4-muxer](https://github.com/Vanilagy/mp4-muxer) di Vanilagy, licenza MIT, incluso in `index.html`.
- Carattere [Barlow Condensed](https://github.com/jpt/barlow), SIL Open Font License 1.1, incluso in `index.html`.
