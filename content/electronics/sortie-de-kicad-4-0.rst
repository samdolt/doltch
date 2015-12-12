Sortie de KiCad 4.0
###################

:authors:   Samuel
:date:      2015-03-09T22:13:42+01:00
:slug:      electronics/sortie-de-kicad-4-0
:category: Électronique
:tags:    kicad, électronique, schém

.. note::

   Article repris depuis le site LinuxFr.org_. Merci à osfe, BAud,
   palm123, Lucas, Xavier Claude, Snark, teoB, Xavier Teyssier,
   Benoît Sibaud, Nicolas Boulay, jcr83, PolePosition, ZeroHeure 
   et cévhé, qui ont participé avec moi à la rédaction de cette
   article.

   Licence `CC BY-SA`_


Le 29 novembre 2015, la quatrième version du projet KiCad a été publiée.

Commençons par une courte présentation, tirée de `l'article
Wikipédia <https://fr.wikipedia.org/wiki/KiCad>`__::

   KiCad est un ensemble de logiciels libres de conception
   pour l'électronique pour le dessin de schémas électroniques
   et la conception de circuits imprimés.

.. image:: http://kicad-pcb.org/img/kicad_logo_small.png
   :alt: Logo de Kicad
   :width: 100px


Cet ensemble offre principalement un gestionnaire de projet, un éditeur
de schémas, un éditeur de circuits imprimés gérant jusqu'à 32 couches de
cuivre, une visionneuse de fichier
`gerber <http://fr.wikipedia.org/wiki/Gerber_(format_de_fichier)>`__ et
une calculatrice d'aide à la conception. Le logiciel a été créé en 1992
par Jean-Pierre Charras, professeur à l'IUT de Saint-Martin-d'Hères.

Les sources ont été publiées sous licence GPL dans le début des années
2000 et ont été depuis constamment améliorées par une équipe de
développement bénévole. Depuis 2013, le
`CERN <http://home.web.cern.ch/fr>`__ s'investit dans le développement
du logiciel, en récoltant des dons et en mettant à disposition `des
développeurs <http://www.ohwr.org/projects/cern-kicad/>`__.

Côté technique, le cœur du logiciel est codé en C++ et utilise la
bibliothèque `wxWidget 3 <https://www.wxwidgets.org/>`__. Il est
également possible d'écrire des extensions en Python.

--------------

- `Site officiel <http://www.kicad-pcb.org/>`__
- `Téléchargement <http://kicad-pcb.org/download/>`__ `Faire un don <https://giving.web.cern.ch/civicrm/contribute/transact?reset=1&id=6>`__
- `Contribution du CERN <http://home.web.cern.ch/fr/about/updates/2015/02/kicad-software-gets-cern-treatment>`__
- `Documentation <http://kicad-pcb.org/help/documentation/>`__
- `Présentation du routage en mode « Push and shove » <https://www.youtube.com/watch?v=CCG4daPvuVI>`__ `Présentation du routage de pistes à longueur controllée <https://www.youtube.com/watch?v=chejn7dqpfQ>`__
- `Présentation du routage de paires différentielles <https://www.youtube.com/watch?v=chejn7dqpfQ>`__

--------------

Présentation des différents composants Kicad
============================================

Eeschema, l'éditeur de schémas
------------------------------

.. image:: http://kicad-pcb.org/img/screenshots/mint_eeschema.png
   :alt: Eeschema

La première étape dans la conception d'un circuit électronique est d'en
dessiner le `schéma
électrique <https://fr.wikipedia.org/wiki/Sch%C3%A9ma_%C3%A9lectrique>`__.

Eeschema, l'éditeur de schémas de Kicad, permet donc de représenter les
différents composants électroniques utilisés dans le projet et leurs
connexions.

Le logiciel propose deux paradigmes différents pour la représentation
d'un circuit :

1. Schéma simple-page
2. Schéma hiérarchique

Un schéma simple-page tient dans une seule page et n'utilise pas de
sous-circuits.

Un schéma hiérarchique est composé de plusieurs pages, représentant des
sous-circuits, qui peuvent ensuite être réutilisés facilement. Un peu à
l'image de la séparation d'un code source en plusieurs fichiers.

La capture d'eeschema ci-dessus nous montre un schéma hiérarchique. En
effet, si on regarde attentivement, on aperçoit sur la droite un bloc
« Sheet pic\_socket » qui renvoie vers le fichier « pic\_socket.sch ».

Création de bus
~~~~~~~~~~~~~~~

L'outil permet aussi de créer des bus, fonctionnalité qui permet de
regrouper plusieurs équipotentielles en un seul et même fil. Cette
fonction permet aussi de rendre le schéma plus clair et donc plus simple
à lire.

Génération de liste de composants
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Une fois la carte conçue et fabriquée, il faut alors commander puis
souder les composants sur la carte. Pour une petite carte avec quelques
composants un traitement manuel suffit amplement. Cependant, pour une
carte avec plusieurs centaines de composants, cette tâche peut vite
devenir fastidieuse. Kicad permet de générer une liste de pièces,
appelée `BOM <https://en.wikipedia.org/wiki/Bill_of_materials>`__ (*Bill
Of Material*), qui est la liste des composants présents sur la carte.
Ceci facilite grandement la commande des composants et le câblage
(soudage des composants sur la carte) de la carte. Cette BOM peut être
générée sous plusieurs formes différentes grâce à un système de greffon
écrit en XML.

Éditeur circuits imprimés (*layout*) -- pcbnew
----------------------------------------------

.. image:: http://kicad-pcb.org/img/screenshots/mac_pcbnew.png
   :alt: Pcbnew

L'éditeur de circuit imprimé ou *layout* en anglais permet d'éditer des
cartes jusqu'à 32 couches de cuivre et sans limite de dimension. Le CERN
qui contribue désormais de manière très active au développement du
logiciel a apporté des fonctionnalités très importantes comme la
longueur contrôlée des équipotentielles (*length matching*), le routage
différentiel ou le routage assisté (*push and shove*).

Visionneuse de films de fabrication -- GerbView
-----------------------------------------------

|GerbView| KiCad permet l'export au format
`Gerber <https://fr.wikipedia.org/wiki/Gerber_%28format_de_fichier%29>`__,
le format standard pour la transmission de donnée à une usine de
fabrication de circuit imprimé. L’outil GerbView permet de visionner les
fichiers produit, afin d'y détecter les erreurs éventuelles avant
l'envoi en fabrication du circuit.

Calculatrice d'aide à la conception
-----------------------------------

.. image:: http://kicad-pcb.org/img/screenshots/calc_rf.png
   :alt: Pcb Calculator

Visualisateur 3D
----------------

Kicad intègre un module de visualisation, permettant d'inspecter un
circuit en 3D.

.. image:: http://kicad-pcb.org/img/frontpage/kicad_3dviewer.png
   :alt: Kicad 3D Viewer

Nouveautés de la version 4
==========================

PcbNew
------

Durant le développement de cette nouvelle version, les développeurs de
KiCad se sont concentrés sur « pcbnew », le module de création et de
routage de circuits imprimés.

Nouveaux formats de fichiers
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Le format de fichier pour les empreintes de composants et pour les
circuits imprimés a été remplacé par un format maison basé sur la
syntaxe `S-expression <http://fr.wikipedia.org/wiki/S-expression>`__.

.. code:: lisp

    (module R_0805 (layer F.Cu) (tedit 5415CDEB)
      (descr "Resistor SMD 0805, reflow soldering, Vishay (see dcrcw.pdf)")
      (tags "resistor 0805")
      (attr smd)
      (fp_text reference R_0805 (at 0 -2.1) (layer F.SilkS)
        (effects (font (size 1 1) (thickness 0.15)))
      )
      (fp_text value VAL** (at 0 2.1) (layer F.SilkS)
        (effects (font (size 1 1) (thickness 0.15)))
      )
      (fp_line (start -1.6 -1) (end 1.6 -1) (layer F.CrtYd) (width 0.05))
      (fp_line (start -1.6 1) (end 1.6 1) (layer F.CrtYd) (width 0.05))
      (fp_line (start -1.6 -1) (end -1.6 1) (layer F.CrtYd) (width 0.05))
      (fp_line (start 1.6 -1) (end 1.6 1) (layer F.CrtYd) (width 0.05))
      (fp_line (start 0.6 0.875) (end -0.6 0.875) (layer F.SilkS) (width 0.15))
      (fp_line (start -0.6 -0.875) (end 0.6 -0.875) (layer F.SilkS) (width 0.15))
      (pad 1 smd rect (at -0.95 0) (size 0.7 1.3) (layers F.Cu F.Paste F.Mask))
      (pad 2 smd rect (at 0.95 0) (size 0.7 1.3) (layers F.Cu F.Paste F.Mask))
      (model Resistors_SMD/R_0805.wrl
        (at (xyz 0 0 0))
        (scale (xyz 1 1 1))
        (rotate (xyz 0 0 0))
      )
    )

L'exemple ci-dessus représente une résistance SMD de type 0805 :

+--------------+--------------+
| Rendu 2D     | Rendu 3D     |
+==============+==============+
| |Rendu 2D|   | |Rendu 3D|   |
+--------------+--------------+

Nouveau moteur de rendu 2D
~~~~~~~~~~~~~~~~~~~~~~~~~~

L'équipe du CERN a aidé à développer un nouveau moteur de rendu pour
PcbNew, destiné à remplacer l'ancien.

Le nouveau moteur n'implémente pas encore toutes les fonctionnalités de
l'ancien, et donc les deux modes restent accessibles pour cette version
4. À noter que les nouveaux outils pour l'aide au routage présentés
ci-dessous sont uniquement disponibles dans le nouveau mode.

Routeur « Push and Shove »
~~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: http://share.gifyoutube.com/ml2lLD.gif 
   :width: 600px
   :alt: Le routeur en action

Ce mode de routage déplace automatiquement les
pistes gênantes pour la connexion en cours.

.. raw:: html

   <iframe width="800" height="600" src="https://www.youtube.com/embed/CCG4daPvuVI" frameborder="0" allowfullscreen>
   </iframe>

Routage de paire différentielle
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: http://share.gifyoutube.com/vZDVLV.gif
   :width: 600px
   :alt: Le routeur en action

Permet de router deux pistes en gardant une largeur
fixe entre elles. Utile pour les `transmissions
différentielles <https://fr.wikipedia.org/wiki/Signalisation_diff%C3%A9rentielle>`__.

Piste à longueur contrôlée « length matching »
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: http://share.gifyoutube.com/yXDEOb.gif 
   :width: 600px
   :alt: Le routeur en action

Cette fonction permet de définir une longueur
souhaitée à un fil et de voir en temps réel, pendant le routage si on
s'approche ou si on s'éloigne de cette valeur. Lorsqu'un concepteur
route un bus analogique rapide, il est particulièrement important que
toutes ses pistes mesurent bien la même longueur afin d'éviter les
problèmes de désynchronisation, c’est-à-dire une différence de temps de
transmission sur deux lignes parallèles.

Prise en charge de Mac OS X
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Dans la version précédente, la prise en charge de Mac OS X était notée
comme expérimentale. Avec cette nouvelle version, Mac OS X est devenu un
citoyen de première classe :

-  Image d'installation simple « glisser déposer »

.. image:: http://s9.postimg.org/3p6e5dfm7/Ki_Cad_OSX_Installer.png
   :alt: Installateur OSX

-  Prise en compte des trackpads modernes pour le défilement horizontal
   et vertical à deux doigts, ainsi que le « pinch to zoom ».

Bibliothèques
-------------

Un effort particulier a été effectué sur les bibliothèques, avec
notamment la création d'une convention pour la création de composants
schémas et d'empreintes. Voir `KiCad Library
Convention <https://github.com/KiCad/kicad-library/blob/master/KiCad_Library_Convention.txt>`__.

Et pour les prochaines versions?
================================

La prochaine version devrait amener plusieurs améliorations
intéressantes, notamment :

-  Nouveaux formats basés sur la syntaxe
   `S-expression <http://fr.wikipedia.org/wiki/S-expression>`__ pour les
   schémas et les composants schémas
-  Amélioration et ajout des fonctionnalités manquantes dans le nouveau
   moteur de rendu de Pcbnew, permettant de supprimer l'ancien moteur
-  Réécriture du moteur 3D.

Références
==========

-  `Présentation de Kicad par Wayne Stambaugh -- FOSDEM
   2015 <https://www.youtube.com/watch?v=wRolB1my6fI>`__
-  `Olimex <https://olimex.wordpress.com/2015/03/12/our-first-two-small-kicad-oshw-boards-are-ready/>`__

.. |GerbView| image:: http://docs.kicad-pcb.org/en/images/3360000029F09D033B0.png
.. |Rendu 2D| image:: https://framapic.org/fBKrPp01NB2h/jXe9A3Ib
.. |Rendu 3D| image:: https://framapic.org/ZwHJjPjYd5f0/lWkqeNb9

.. _Linuxfr.org: https://linuxfr.org/news/sortie-de-kicad-4-0
.. _`CC BY-SA`: http://creativecommons.org/licenses/by-sa/4.0/deed.fr
