# 🎮 WhatDoYouSwift?

Gioco multiplayer peer-to-peer (P2P) - funziona completamente **senza server**!

## ✨ Caratteristiche

- 🌐 **Nessun server richiesto** - usa WebRTC peer-to-peer
- 📱 **Funziona ovunque** - GitHub Pages, Netlify, o qualsiasi hosting statico
- 🎮 **Multiplayer real-time** - gioca con 3-8 amici
- 🔒 **Privacy** - nessun dato salvato sui server
- 🚀 **Zero configurazione** - basta aprire il link!
- 🎴 **Carte realistiche** - design con bordi arrotondati ed effetti 3D
- 🎲 **Giudice casuale** - ogni round un giocatore diverso sceglie l'immagine
- 👨‍⚖️ **Controllo giudice** - solo il giudice vota il vincitore

## 📁 Struttura File

```
WhatDoYouSwift/
├── index.html      # Gioco principale
├── images.json     # Lista immagini meme
├── texts.json      # Liste frasi per le carte
└── README.md       # Questo file
```

### 📝 File di Configurazione

#### `images.json` - Immagini Meme

Contiene un array di oggetti con le immagini:

```json
[
  {
    "id": 1,
    "url": "https://i.imgflip.com/30b1gx.jpg",
    "alt": "Drake Hotline Bling"
  },
  {
    "id": 2,
    "url": "https://i.imgflip.com/1bij.jpg",
    "alt": "Distracted Boyfriend"
  }
]
```

**Puoi:**
- ✅ Aggiungere nuove immagini
- ✅ Cambiare gli URL
- ✅ Usare immagini locali (es. `./images/meme1.jpg`)
- ✅ Modificare le descrizioni

#### `texts.json` - Carte di Testo

Contiene un semplice array di stringhe:

```json
[
  "Quando realizzi che è già lunedì",
  "La mia vita sociale dopo la quarantena",
  "Io che cerco di essere produttivo"
]
```

**Puoi:**
- ✅ Aggiungere nuove frasi
- ✅ Rimuovere frasi
- ✅ Modificare il testo
- ✅ Creare versioni tematiche (Natale, compleanno, etc.)

### 🔄 Fallback Automatico

Se i file JSON non vengono trovati, il gioco usa dati di esempio integrati per non bloccarsi.

---

## 🚀 Deploy su GitHub Pages

### Opzione 1: Fork & Deploy (Più Facile)

1. **Fai Fork** di questo repository
2. Vai su **Settings** → **Pages**
3. Seleziona **Source**: `main` branch, folder `/`
4. Clicca **Save**
5. Il tuo gioco sarà disponibile su: `https://teorub.github.io/WhatDoYouSwift/`

### Opzione 2: Deploy Manuale

1. Crea un nuovo repository su GitHub (es. `meme-game`)
2. Carica il file `index.html`
3. Vai su **Settings** → **Pages**
4. Abilita GitHub Pages selezionando il branch `main`
5. Fatto! 🎉

## 🎯 Come Giocare

### 📊 Flusso Visivo:

```
CREATORE (Mario)                    AMICI (Luigi & Peach)
     |                                      |
     | 1. Apre il link                      |
     | 2. Crea partita                      |
     | 3. Riceve codice:                    |
     |    "a1b2c3d4..."                     |
     |         |                            |
     |         |-------- Condivide -------->|
     |                   (WhatsApp/etc)     |
     |                                      | 4. Aprono il link
     |                                      | 5. Inseriscono codice
     |                                      | 6. Si connettono
     |<-------- Connessione P2P ----------->|
     |                                      |
     | Tutti giocano insieme! 🎮            |
```

### 📋 IMPORTANTE: Come Connettersi

La connessione è **peer-to-peer** (P2P), quindi funziona così:

#### 🎮 Per il CREATORE della partita:

1. Apri il link del gioco nel browser
2. Inserisci il tuo nome
3. Clicca **"Crea Partita"**
4. Ti verrà dato un **CODICE UNIVOCO** (lungo, tipo: `a1b2c3d4-e5f6-7890...`)
5. **COPIA il codice** (c'è un bottone "Copia Codice")
6. **CONDIVIDI il codice** con i tuoi amici via:
   - WhatsApp
   - Telegram
   - SMS
   - Email
   - Discord
7. ⚠️ **NON CHIUDERE LA PAGINA** - sei il server!

#### 👥 Per chi SI UNISCE:

1. Apri lo **STESSO LINK** del gioco
2. Inserisci il tuo nome
3. Inserisci il **CODICE ricevuto** dal creatore
4. Clicca **"Unisciti a Partita"**
5. Sei dentro! 🎉

#### ⚡ Esempio pratico:

```
Creatore (Mario):
- Crea partita → riceve codice "a1b2c3d4-..."
- Invia su WhatsApp: "Codice partita: a1b2c3d4-..."

Amici (Luigi e Peach):
- Aprono il link
- Inseriscono "a1b2c3d4-..." 
- Si connettono a Mario
```

### Creare una Partita

### 🎮 Gameplay

1. **Aspetta almeno 3 giocatori** nella lobby
2. Tutti cliccano **"Sono Pronto"**
3. L'host clicca **"Avvia Partita"**
4. Ogni turno:
   - Un giocatore viene scelto **casualmente come Giudice** 🎲
   - Il **Giudice sceglie un'immagine meme** dalla galleria
   - Gli altri giocatori scelgono una **carta testo** dalla loro mano
   - Il giudice vede tutte le carte (anonime) e sceglie la **più divertente**
   - Chi vince guadagna **1 punto**
5. **Primo a 5 punti vince!** 🏆

## 🔧 Tecnologie Usate

- **HTML5 + CSS3 + JavaScript** (vanilla, no framework)
- **PeerJS** - per connessioni WebRTC peer-to-peer
- **STUN servers** - Google & Twilio per NAT traversal

## 📱 Compatibilità

✅ Chrome/Edge (Desktop & Mobile)  
✅ Firefox (Desktop & Mobile)  
✅ Safari (Desktop & Mobile)  
✅ Opera  

## 🐛 Troubleshooting

### "Impossibile connettersi"
- Controlla la connessione internet
- Alcuni firewall aziendali bloccano WebRTC
- Prova da una rete diversa (es. hotspot mobile)

### "Partita non trovata"
- Assicurati che il codice sia corretto
- Il creatore deve rimanere connesso
- Il codice è valido solo mentre il creatore è online

### "Disconnessione improvvisa"
- WebRTC richiede connessione stabile
- Se l'host si disconnette, la partita termina
- Ricarica la pagina e ricomincia

## 🎨 Personalizzazione

Puoi facilmente personalizzare:

- **Immagini meme**: modifica l'array `MEME_IMAGES` nel codice
- **Carte testo**: modifica l'array `TEXT_CARDS`
- **Colori**: cambia i gradient in CSS
- **Numero giocatori**: modifica max players (default 8)
- **Punti per vincere**: modifica il check `score >= 5`

## 🌟 Features Future

- [ ] Chat durante il gioco
- [ ] Modalità NSFW
- [ ] Pacchetti tematici (Natale, Halloween, etc.)
- [ ] Upload meme personalizzati
- [ ] Statistiche partita
- [ ] Sistema di emoji reactions

## 📄 Licenza

MIT License - Sentiti libero di usarlo e modificarlo!

## 🤝 Contribuire

Pull requests sono benvenute! Per modifiche importanti, apri prima un issue.

---

## 🎉 Pronto per Giocare!

Una volta deployato su GitHub Pages, condividi il link con i tuoi amici!

**Link Esempio**: `https://teorub.github.io/WhatDoYouSwift/`

---

Made with ❤️ for fun and friends

## 💡 Come Funziona (Tecnico)

### Architettura P2P Spiegata Semplice:

1. **Creazione Partita:**
   - Il creatore apre la pagina
   - **PeerJS** genera un ID univoco (il "codice partita")
   - Questo ID è come un numero di telefono temporaneo
   - Il creatore diventa il "coordinatore" del gioco

2. **Connessione:**
   - Gli altri giocatori usano questo ID per "chiamare" il creatore
   - La connessione avviene **direttamente** tra i browser (P2P)
   - Nessun dato passa attraverso server esterni (tranne per stabilire la connessione iniziale)

3. **Durante il Gioco:**
   - Il creatore gestisce la logica (turni, punteggi, fasi)
   - Ogni azione viene inviata a tutti i giocatori connessi
   - I dati viaggiano **direttamente** tra i browser

4. **Tecnologie Usate:**
   - **WebRTC** - Per connessioni P2P tra browser
   - **PeerJS** - Libreria che semplifica WebRTC
   - **STUN servers** - Server Google/Twilio che aiutano a stabilire la connessione (non vedono i dati del gioco)

### Perché il creatore deve rimanere connesso?

Il creatore è il "server" del gioco. Se si disconnette:
- La logica del gioco si perde
- Le connessioni tra gli altri giocatori si interrompono
- È come se spegnessi il WiFi router di casa

### Vantaggi di questo approccio:

✅ **Gratis** - Nessun server da pagare  
✅ **Privacy** - I tuoi dati non vengono salvati  
✅ **Veloce** - Connessione diretta senza intermediari  
✅ **Semplice** - Un solo file HTML da hostare  

### Limitazioni:

❌ Il creatore deve rimanere connesso  
❌ Alcuni firewall aziendali potrebbero bloccare WebRTC  
❌ Se il creatore ha internet lento, può rallentare il gioco  

---

## 🤝 Contribuire
