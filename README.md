# 🏝️ L'île des mini-jeux

Jeu 2D en **Python / Pygame** réalisé dans le cadre du projet logiciel de 3A à Polytech Grenoble.

Le joueur explore une île en vue du dessus (style Pokémon), se déplace à pied, en courant, à vélo ou en surf, et lance des **mini-jeux d'arcade** en s'approchant des bornes réparties sur la carte. Les meilleurs scores sont enregistrés dans des sauvegardes.

## ✨ Fonctionnalités

- **Menu principal** : créer une partie (nom + choix du skin), charger une sauvegarde
- **Exploration** d'une carte réalisée avec Tiled (`.tmx`), avec collisions, zones d'eau et changements de zone (maison, labo, Pokécenter, boutique…)
- **4 modes de déplacement** : marche, course, vélo, surf
- **5 mini-jeux** intégrés :
  - Tetris
  - Pac-Man
  - Snake
  - Space Invaders
  - Breakout
- **Sauvegardes JSON** : position, carte, skin et meilleurs scores par jeu
- Musiques par écran et transitions en fondu entre la carte et les mini-jeux

## 🎮 Commandes

| Touche | Action |
|---|---|
| Flèches | Se déplacer / jouer |
| `E` | Lancer le mini-jeu à proximité |
| `R` | Courir |
| `B` | Vélo |
| `S` | Surfer (sur l'eau) |
| `M` | Ouvrir / fermer le menu en jeu (scores, retour au menu) |
| `Échap` | Quitter un mini-jeu |
| `Espace` | Tirer (Space Invaders) / action |

## 🚀 Lancer le jeu

**Prérequis :** Python 3.11+

```bash
pip install pygame pytmx pyscroll
```

Depuis la racine du projet :

```bash
# Windows (PowerShell)
$env:PYTHONPATH="code;code/map_affichage"
python code/map_affichage/main.py

# Linux / macOS
PYTHONPATH=code:code/map_affichage python3 code/map_affichage/main.py
```

> Il faut lancer le jeu depuis la racine du projet, car les assets sont chargés en chemins relatifs (`assets/...`).

## 📁 Structure

```
projet_logiciel/
├── code/
│   ├── map_affichage/   # moteur principal : menu, boucle de jeu, carte, joueur, sauvegardes
│   │   ├── main.py      # point d'entrée
│   │   ├── game.py      # boucle de jeu + gestion des mini-jeux
│   │   ├── menu.py      # menu principal
│   │   ├── map.py       # chargement des cartes Tiled
│   │   ├── player.py    # joueur, modes de déplacement, menu en jeu
│   │   └── save_manager.py
│   └── jeux/            # mini-jeux (tetris, pacman, snake, space_invader, breakout)
├── assets/
│   ├── map/             # cartes .tmx + tilesets
│   ├── sprite/          # sprites du joueur
│   ├── music/           # musiques
│   └── json/            # données (pokémon, attaques, talents)
└── saves/               # sauvegardes des joueurs (.json)
```

## 🛠️ Technologies

- Python
- Pygame
- PyTMX + Pyscroll (rendu des cartes Tiled)
- JSON (sauvegardes)

## 👥 Auteurs

- Karim Glelah
- *(ajouter les autres membres de l'équipe)*

---

*Projet scolaire — les sprites, musiques et données inspirés de Pokémon appartiennent à leurs ayants droit respectifs et sont utilisés à des fins pédagogiques uniquement.*
