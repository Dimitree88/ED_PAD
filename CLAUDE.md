# ED_PAD

Controller hardware (principalmente MIDI) basato su una matrice di pulsanti, con LED RGB,
strip touch e display OLED. **Produce esclusivamente segnali MIDI / di controllo**: nessun
suono, nessun campione audio, nessuna sintesi viene generata a bordo.

## Scope attuale del progetto

**La fase corrente serve solo a definire accuratamente le feature** (le modalità d'uso della
matrice). In questo momento:

- NON si scrive codice / firmware.
- NON si progetta l'hardware nel dettaglio.
- L'obiettivo è approfondire e specificare le **modalità d'uso** (step sequencer, drum machine,
  chord generator, controller Ableton, e altre da definire).

Quando lavori a questo progetto, mantieni il focus sulla progettazione concettuale delle
funzionalità, salvo diversa indicazione esplicita.

## Layout hardware

- **Matrice 8x8** di pulsanti (input principale).
- **Due file aggiuntive da 8 pulsanti** attorno alla matrice: una verticale e una orizzontale.
  - Uno dei due set da 8 (probabilmente quello in alto — TBD, ininfluente per ora) serve a
    **cambiare la funzione/modalità** della matrice.
- **LED RGB sotto ogni pulsante**, controllabili indipendentemente dai pulsanti.
- **Strip di contatti touch** su un lato: presumibilmente ~48 contatti, realizzata con 4x IC MPR121.
- **Display grafico OLED** sul lato inferiore.
- Possibili LED/pulsanti aggiuntivi per la navigazione del display — TBD.

## Specifiche tecniche (note e TBD)

- **CPU:** ATSAMD51J19. Gestisce la matrice di input.
  - Arrangiamento matrice: a matrice con diodi *oppure* con shift register — **TBD**.
- **LED:** SK9822, controllabili con FastLED o con libreria custom.
- **I/O previsti:**
  - Connettore USB (USB MIDI + alimentazione).
  - MIDI OUT su jack 3.5mm.
  - **TBD:** eventuali CV/GATE o ulteriori uscite MIDI.
- **Display OLED:** modello non ancora scelto → chip di gestione **TBD**.

## Modalità d'uso (da definire e ampliare)

Lista iniziale, non esaustiva:

- Step sequencer
- Drum machine
- Chord generator
- Controller Ableton
- Altre da definire

## References e ispirazioni

Manuali presenti in [references/](references/):

- Ableton Push 3 — `ableton_push3-manual-en.pdf`
- Novation Launchpad Pro — `Launchpad Pro User Guide.pdf`
- OXI One — `OXI One User Manual.pdf`
- Yamaha Tenori-on — `tnri_v15_en_qg_e0.pdf`, `tnrw_tnro_en_om_a0.pdf`

Altre ispirazioni citate (manuale non presente):

- Versioni open-firmware del Launchpad Pro
- Monome
- Soundprism Legacy (app iOS)
- App Tenori per iOS

Se conosci altri controller a matrice simili o interessanti, puoi proporne l'aggiunta a questa
lista.
