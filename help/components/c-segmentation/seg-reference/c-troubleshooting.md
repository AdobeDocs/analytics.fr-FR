---
description: valeur nulle
title: Dépannage de la segmentation
uuid: 8476d617-4b44-4ff2-9b3a-02685f666afc
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Dépannage de la segmentation

## Erreur : « Éléments incompatibles dans ce segment » {#section_B167EE10A0844E649DD7E14D0BAEDA17}

Cette erreur survient lorsque vous essayez d’enregistrer un segment dans le dossier de l’entrepôt de données et que celui-ci contient des éléments non compatibles avec Data Warehouse. Pour résoudre cette erreur, suivez l’une des deux étapes suivantes :

* enregistrez le segment dans un dossier différent ;
* supprimez ou modifiez les portions incompatibles du segment.

## Pourquoi mon segment ne renvoie-t-il aucune donnée ?  {#section_999749CBBE984142AEA49A6E68E6730A}

Raisons possibles :

* Imbrication de conteneurs ; par exemple, lorsqu’un conteneur Visiteur est imbriqué sous un conteneur Visite.
* Le rapport ne prend pas en charge la segmentation.
* Aucune donnée ne correspond aux critères de segmentation.

## Pourquoi ne puis-je pas voir un segment que j’ai créé dans le Gestionnaire de segments ?  {#section_BE0A0930A2694A23BB32DA71696D52CE}

Raisons possibles :

* Certaines dimensions sont disponibles uniquement dans Data Warehouse, et non dans le Gestionnaire de segments.
* Le segment n’est pas compatible avec les Reports &amp; Analytics.
* Le segment n’est vérifié que pour une suite de rapports spécifique.
* Il est possible qu’un segment partagé ait été supprimé par un autre utilisateur.
* Chargement des segments impossible en raison d’un problème lié au centre de données ou au cache du navigateur.
* Le segment n’a pas été enregistré.
* L’adresse IP est peut-être bloquée du côté de l’utilisateur.

## Pourquoi les données de page affichées après avoir appliqué un segment semblent-elles incorrectes ?  {#section_B226AF69FE06463A8BC5337FDA8D4949}

Raisons possibles :

* Les règles/opérateurs sont incorrects pour le résultat requis.
* Application incorrecte des conteneurs sur le segment.
* Les variables de trafic utilisées pour la segmentation ne sont pas configurées correctement ou ont expiré.

