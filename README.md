# FamilyChat 🏠

Messagerie instantanée privée pour la famille — type WhatsApp.

## Fonctionnalités
- ✅ Comptes : Papa, Maman, Enfant 1, Enfant 2
- ✅ Groupe famille + conversations individuelles (1 à 1)
- ✅ Messages en temps réel (Socket.io)
- ✅ Emojis + réactions rapides (clic droit sur un message)
- ✅ Envoi de photos et fichiers (PDF, ZIP, etc.)
- ✅ Indicateur "en train d'écrire…"
- ✅ Accusés de lecture (✓ / ✓✓)
- ✅ Présence en ligne (point vert)
- ✅ Notifications navigateur
- ✅ Recherche de conversations
- ✅ Thème sombre, responsive mobile

## Installation

### Prérequis
- Node.js v18+ : https://nodejs.org

### Lancer l'application

```bash
# 1. Extraire le dossier, puis :
cd familychat
npm install
node server.js
```

Ouvrir dans le navigateur : **http://localhost:3000**

### Accès depuis d'autres appareils (même réseau Wi-Fi)

1. Trouver l'IP de la machine : `ipconfig` (Windows) ou `ifconfig` (Mac/Linux)
2. Ouvrir depuis n'importe quel appareil : `http://192.168.X.X:3000`

### Accès depuis Internet (optionnel)

Utiliser **ngrok** pour partager en dehors du réseau :
```bash
npx ngrok http 3000
```
→ Partager le lien `https://xxx.ngrok.io` à la famille.

## Personnalisation

Modifier les profils dans `server.js` (ligne ~20) :
```js
users: [
  { id: 'u1', name: 'Papa',   avatar: '👨', color: '#4A90D9' },
  { id: 'u2', name: 'Maman',  avatar: '👩', color: '#E57373' },
  { id: 'u3', name: 'Lucas',  avatar: '🧒', color: '#66BB6A' },
  { id: 'u4', name: 'Emma',   avatar: '👧', color: '#FFA726' },
]
```

## Données

Les messages sont sauvegardés dans `data.json`.  
Les fichiers envoyés sont dans `public/uploads/`.

## Structure
```
familychat/
├── server.js          ← Serveur Node.js + Socket.io
├── data.json          ← Messages et config (auto-créé)
├── package.json
└── public/
    ├── index.html     ← Interface web complète
    └── uploads/       ← Fichiers envoyés (auto-créé)
```
