---
description: valeur nulle
seo-description: valeur nulle
seo-title: PHP
solution: Analytics
subtopic: Notes de mise à jour
title: PHP
topic: Développeur et mise en œuvre
uuid: 65 a 644 ef -8 e 50-406 b -8 b 12-0582495 d 130 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# PHP{#php}

>[!NOTE]
>
>Pour trouver la version de la bibliothèque actuelle, activez la journalisation du débogage.

## Version 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

Date de publication : **août 2014**

* Changements internes pour la prise en charge des fonctions à venir.

## Version 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

Date de publication : **juillet 2012**

* Added a check for the "off" returned for the $_SERVER['HTTPS'] in IIS. Without this check, typecasting to boolean ((bool)$_SERVER['HTTPS']) returned true in IE whether the request was made through HTTP or HTTPS. Cela entraînait les pages non sécurisées à effectuer une requête d’image sécurisée. 

## Version 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

Les bibliothèques de mesures pour PHP 1.1 comprennent les mises à jour suivantes depuis la version 1.0 :

* Géosegmentation plus précise (quand `sendFromServer` est activé).
* Correction d’un bogue de sorte que l’utilisateur puisse maintenant ajouter à la variable `userAgent`.
* La balise Image est maintenant plus conforme avec davantage de navigateurs mobiles.
* La variable `imageDimensions` est maintenant définie par défaut sur 5x5 quand l’option mobile est activée.
* Liste de détection des robots perfectionnée.
* Ajout d’informations de débogage (en-têtes HTTP, réponse, erreurs, etc.) quand `debugTracking` et `sendFromServer` sont activés.

* Added the `debugFilename` variable (when `sendFromServer` is enabled).

* The pagename variable defaults to `$_SERVER['SCRIPT_NAME']` when neither `pagename` nor `pageURL` are set.

* Prise en charge complète des mises en œuvre CGI de PHP.
* Amélioration des performances.

