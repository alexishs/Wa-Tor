# 🌊 Wa-Tor – Simulateur de monde aquatique

Wa-Tor est une simulation d’écosystème dans un environnement aquatique. Le monde est représenté par une grille torique où vivent deux types d'agents : les poissons 🐟 et les requins 🦈. Chaque agent suit des règles de reproduction, de déplacement et de survie, simulant une dynamique de population.

## 🔧 Requirements

Ce projet nécessite Python 3.7 ou plus récent. Pour installer les dépendances :

```bash
pip install -r requirements.txt
``` 

## Version en mode texte

### ⚙️ Arguments disponibles

La version en **mode texte** (wa-tor-cli-) peut être exécuté avec les arguments suivants :

#### --menu

default=OUI,
Afficher le menu (OUI ou NON)

#### --auto, -a [str]

default=NON
Automatiser la simulation (OUI ou NON)

#### --chronon, -c [int]

default=100
Nombre d'étapes de simulation si activation paramètre --auto=OUI (cycle de vie)

#### --hauteur, -H [int]

default=30
Nombre de lignes dans la grille

#### --largeur, -l [int]

default=30
Nombre de colonnes dans la grille

#### --nb-proie, -p [int]

default=40
Nombre de proies à placer dans la grille

#### --nb-requin, -r [int]

default=15
Nombre de requins à placer dans la grille

#### --cycle-reproduction-requin [int]

default=12
Nombre de cycles entre chaque reproduction des requins

#### --cycle-reproduction-proie [int]

default=8
Nombre de cycles entre chaque reproduction des proies

#### --visibilite-requin [int]

default=1
Distance en cellules pour la vision des requins

#### --visibilite-proie [int]

default=1
Distance en cellules pour la vision des proies

#### --vue_arriere-requin [str]

default=OUI
Capacité des requins à détecter les proies à distance derrière eux

#### --vue_arriere-proie [str]

default=OUI
Capacité des proies à détecter les requins à distance derrière eux

#### --points-de-vie-requin [int]

default=12
Points de vie du requin (réduit de 1 à chaque cycle)

#### --points-par-repas-requin [int]

default=6
Points de recharge par proie mangée

### ▶️ Exemple d'utilisation
Exécution dans le terminal (les paramètres ci-dessus peuvent être appliqué) :
```bash
python wa-tor-cli.py 
``` 
La liste des paramètres disponibles peut être rappelée avec cette commande :
```bash
python wa-tor-cli.py -h
```

## Exécution avec interface en pygame :
```bash
python main_pygame.py 
``` 

## 📁 Structure du projet
```plaintext
Wa-Tor/
├── main.py                # Script principal pour exécuter la simulation en ligne de commande
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

Ce projet est, à l'origine, un travail de groupe dans le cadre d'une formation à Python effectué à [Simplon Hauts-de-France](https://www.simplon.co/).

Ce dépot est un fork du dépot commun https://github.com/Flockyy/Wa-Tor qui a été conjointement créé
avec [Florian - Flockyy](https://github.com/Flockyy) et [Vincent - CVincent27](https://github.com/CVincent27).

***Tous les commits effectués jusqu'au 15/05/2025 sont issus du travail en commun.*** 

La branche [projet-avant-fork](https://github.com/alexishs/Wa-Tor/tree/projet-avant-fork) est une archive du travail effectué en commun.
## 🤝👥 Membres et contributions

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

