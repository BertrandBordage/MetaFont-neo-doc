************************
Qu'est-ce que MetaFont ?
************************

.. todo::
  Finir cette introduction.

Historique
===========

MetaFont est un langage de programmation permettant de générer des
`fontes de caractères <http://fr.wikipedia.org/wiki/Fonte_de_caract%C3%A8res>`_.
Il fut créé par le mathématicien et informaticien
`Donald Knuth <http://fr.wikipedia.org/wiki/Donald_Knuth>`_ en 1977
en même temps que `TeX <http://fr.wikipedia.org/wiki/TeX>`_,
un logiciel de composition de documents depuis utilisé par
une majeure partie de la communauté scientifique internationale.

.. seealso::
  `Code source du programme MetaFont <http://www.tex.ac.uk/ctan/systems/knuth/dist/mf/mf.web>`_

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

À tout moment, on dispose donc du
`code source <http://fr.wikipedia.org/wiki/Code_source>`_ de la fonte.
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
- `TeX <http://fr.wikipedia.org/wiki/TeX>`_
  et ses variantes (`LaTeX <http://www.latex-project.org/>`_,
  `ConTeXt <http://fr.wikipedia.org/wiki/Context>`_...)
- `LilyPond <http://lilypond.org>`_

Exemples de fontes
==================

- `Computer Modern <http://fr.wikipedia.org/wiki/Computer_Modern>`_
  de TeX
- `Feta <http://lilypond.org/doc/v2.14/Documentation/notation/the-feta-font>`_
  de LilyPond

De MetaFont à OpenType
======================

La création d'une fonte `OpenType <http://fr.wikipedia.org/wiki/OpenType>`_
à l'aide de MetaFont n'est hélas pas simple.
Elle comporte de nombreuses étapes intermédiaires.

Image matricielle → image vectorielle
-------------------------------------

La `compilation <http://fr.wikipedia.org/wiki/Compilation_(informatique)>`_
d'un code source MetaFont permet d'obtenir une ou des images.
Hélas, MetaFont date d'une époque où les imprimantes vectorielles
n'existaient pas.
Le format de sortie est donc
`matriciel <http://fr.wikipedia.org/wiki/Image_matricielle>`_ et non
`vectoriel <http://fr.wikipedia.org/wiki/Image_vectorielle>`_.

Il existe heureusement quelques programmes permettant d'obtenir
des images vectorielles à partir de code MetaFont :

- `METATYPE1 <http://www.ctan.org/tex-archive/fonts/utilities/metatype1/>`_
  (`documentation <http://www.ntg.nl/maps/26/15.pdf>`_),
  script `Perl <http://fr.wikipedia.org/wiki/Perl_(langage)>`_
  par l'équipe polonaise JNS
- `mf2pt1 <http://www.ctan.org/tex-archive/support/mf2pt1/>`_,
  script Perl par Scott Pakin
- `mftrace <http://lilypond.org/mftrace/>`_,
  script `Python <http://fr.wikipedia.org/wiki/Python_(langage)>`_
  par le créateur de LilyPond,
  Han-Wen Nienhuys

Le point commun de ces scripts est l'utilisation de MetaPost.
MetaPost permet en effet de créer des dessins vectoriels
à partir d'un code presque identique à MetaFont.

Images vectorielles → fonte
---------------------------

.. todo::
  Finir cette partie

Il faut principalement utiliser
`FontForge <http://fr.wikipedia.org/wiki/FontForge>`_.
