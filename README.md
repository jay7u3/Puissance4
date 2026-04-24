# Puissance 4

Jeu de Puissance 4 développé en Python avec une interface graphique Pygame. Le projet permet de jouer contre plusieurs adversaires contrôlés par l'ordinateur, dont une IA basée sur l'algorithme Minimax et un mode aléatoire.

## Description du projet

Ce dépôt contient une implémentation graphique du Puissance 4 :

- plateau de 6 lignes par 7 colonnes ;
- interface en fenêtre avec assets graphiques et effets sonores ;
- détection des victoires horizontales, verticales et diagonales ;
- détection du match nul ;
- plusieurs niveaux d'ordinateur basés sur une profondeur de recherche Minimax ;
- mode "monkey" qui joue une colonne valide au hasard.

Le joueur place ses jetons à la souris. L'ordinateur évalue ensuite les coups possibles grâce à une fonction de score prenant en compte le contrôle du centre, la hauteur des jetons et les alignements potentiels.

## Installation

### Prérequis

- Python 3
- `pip`
- Pygame

### Mise en place

Clonez le dépôt puis placez-vous dans le dossier du projet :

```bash
git clone <url-du-depot>
cd Puissance4
```

Il est recommandé d'utiliser un environnement virtuel :

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install pygame
```

> Le jeu charge ses images et sons avec des chemins relatifs. Lancez donc les commandes depuis la racine du projet.

## Utilisation

Démarrez le jeu avec :

```bash
python3 main.py
```

Depuis le menu principal, cliquez sur un niveau pour lancer une partie :

- `Niveau 1` : IA Minimax avec une recherche moins profonde ;
- `Niveau 2` : IA Minimax intermédiaire ;
- `Niveau 3` : IA Minimax plus profonde ;
- bouton `monkey` : adversaire aléatoire.

Pendant une partie :

- cliquez sur une colonne pour y déposer un jeton ;
- le jeton tombe automatiquement dans la case libre la plus basse ;
- le bouton pause en haut à droite permet de revenir au menu ;
- la partie se termine lorsqu'un joueur aligne quatre jetons ou lorsque le plateau est plein.

## Structure du projet

```text
Puissance4/
├── main.py              # Point d'entrée, interface Pygame et boucle de jeu
├── ordinateur_level.py  # Recherche Minimax et choix du meilleur coup
├── evaluation.py        # Fonction d'évaluation d'une position
├── monkey_level.py      # Choix aléatoire d'une colonne valide
├── ressources/          # Images et sons utilisés par l'interface
└── README.md
```

## Exemples

### Lancer une partie

```bash
python3 main.py
```

### Installer la dépendance principale

```bash
pip install pygame
```

### Utiliser le choix aléatoire dans un script Python

```python
from monkey_level import monkey_choice

plateau = [[0] * 7 for _ in range(6)]
colonne = monkey_choice(plateau)
print(f"Colonne jouée : {colonne}")
```

### Demander un coup à l'IA Minimax

```python
from ordinateur_level import coup_ordinateur

plateau = [[0] * 7 for _ in range(6)]
ligne, colonne = coup_ordinateur(plateau, profondeur=2, coup=1)
print(f"Coup proposé : ligne={ligne}, colonne={colonne}")
```

## Dépendances

Le projet utilise :

- `pygame` : affichage graphique, gestion des événements, images et sons ;
- modules standards Python : `random`, `time`, `sys`, `copy`.

Aucun fichier `requirements.txt` n'est présent dans le dépôt. Pour reproduire l'environnement minimal :

```bash
pip install pygame
```

## Licence

Aucune licence n'a été détectée dans le dépôt. Par défaut, le code reste sous copyright de ses auteurs tant qu'une licence explicite n'est pas ajoutée.
