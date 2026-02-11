# 🎮 Meme Game - P2P Multiplayer

Gioco multiplayer peer-to-peer (P2P) ispirato a "What Do You Meme?" - funziona completamente **senza server**!

## ✨ Caratteristiche

- 🌐 **Nessun server richiesto** - usa WebRTC peer-to-peer
- 📱 **Funziona ovunque** - GitHub Pages, Netlify, o qualsiasi hosting statico
- 🎮 **Multiplayer real-time** - gioca con 3-8 amici
- 🔒 **Privacy** - nessun dato salvato sui server
- 🚀 **Zero configurazione** - basta aprire il link!

## 🚀 Deploy su GitHub Pages

### Opzione 1: Fork & Deploy (Più Facile)

1. **Fai Fork** di questo repository
2. Vai su **Settings** → **Pages**
3. Seleziona **Source**: `main` branch, folder `/`
4. Clicca **Save**
5. Il tuo gioco sarà disponibile su: `https://tuo-username.github.io/meme-game-p2p/`

### Opzione 2: Deploy Manuale

1. Crea un nuovo repository su GitHub (es. `meme-game`)
2. Carica il file `index.html`
3. Vai su **Settings** → **Pages**
4. Abilita GitHub Pages selezionando il branch `main`
5. Fatto! 🎉

## 🎯 Come Giocare

### Creare una Partita

1. Apri il gioco nel browser
2. Inserisci il tuo nome
3. Clicca **"Crea Partita"**
4. Condividi il **codice partita** con i tuoi amici

### Unirsi a una Partita

1. Apri il gioco
2. Inserisci il tuo nome
3. Inserisci il **codice partita** ricevuto
4. Clicca **"Unisciti"**

### Gameplay

1. **Aspetta almeno 3 giocatori** nella lobby
2. Tutti cliccano **"Sono Pronto"**
3. L'host clicca **"Avvia Partita"**
4. Ogni turno:
   - Un giocatore è il **Giudice** (rotazione automatica)
   - Appare un'**immagine meme**
   - Gli altri giocatori scelgono una **carta testo**
   - Il giudice sceglie la **carta più divertente**
   - Chi vince guadagna **1 punto**
5. **Primo a 5 punti vince!**

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

## 💡 Come Funziona (Tecnico)

1. **PeerJS** crea un ID univoco per ogni giocatore
2. Il **creatore** condivide il suo peer ID come "codice partita"
3. Gli altri giocatori si connettono usando questo ID
4. L'**host** gestisce la logica di gioco e la sincronizzazione
5. Tutti i messaggi viaggiano **peer-to-peer** (no server intermediario)
6. **STUN servers** aiutano a stabilire la connessione attraverso NAT/firewall

---

## 🎉 Pronto per Giocare!

Una volta deployato, condividi il link con i tuoi amici e divertiti! 🚀

**Link Demo**: [https://tuo-username.github.io/meme-game-p2p/](https://tuo-username.github.io/meme-game-p2p/)

---

Made with ❤️ for fun and friends
