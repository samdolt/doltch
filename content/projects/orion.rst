Projet Orion
############

:date: 2015-03-26 21:45
:slug: projects/orion
:tags: Projets

Orion est un projet personnel en cours pour la création d'une plateforme
ouverte de domotique. Le projet se compose / se composera de:

Partie matérielle
=================

Orion_HDK
---------

Plateforme de dévellopement hardware permettant la création de noeuds
communiquant avec un contrôlleur à l'aide d'un protocôle radio.

Cette plateforme sera basée sur un processeur ARM Cortex M0+ de STM
Microelectronics couplé au circuit RF CC1200 de Texas Instrument

Orion_BaseStation
-----------------

Coeur du système permettant de communiquer avec chaque noeuds radio. 
Cette partie sera constituée d'un carte de dévellopement GNU/Linux open source
de la game OLinuxino de Olimex couplée à une carte Orion-HDK pour la partie
RF.


Partie logicielle
=================

Orion_Backend
-------------

Logiciel ayant deux rôles: Surveiller et enregistrer les données en provenance
des noeuds ainsi que faciliter l'échange d'information.

L'échange d'information utilise le principe sub/push. Chaque nouvelle valeur en
provenance d'un noeuds est ainsi enregistrée puis envoyée à tous les logiciels
ayant demander à être informé.

Orion_WebFrontEnd
-----------------

Interface web permettant de gérer le système.

Orion_Driver_RF_HDK
-------------------

Driver permettant de relier un réseaux de noeuds utilisant la plateforme
Orion_HDK à Orion_Backend

Choix technique
===============

Language de programmation
-------------------------

Les différents logiciels doivent pouvoir fonctionner pour une installation
standard sur une station de base au ressource limitée tels que:

  - OLinuxino 64MB de RAM / 2Go de FLASH

De plus, le language de programmation doit être moderne, sécurisé et si
possible simple.

Les faibles ressources à disposition impose de restreindre le choix à des
language compilé:

  - C
  - C++
  - Go
  - Rust

Go n'a pas été choisit pour les raisons suivantes:

    - Linker static, augmentation de l'espace disque
    - Language apportant peu pour notre cas d'utilisation par rapport au C++.

C++ n'a pas été retenu pour les raisons suivantes:

    - Language qui privilégie l'héritage alors que je préfère la compisition.
    - Language un peu complexe
    - Utilisation fréquente de la HEAP

Le language C n'a pas été retenu pour les raisons suivantes:

    - Peu de modernité
    - Rust existe

Le language Rust a été choisit malgré:

    - la jeunesse du langage
    - le manque de librairie

Pour les raisons suivantes:

    - Language système moderne
    - Orienté Object par composition
    - Favarise la création de variable sur la pile (STACK)
    - Diminue les nombres d'erreurs de conception, avec des contrôls poussés
      lors de la compilation et pas au RUNTIME.

Plateformes matérielles
-----------------------

ARM Cortex M0+ pour la faible consommation d'ernergie.


