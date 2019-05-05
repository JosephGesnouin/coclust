# Coclustering: gènes et maladies
La plupart des études d’association se limitent souvent à la mise en évidence d’un lien entre un groupe de gènes G et une maladie. Cependant, l’étape suivante est l’étude des interaction entre les gènes de G pour mieux comprendre comment ces gènes coopèrent pour provoquer l’apparition d’une maladie ou d’un phénotype.

La présentation de la solution se présente sous forme d'une interface graphique Web utilisant le framework Flask disponible [ici](insert_liens_site)

On a un ensemble G de k gènes suspectés d’être associés à une maladie et on construit des représentations vectorielles de ces gènes. Pour étudier ces interactions, nous avons utilisé des techniques de clustering hiérarchique sur le groupe G étudié ainsi que des techniques de co-clustering afin d’obtenir automatiquement des ensembles de termes
descripteurs pour chacun des sous-groupes identifiés au sein du groupe étudié G.

## Datasets
Dans le but d’être le plus précis possible et d'obtenir un nombre de noms de maladies et de gênes conséquents, il aura fallu prendre en considération de nombreuses bases de données: en particulier, si l’on souhaite concevoir une base de données beaucoup plus grande. C’est ce que nous avons réalisé dans le cadre de ce projet. Les bases de données utilisées sont nombreuses:
* Online Mendelian Inheritance in Man (OMIM)
* Diseases
* Gene Ontology (GO)
* Entrez-Gene (EG)
* Pubmed

L’utilisation de toutes ces bases de données nous aura permis d’isoler une multitude de noms de maladies et de gènes grâce à des traitements de text-mining: nous disposions d’une liste assez conséquente des maladies et gènes existants. Ainsi, nous disposions d’environ 4 000 maladies différentes et de 16 000 gènes.


## Named Entity Recognition
En plus des noms de maladies et de gènes isolés grâce aux datasets précédents, un NER (Spacy) aura été lancé sur les fichiers asthma et autism afin d'aggrémenter le jeu de données de nouvelles maladies et de nouveaux gênes, le NER est également disponible sur le site pour experimentation.

## Coclust
Nous avons utilisé la bibliothèque [Coclust](https://github.com/franrole/cclust_package/tree/master/datasets) pour le co-clustering ainsi que [Scikit](https://scikit-learn.org/stable/) pour le clustering hiérarchique.

Afin d'être le plus dynamique possible, l'interface permet:
* De sélectionner la maladie concernée et de spécifier la liste des gènes G correspondant à cette maladie.
* De calculer et d’afficher une matrice de similarités pairwise entre les gènes du groupe G ainsi que le
boxplot correspondant.
* De déclencher et d’afficher les résultats d’un clustering hiérarchique (en justifiant le choix du critère d’agrégation) sur la matrice des vecteurs de gènes de G.
* De déclencher et d’afficher les résultats d’un co-clustering sur la matrice des vecteurs de gènes de G,
avec possibilité de choisir entre les différentes méthodes disponibles dans la bibliothèque Coclust.

### Approches proposées
Différentes approches pour le co-clustering sont proposées:
#### Gene Gene
Une approche Gene Gene,
#### Gene Terme
Une approche Gene Terme,
#### Gene Article
Une approche Gene Article,

## Références
