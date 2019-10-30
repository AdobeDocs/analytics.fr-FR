---
description: Affiche des mesures selon que JavaScript est activé, désactivé ou comptabilisé en tant que « non identifié » sur le périphérique.
seo-description: Affiche des mesures selon que JavaScript est activé, désactivé ou comptabilisé en tant que « non identifié » sur le périphérique.
seo-title: 'Prise en charge de JavaScript '
solution: Analytics
title: 'Prise en charge de JavaScript '
topic: Rapports
uuid: 7b95001a-cd35-478a-8b24-54d3066110d
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Prise en charge de JavaScript 

Affiche des mesures selon que JavaScript est activé, désactivé ou comptabilisé en tant que « non identifié » sur le périphérique.

> [!NOTE] Début novembre 2016, nous prévoyons de supprimer la restriction qui répertorie toujours JavaScript comme *`disabled / unidentified`* pour les périphériques mobiles.

Le rapport JavaScript correspond à la colonne javascript des données brutes.

javascript est un champ de niveau visite. Il conserve donc la valeur du premier accès lors de la visite. La colonne javascript repose sur la première valeur présente dans la colonne j_jscript (tout comme un visit_referrer conserve uniquement le premier référent de la visite).

j_jscript est renseigné à partir du paramètre j de la demande d’image Adobe Analytics.

Voici un exemple :

| Accès | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

Par conséquent, cela n’a pas d’importance si une version de JavaScript est spécifiée à un moment donné de la visite. Elle sera toujours affichée comme n’étant pas JavaScript, car le premier accès ne contenait aucune valeur pour j_jscript.
