# 🌊 Wa-Tor

Ce projet est la continuité d'un travail de groupe datant de mai 2024 (voir la rubrique [Origine du projet et remerciements](#origine-du-projet-et-remerciements).)

## Qu'est-ce que Wa-Tor ?

Wa-Tor est une simulation d’écosystème dans un environnement aquatique. Wa-Tor est une « planète » **torique** (comme un donnut représentable par une carte infinie : lorsque l'on dépasse un bord, on se retrouve sur le bord opposé).

![Représentation de la planète Wa-Tor](ressources/planete-wa-tor.jpg)

La planète est entièrement recouverte par un océan dans lequel vivent deux types de poissons : les requins 🦈 et les proies 🐟. Chaque agent (requin ou proie) suit des règles de reproduction, de déplacement et de survie, simulant une dynamique de population dans un contexte de prédation.

Il s'agit d'un écosystème fragile dont la modification de paramètre peut conduire à l'effondrement : l'extinction des requins prédateurs, ou celle des proies et, in fine, celle des prédateurs également.

[Voir la page Wikipedia](https://en.wikipedia.org/wiki/Wa-Tor).

## Wa-Tor, oui, mais avec des paramètres plus riches…

### L'implémentation dans ce projet dépasse les caractéristiques premières de Wa-Tor en proposant un monde plus complexe.

Sur la planète Wa-Tor originale, les poissons se déplacent sur la grille (l'océan) en fonction de leur environnement immédiat. Seule les cases immédiatement limitrophes sont prises en compte : Une proie ne détectera un requin que lorsque celui-ci se trouvera strictement à côté d'elle. De même, un requin ne détectera et ne pourra manger une proie uniquement si elle se trouve dans une case collée à la sienne.

Dans cette planète-ci, les poissons peuvent être plus évolués et détecter les prédateurs ou les proies à plus ou moins grande distance, qui va d'une case à… l'ensemble de la carte. Et ça peut tout changer !

## 🔧 Installation et configuration requise

Ce projet nécessite Git et Python 3.7 ou plus récent (développement effectué avec Python 3.13).

Récupération du dépôt (via le lien public en https) et installation sous Linux/macOS  :

```bash
# récupération du dépôt dans un nouveau sous-répertoire au répertoire courant :
git clone https://github.com/alexishs/Wa-Tor.git
# Le dépôt est téléchargé dans le répertoire créé Wa-Tor.
# On se déplace dans ce sous-répertoire :
cd ./Wa-Tor
# Configuration de l'environnement avec venv :
python -m venv .venv
source .venv/bin/activate
# Installation des dépendances avec PIP
pip install -r requirements.txt
``` 

## Version en mode texte

La version en **mode texte** (wa-tor-cli.py) peut être exécuté avec la commande :
```bash
python wa-tor-cli.py 
``` 
La liste des paramètres disponibles peut être rappelée avec cette commande :
```bash
python wa-tor-cli.py -h
```
### ⚙️ Arguments disponibles

 * --menu
        default=OUI,
        Afficher le menu (OUI ou NON)

 * --auto, -a [str]
        default=NON
        Automatiser la simulation (OUI ou NON)

 * --chronon, -c [int]
        default=100
        Nombre d'étapes de simulation si activation paramètre --auto=OUI (cycle de vie)

 * --hauteur, -H [int]
        default=30
        Nombre de lignes dans la grille

 * --largeur, -l [int]
        default=30
        Nombre de colonnes dans la grille

 * --nb-proie, -p [int]
        default=40
        Nombre de proies à placer dans la grille

 * --nb-requin, -r [int]
        default=15
        Nombre de requins à placer dans la grille

 * --cycle-reproduction-requin [int]
        default=12
        Nombre de cycles entre chaque reproduction des requins

 * --cycle-reproduction-proie [int]
        default=8
        Nombre de cycles entre chaque reproduction des proies

 * --visibilite-requin [int]
        default=1
        Distance en cellules pour la vision des requins

 * --visibilite-proie [int]
        default=1
        Distance en cellules pour la vision des proies

 * --vue_arriere-requin [str]
        default=OUI
        Capacité des requins à détecter les proies à distance derrière eux

 * --vue_arriere-proie [str]
        default=OUI
        Capacité des proies à détecter les requins à distance derrière eux

 * --points-de-vie-requin [int]
        default=12
        Points de vie du requin (réduit de 1 à chaque cycle)

 * --points-par-repas-requin [int]
        default=6
        Points de recharge par proie mangée

## Version avec interface graphique en pygame :
```bash
python wa-tor-gui.py 
```

## 📁 Structure du projet
```plaintext
Wa-Tor/
├── wa-tor-cli.py          # Script principal pour exécuter la simulation en ligne de commande
├── main_pygame.py         # Script principal pour exécuter la simulation avec interface pygame
├── requirements.txt       # Fichier listant les dépendances nécessaires
├── README.md              # Documentation du projet
├── monde.py               # Module définissant la logique de simulation
├── ocean.py               # Module définissant la grille du jeu
├── poisson                # Module parent de proie et requins définissant leur logiques communes
├── proie.py               # Module définissant la classe proie
├── requin.py              # Module définissant la classe requin
└── assets/                # Dossier pour les ressources (images, sons, etc.)
    └── sprites/           # Dossier pour les sprites utilisés dans pygame
```

## Origine du projet et remerciements

Ce projet est, à l'origine, un travail de groupe dans le cadre d'une formation à Python effectué à [Simplon Hauts-de-France](https://www.simplon.co/) qui a été rendu le vendredi 16 mai 2025.

Ce dépot est un fork du dépot commun https://github.com/Flockyy/Wa-Tor qui a été conjointement créé
avec [Florian (Flockyy)](https://github.com/Flockyy) et [Vincent (CVincent27)](https://github.com/CVincent27).

***Tous les commits effectués jusqu'au 15/05/2025 sont issus du travail en commun.*** 

La branche [projet-avant-fork](https://github.com/alexishs/Wa-Tor/tree/projet-avant-fork) est une archive du travail effectué en commun.

### 🤝👥 Contributions dans le projet commun d'origine

Tout le monde a plus ou moin touché à toutes les fonctionalités mais dans les grandes lignes :

- Alexis
    - Monde
    - Ocean
    - Poisson
    - Proie
    - Requin
    - Spécificités de la version CLI
- Florian
    - Monde
    - Ocean
    - Spécificités de la version CLI,
    - Spécificités de la version Pygame
- Vincent 
    - Poisson
    - Proie
    - Requin
    - Monde