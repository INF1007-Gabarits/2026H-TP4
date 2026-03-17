# TP4 - Analyse de donnees sur les jeux Steam avec des librairies scientifiques

## Directives
:alarm_clock: Date de remise : 12 avril 2026 à 23:59

A remettre sur Github (la correction peut se baser sur votre dernier `git push` effectue avant la date limite).

## Introduction
Vous etes analyste de donnees pour une equipe qui etudie le marche des jeux video sur Steam. Vous disposez d'une base de donnees `steam_games_dataset.csv` contenant des informations sur 10 000 jeux, notamment :

- `appid` : identifiant unique du jeu
- `name` : nom du jeu
- `developer` : studio de developpement
- `publisher` : editeur
- `score_rank` : rang de score (souvent vide)
- `positive` et `negative` : nombre d'evaluations positives et negatives
- `owners` : estimation du nombre de proprietaires
- `average_forever` et `average_2weeks` : temps de jeu moyen en minutes
- `median_forever` et `median_2weeks` : temps de jeu median en minutes
- `price` et `initialprice` : prix en cents
- `discount` : pourcentage de rabais
- `ccu` : nombre de joueurs simultanes

Votre objectif est de nettoyer cette base de donnees, d'en extraire des statistiques descriptives et de la visualiser a l'aide de representations graphiques. Pour ce faire, vous serez amenes a utiliser les librairies Python suivantes :

- Pandas : pour manipuler des donnees tabulaires avec des DataFrames.
- NumPy : pour effectuer des traitements numeriques et creer des colonnes conditionnelles.
- Matplotlib : pour produire des graphiques 2D personnalises.
- Seaborn : pour realiser facilement des visualisations statistiques.
- Plotly : pour creer des graphiques interactifs.

Pour ce TP, nous allons travailler avec un Jupyter Notebook (`.ipynb`).

## Qu'est-ce qu'un Jupyter Notebook ?
Un Jupyter Notebook est un environnement interactif utilise pour ecrire et executer du code, ainsi que pour visualiser des resultats en temps reel. Il permet d'integrer a la fois du code, des commentaires textuels (Markdown), des visualisations et des equations mathematiques.

### Structure d'un Jupyter Notebook
Un notebook se compose de cellules qui peuvent etre :

- Cellules de code : ou vous ecrivez et executez du code Python.
- Cellules Markdown : ou vous ajoutez des explications, des descriptions ou des notes en utilisant le langage Markdown.

### Comment ca fonctionne
Lorsqu'un Jupyter Notebook est ouvert, vous pouvez executer chaque cellule individuellement, ce qui permet une execution etape par etape. Les resultats (comme les graphiques ou les variables calculees) sont affiches directement sous la cellule de code.

Il est egalement possible d'executer toutes les cellules l'une a la suite de l'autre avec le bouton "Run All" dans VS Code.

## Installations requises
Avant de debuter ce TP, vous devez installer Jupyter ainsi que l'extension de Jupyter Notebook dans VS Code.

1. Pour installer Jupyter, ouvrez un nouveau terminal dans VS Code et entrez la commande suivante :

```bash
pip install jupyter
```

2. Ensuite, installez l'extension Jupyter, si ce n'est pas deja fait, dans VS Code :

- Allez a l'icone des extensions dans la barre laterale de gauche.
- Recherchez Jupyter.
- Installez l'extension Jupyter developpee par Microsoft.

Elle devrait ressembler a ceci :
![image](../images/jupyter.png)

Si vous devez revenir a une version precedente de l'extension, vous pouvez suivre le meme principe que dans l'exemple ci-dessous :
![image](../images/Exemple_jupyter_2.png)

Une fois Jupyter et l'extension installes, vous pouvez ouvrir le notebook `TP4.ipynb` dans ce dossier et suivre les instructions.

Vous devrez egalement installer les librairies Pandas, NumPy, Matplotlib, Seaborn et Plotly. Les instructions d'installation se retrouvent dans le notebook `TP4.ipynb`.

## Instructions pour le TP
Les etapes detaillees et les instructions pour realiser ce TP sont disponibles dans le Jupyter Notebook `TP4.ipynb`.

### Resultats attendus pour les exercices du TP
- Partie 1 : votre DataFrame final ne devrait plus contenir les colonnes `score_rank` et `userscore`. La colonne `owners` devrait avoir ete transformee en borne minimale numerique, et les colonnes `Type_prix`, `Etat_rabais` et `prix_dollars` devraient etre presentes.
- Partie 2 : vos tableaux statistiques devraient etre retournes sous forme de DataFrames bien structures, avec des colonnes explicites et des proportions affichees en pourcentage.
- Partie 3 : vous devriez produire deux barplots Seaborn sur les editeurs/developpeurs les plus frequents, puis un nuage de points interactif Plotly sur les evaluations positives et negatives avec axes logarithmiques.

## Bareme de correction

Le bareme de correction pour ce TP est le suivant :

| **Partie** | **Tache** | **Points** |
|---|---|---:|
| **Partie 1 : Chargement et nettoyage des donnees avec pandas** |  | **/6** |
|  | 1.1 Completer la fonction `charger_donnees` | 1 |
|  | 1.2 Utiliser `charger_donnees` pour obtenir le DataFrame | 0.5 |
|  | 1.3 Affichage du DataFrame | 0.5 |
|  | 1.4 Completer la fonction `supprimer_colonnes` | 1 |
|  | 1.5 Utiliser `supprimer_colonnes` pour supprimer les colonnes `score_rank` et `userscore` | 0.5 |
|  | 1.6 Affichage du DataFrame modifie | 0.5 |
|  | 1.7 Completer la fonction `convertir_owners_min` | 1 |
|  | 1.8 Utiliser `convertir_owners_min` pour transformer `owners` | 0.5 |
|  | 1.9 Creation des colonnes derivees avec NumPy et affichage | 0.5 |
| **Partie 2 : Calcul des statistiques** |  | **/5** |
|  | 2.1 Affichage du nombre de jeux par categorie | 1 |
|  | 2.2 Completer la fonction `stats_par_groupe` | 1 |
|  | 2.3 Affichage des statistiques avec `stats_par_groupe` (3 affichages a 0.5 chacun) | 1.5 |
|  | 2.4 Completer la fonction `proportion_jeux_bien_notes_par_type_prix` | 1 |
|  | 2.5 Affichage du DataFrame avec proportions (%) | 0.5 |
| **Partie 3 : Visualisation des donnees** |  | **/9** |
|  | 3.1 Diagrammes en barres horizontales avec Seaborn | 5 |
|  | 3.2 Nuage de points interactif avec Plotly | 4 |
| **Bonus** | Question bonus | +1 |
| **Total** |  | **/20** |

*A noter que la note maximale est de 100 % (donc si vous avez 20/20 + 1 point bonus, vous aurez quand meme 20/20 sur le TP).*
