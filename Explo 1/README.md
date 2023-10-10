##COMPTE RENDU

Suite à quelques explorations avec le WebClient DAT, et une idée de base d'aller récuperer des données sur Internet, j'ai décidé d'utiliser une API pour amasser de l'information sur la
quantité de pollen dans une région donnée. Ainsi, dépendemment de la quantité et du type de pollen, plusieurs particules représentes les données reçues à l'écran. 
Pour faciliter la compréhension et suivre l'idée que j'avais en tête qui était de lui donner une apparence de "greeting meteo", j'ai rajouté un texte au bas du rendu pour donner le facteur
risque reçu par l'api.

Puisque la quantité de caque type de particules doit être indépendante, le patch contient trois systèmes de noises identiques, mais avec une seed différente. Les noises sont connectés aux
geos pour utiliser chaque sample comme donnée pour une particule. Une GRID SOP est utilisées pour modifier la quantité de samples via la quantité de colonnes du SOP. Un resample est inclu
dans le noise system pour lier la grid, transformé en CHOP, au noise de base de chacune des caractéristiques des particules, NÉCÉSSAIRES à l'apparition d'une d'entre elles. Ainsi, seul le
channel X et Y sont affecté par le nombre de sample variables.  

Il y a une chose que j'aurais aimé faire sans succès, donner une apparences plus flotantes aux particules qui monteraient systématiquement vers le haut. Je n'ai pas trouvé de façon fluide
de le faire. Peut-être en jouant avec le offset du noise de la valeur Y, mais il s'agit de reset la valeur de temps a autres pour que les particules restent a l'écran, et ce "seemlessly" qui
m'a freiné dans mon objectif

S'en suit un feedback loop pour fournir une apparence poussiereuse aux particules avec un léger blur.

Cette exploration m'a aidé à comprendre le potentiel infini de l'amassement de données externes pour une oeuvre. Il s'agit d'un example simple, mais l'utilisation d'une API pourrait
éventuellement servir plusieurs fois dans un Workflow, en nourissant la réponse d'une première api à la deuxième et ainsi de suite.

Au courant de l'ajustement des noises et du feedback loop, plusieurs résultats extrêmement différents ont vu le jour. Je pense que ce que j'ai comme noise system est une excellente base pour
tout concept entourant des particules. Petite question sur le coup: est-il possible d'une façon ou d'une autre d'avoir un CHOP a plusieurs samples (comme les noises dans ce cas), mais qui 
contiennent chacun un LFO?
