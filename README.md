# 👑 Question pour un GOLMON

> **Battle Royale de culture générale en temps réel pour les streams Twitch & Kick.**
> Dernier survivant = Roi des Golmons.

![Battle Royale](https://img.shields.io/badge/Genre-Battle%20Royale-gold?style=for-the-badge)
![HTML](https://img.shields.io/badge/Stack-HTML%20%2F%20CSS%20%2F%20JS-orange?style=for-the-badge)
![GitHub Pages](https://img.shields.io/badge/Deploy-GitHub%20Pages-222?style=for-the-badge&logo=github)
![Twitch](https://img.shields.io/badge/Chat-Twitch-9147ff?style=for-the-badge&logo=twitch)
![Kick](https://img.shields.io/badge/Chat-Kick-53fc18?style=for-the-badge)

🎮 **[Jouer maintenant](https://moifay.github.io/Golmon/)** — aucune installation, directement dans le navigateur.

---

## 🎮 Concept

| Étape | Description |
|-------|-------------|
| 1 | Le **streamer** connecte son chat Twitch ou Kick |
| 2 | Les **viewers** tapent `!entry` dans le chat pour rejoindre |
| 3 | Le streamer choisit la **catégorie** et le **nombre de vies** |
| 4 | La partie démarre — 1 question QCM, 4 réponses, **25 secondes** |
| 5 | Les viewers répondent **A B C ou D** dans le chat |
| 6 | Le streamer répond en **cliquant** sur les cartes |
| 7 | Mauvaise réponse = perte d'une vie — 0 vie = élimination |
| 8 | Dernier survivant = **👑 ROI DES GOLMONS** |

---

## ✨ Fonctionnalités

### 🎯 Gameplay
- **Battle Royale** — de 2 à ∞ joueurs, dernier survivant gagne
- **Choix du nombre de vies** — 1 (brutal), 2 ou 3 (standard)
- **25 secondes** par question avec timer visuel animé
- **Auto-avance** — dès que tout le monde a répondu, pas d'attente
- **Protection anti-égalité** — si tout le monde se trompe au même round, personne n'est éliminé
- **555 questions** réparties en 11 catégories
- Questions mélangées aléatoirement à chaque partie

### 📺 Plateformes
- **Twitch** — connexion IRC anonyme, aucun token requis
- **Kick** — WebSocket Pusher natif, chatroom ID requis
- Commandes chat : `!entry` pour rejoindre · `!exit` pour quitter

### 👑 Streamer
- Inscrit automatiquement, ne peut pas quitter la partie
- Répond en **cliquant** sur les cartes (les viewers tapent dans le chat)
- Badge couronne 👑 dans le lobby et pendant la partie

### 🎯 Catégories de questions
| Catégorie | Questions |
|-----------|-----------|
| 🧠 Culture générale | 51 |
| 🇫🇷 Culture française | 51 |
| 📜 Histoire | 50 |
| 🔬 Science | 51 |
| ⚽ Football | 50 |
| 🎮 Jeux vidéo | 50 |
| 🎬 Cinéma & Séries | 50 |
| 🎵 Musique | 50 |
| 🏆 Sport | 50 |
| 🗺️ Géographie | 51 |
| 🎨 Art & Littérature | 51 |

### 🔊 Sons & Animations
- Tic-tac aux 5 dernières secondes
- Son quand tout le monde a répondu
- Révélation joueur par joueur avec animation vert/rouge
- Son dramatique à chaque élimination
- Fanfare + confettis au vainqueur
- Bouton 🔊/🔇 pour couper le son

### 💾 Persistance
- **Classement des victoires** par plateforme (Twitch / Kick) sauvegardé en localStorage
- **Sauvegarde de session** — reconnexion en 1 clic à la dernière chaîne connectée

---

## 🗂️ Structure du repo

```
Golmon/
├── index.html       ← Le jeu complet (1 seul fichier)
├── questions.json   ← Les 555 questions (modifiable)
├── twitch.png       ← Logo Twitch
├── kick.png         ← Logo Kick
└── README.md
```

---

## 🚀 Déploiement

Le jeu tourne sur **GitHub Pages** — aucun serveur, aucun backend.

### Cloner et déployer

```bash
git clone https://github.com/MoiFay/Golmon.git
cd Golmon
```

Puis activer GitHub Pages :
1. **Settings → Pages**
2. Source : `Deploy from a branch`
3. Branch : `main` / `/ (root)`
4. Sauvegarder — le site est disponible en 1-2 minutes

---

## ❓ Ajouter des questions

Le fichier `questions.json` contient toutes les questions. Format :

```json
{
  "q": "Quelle est la capitale de la France ?",
  "a": ["Lyon", "Marseille", "Paris", "Bordeaux"],
  "c": 2,
  "cat": "france"
}
```

| Champ | Description |
|-------|-------------|
| `q` | Texte de la question |
| `a` | Tableau des 4 réponses (A, B, C, D) |
| `c` | Index de la bonne réponse (0 = A, 1 = B, 2 = C, 3 = D) |
| `cat` | Catégorie : `culture` `france` `histoire` `science` `football` `gaming` `cinema` `musique` `sport` `geo` `art` |

---

## 🔌 Connexion Chat

### Twitch
Aucune configuration requise — connexion IRC anonyme directe.

### Kick
Le **Chatroom ID** est requis (CORS bloqué côté navigateur) :
1. Ouvre `kick.com/api/v2/channels/TON_PSEUDO` dans ton navigateur
2. Cherche `"chatroom":{"id":`
3. Copie le nombre et colle-le dans le champ

---

## 🛠️ Stack technique

| Élément | Détail |
|---------|--------|
| **Frontend** | HTML / CSS / JavaScript vanilla — 1 fichier |
| **Chat Twitch** | WebSocket IRC anonyme (`wss://irc-ws.chat.twitch.tv`) |
| **Chat Kick** | WebSocket Pusher natif (`wss://ws-us2.pusher.com`) |
| **Sons** | Web Audio API — aucune dépendance |
| **Persistance** | localStorage (classement + session) |
| **Hébergement** | GitHub Pages — 100% gratuit |
| **Dépendances** | Aucune — zéro npm, zéro framework |

---

## 📄 Licence

MIT — Fais-en ce que tu veux. 👑
