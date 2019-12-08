---
description: valeur nulle
subtopic: Release notes
title: PHP
topic: Developer and implementation
uuid: 65a644ef-8e50-406b-8b12-0582495d130a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# PHP{#php}

> [!NOTE] Pour connaître la version de la bibliothèque actuelle, activez la journalisation du débogage.

## Version 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

Date de publication : **août 2014**

* Changements internes pour la prise en charge des fonctions à venir.

## Version 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

Date de publication : **juillet 2012**

* Ajout d’une vérification pour la valeur « off » renvoyée pour $_SERVER['HTTPS’] dans IIS. Sinon, le casting de type booléen ((bool)$_SERVER['HTTPS’]) renvoyait true dans IE que la requête soit effectuée via HTTP ou HTTPS. Cela entraînait les pages non sécurisées à effectuer une requête d’image sécurisée.

## Version 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

Les bibliothèques de mesures pour PHP 1.1 comprennent les mises à jour suivantes depuis la version 1.0 :

* Géosegmentation plus précise (quand `sendFromServer` est activé).
* Correction d’un bogue de sorte que l’utilisateur puisse maintenant ajouter à la variable `userAgent`.
* La balise Image est maintenant plus conforme avec davantage de navigateurs mobiles.
* La variable `imageDimensions` est maintenant définie par défaut sur 5x5 quand l’option mobile est activée.
* Liste de détection des robots perfectionnée.
* Ajout d’informations de débogage (en-têtes HTTP, réponse, erreurs, etc.) quand `debugTracking` et `sendFromServer` sont activés.

* Ajout de la variable `debugFilename` (quand `sendFromServer` est activé).

* La variable du nom de page est définie par défaut sur `$_SERVER['SCRIPT_NAME']` quand `pagename` et `pageURL` ne sont pas définies.

* Prise en charge complète des mises en œuvre CGI de PHP.
* Amélioration des performances.

