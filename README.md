# 🏝️ L'île des mini-jeux

Jeu 2D en **Python / Pygame** : on explore une île en vue de dessus et on lance des **mini-jeux d'arcade** depuis des bornes réparties sur la carte. Chaque partie est sauvegardée avec la position du joueur et ses meilleurs scores.

## ✨ Fonctionnalités

**Menu principal**
- Créer une partie (pseudo + choix du personnage) ou charger une sauvegarde existante
- Fond animé (soleil, palmiers, vagues) et musique

**Exploration**
- Cartes créées avec **Tiled** (`.tmx`), affichées avec `pyscroll` (caméra qui suit le joueur)
- Collisions, zones d'eau et **passages entre les cartes** (maison, laboratoire, centre, boutique…)
- **4 modes de déplacement** avec leurs propres animations : marche, course, vélo, surf (seulement sur l'eau)
- Menu en jeu : meilleurs scores, sauvegarde, retour au menu principal

**5 mini-jeux**, chacun dans une console d'arcade à l'écran :

| Jeu | Particularités |
|---|---|
| **Tetris** | Pièce fantôme, niveaux qui accélèrent, score selon le nombre de lignes |
| **Pac-Man** | Fantômes, super-pastilles pour les manger |
| **Snake** | Murs, bonus clignotants à attraper |
| **Space Invaders** | Ennemis qui accélèrent à chaque niveau, bunkers, boss |
| **Breakout** | Briques générées, effets de particules |

**Autres**
- Sauvegardes en **JSON** (position, carte, personnage, meilleur score par jeu)
- Notifications animées, transitions en fondu entre la carte et les jeux, une musique par écran

## 🎮 Commandes

| Touche | Action |
|---|---|
| Flèches | Se déplacer / jouer |
| `E` | Lancer le mini-jeu à proximité |
| `R` / `B` / `S` | Courir / vélo / surf |
| `M` | Ouvrir le menu en jeu |
| `Échap` | Quitter un mini-jeu |
| `Espace` | Tirer (Space Invaders), lancer la balle (Breakout), faire tomber la pièce d'un coup (Tetris) |
| `↑` (Tetris) | Faire tourner la pièce |

## 🚀 Lancer le jeu

Il faut **Python 3.11 ou plus**.

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

## 📁 Structure

```
code/
├── map_affichage/     # moteur : menu, boucle de jeu, cartes, joueur, sauvegardes
│   ├── main.py        # point d'entrée
│   ├── game.py        # boucle principale, gestion des mini-jeux
│   ├── menu.py        # menu principal
│   ├── map.py         # chargement des cartes Tiled
│   ├── player.py      # joueur, déplacements, menu en jeu
│   └── save_manager.py
└── jeux/              # les 5 mini-jeux + thème graphique + notifications
assets/                # cartes, sprites, musiques
saves/                 # sauvegardes des joueurs
```

## 👥 Auteurs

- Karim Glelah
- Nathan Carton
- Mohamed Hashem
- Tayeb Arroub
