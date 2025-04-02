# État de l’art : Diagrammes d’Influence et Diagrammes d’Influence à Mémoire Limitée 
## 1. Introduction 
Dans le cadre de ce projet, on cherche a résoudre un diagramme d'influence (trouver les decisions optimales pour maximiser une fonction utilité). mais, on remarque que cela est une tache qui croît exponentiellement en complexité si on souhaite une solution exacte.
Le but des diagrammes d'influence est trouver des strategies optimales a prendre sous incertitude, cela en prenant toute option precedente en consideration ("no forgetting"), D'ou l'utilité des LIMIDs (limited memory influence diagrams).
Dans ce document, on cherche a introduire les concepts que l'on va exploiter dans tout ce qui suit, et d'explorer les methodes existantes pour resoudre les LIMIDs.
## 2. Fondements théoriques 
### 2.1. Réseaux bayésiens 
Définition et structure : 
Les résaux Bayesiens sont la base sur laquelle on s'appuie pour resoudre notre tache, en eux mêmes, ils servent a modeliser les dependances entre variables aleatoires sous la forme d'un graphe (DAG, directed acyclical graph) ce qui sert a simplifier et structuriser le calcul de certaines probabilités dans le réseau. 
Ils sont modelisés graphiquement par:
- Des noeuds : representant les variables aleatoires dans notre systeme
- Des arcs : representant la dependance entre les variables en question 
### 2.2. Diagrammes d’influence
Définition : 
Les diagrammes d'influence (IDs) sont une extension des réseaux bayésiens pour la prise de décision sous incertitude. Ils permettent de modeliser une situation de prise de decision en vue de trouver la solution optimale.
Structure :
Types de noeuds : 
- **Chance nodes** : les variables aléatoires
- **Decision nodes** : les décisions qui peuvent être prises 
- **Utility nodes** : la fonction qu'on a pour but de maximiser
Méthodes de résolution : 
- Programmation dynamique : (inference exacte pour structure en forme d'arbre) stocker l'esperance de la fonction utilité sachant la realisation des enfants, puis se baser sur cette valeur pour obtenir une MEU (maximum expected utility) et ennumerer les décisions pour trouver la strategie optimale.
### 2.3. Limited Memory Influence Diagrams
Définition : 
Bien que les IDs font une très bonne base de modelisation des problèmes de prise de decision, les contraintes de mémoire et de dépendances rendent les algorithmes de resolution de plus en plus complexes. C'est ici qu'on souhaite relaxer ces contraintes pour en faire des modeles plus efficaces, cependant, pour cela le decision maker (DM) a besoin d'informations locales pour faire les decisions, ce qui pose un nouveau probleme : l'optilisation des polices locales et de definir l'information necessaire et suffisante pour faire une certaine decision.
Donc notre but final est de calculer $MEU = max_\Delta \mathbb{E}[\sum\limits_{i} U_i]$ (l'esperance maximale des fonction utilité etant donnés une certaine decision)
## 3. Algorithmes connus pour resoudre les LIMIDs 
L'algorithme traditionnel pour resoudre un LIMID (ennumeration des decisions) est exponentiel en complexité temporelle et spaciale.
(all that follows are bullet points to fill out later)
- local policy update
- submodel-tree decomposition 
- Marginal MAP (MMAP) through Generalised Dual Decomposition (GDD) and Weighted Mini-Bucket (WMB)
- error bounds (approximal inference)
## 4. Pistes pour l’implémentation d’un algorithme de division en sous-modèles 
- message passing between smaller (computationally simple) models and main model to simplify the problem and avoid redundant computation
- approximating MEU in probabilistic
- relax conditions without losing too much accuracy
## 5. Conclusion 
## 6. Références 
(les articles a ajouter) (is this needed?)

https://docs.google.com/document/d/15OAPzBZ9CiiqbCzqmkgywevDu1jxqOXgZGQ6oIA9gs4/edit?usp=sharing
