************************
Qu'est-ce que MetaFont ?
************************

.. todo::
    Finir cette introduction.

Historique
===========

MetaFont est un langage de programmation permettant de générer des
`fontes de caractères <http://fr.wikipedia.org/wiki/Fonte_de_caract%C3%A8res>`_.
Il fut créé par le mathématicien et informaticien `Donald Knuth <http://fr.wikipedia.org/wiki/Donald_Knuth>`_ en 1977 en même temps que `TeX <http://fr.wikipedia.org/wiki/TeX>`_, un logiciel de composition de documents depuis utilisé par une majeure partie de la communauté scientifique internationale.


Principe de fonctionnement
==========================

Jusqu'au XX\ :sup:`e` siècle, les poinçons des caractères étaient
réalisés dans des moules.
Les centaines de moules d'une fonte n'étaient toutefois créés
qu'après de longues étapes de calculs et dessins.

Qu'elle soit donc réalisée avec ou sans MetaFont, une fonte de caractères
doit une grande partie de sa lisibilité à l'*uniformisation*
entre ses caractères.
En effet, une fonte dont le « e » n'aurait pas la même taille
que le « a » pourrait vite devenir illisible.

Voici quelques uniformisations indispensables :

- forme
- hauteur
- épaisseur
- inclinaison (pour
  l'`italique <http://fr.wikipedia.org/wiki/Italique_(typographie)>`_)
- diamètre des
  `empattements <http://fr.wikipedia.org/wiki/Empattement_(typographie)>`_ 

MetaFont propose une solution simple pour effectuer proprement ces uniformisations.
L'idée est de considérer chacune des contraintes citées précédemment
comme une variable.
Ces variables peuvent être liées entre elles par des équations
plus ou moins complexes.
Cela permet de générer des fontes de différentes tailles (12, 14, 16, 18 
`points <http://fr.wikipedia.org/wiki/Point_(unit%C3%A9)>`_, etc),
différents poids (léger, normal, semi-gras, gras, etc),
différentes densités (condensé, normal, etc)...

Exemple simple :
  Pour plus de lisibilité, on souhaite que les tailles les plus petites
  de la fonte aient des caractères proportionnellement plus épais.
  Il faut donc créer une équation qui liera la taille à l'épaisseur, du type :
  :math:`epaisseur = 0.5 pt + \frac{hauteur}{60}`

C'est là la grande force de MetaFont.
On ne conserve pas uniquement le rendu final ou même le résultat
des nombreux calculs de fonte.
On ne conserve que les équations ayant permis de mettre au point la fonte.
MetaFont se charge de trouver les solutions des équations puis d'en faire
une fonte utilisable.

À tout moment, on dispose donc du `code source <http://fr.wikipedia.org/wiki/Code_source>`_
de la fonte.
Ainsi, si on désire réduire l'inclinaison de l'italique, il suffit de changer
un seul paramètre pour que le changement s'effectue sur tous les caractères
de la fonte.


Forces et faiblesses
====================

:Forces:
  * Écrire un minimum d'équations pour un maximum de résultats
  * Aucun bug connu
  * Conservation de la procédure et non du résultat
      - rigueur scientifique
      - modifier une étape modifiera toute la fonte en conséquence
      - pérennité

:Faiblesses:
  * Documentation difficilement abordable
  * Monochrome uniquement
  * Requiert les talents de designer, mathématicien et informaticien

Projets utilisant MetaFont
==========================

- `MetaPost <http://fr.wikipedia.org/wiki/MetaPost>`_
- Les fontes de caractères de `TeX <http://fr.wikipedia.org/wiki/TeX>`_
  et toutes ses variantes (`LaTeX <http://www.latex-project.org/>`_,
  `ConTeXt <http://fr.wikipedia.org/wiki/Context>`_...)
- Les fontes Feta et Parmesan de `LilyPond <http://lilypond.org>`_
