---
description: Affiche des mesures selon que JavaScript est activé, désactivé ou comptabilisé en tant que « non identifié » sur le périphérique.
seo-description: Affiche des mesures selon que JavaScript est activé, désactivé ou comptabilisé en tant que « non identifié » sur le périphérique.
seo-title: Prise en charge de JavaScript
solution: Analytics
title: Prise en charge de JavaScript
topic: Présentation
uuid: 7 b 95001 a-cd 35-478 a -8 b 24-54 d 30666110 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Prise en charge de JavaScript

Affiche des mesures selon que JavaScript est activé, désactivé ou comptabilisé en tant que « non identifié » sur le périphérique.

>[!NOTE]
>
>In early November 2016, we plan to remove the restriction where JavaScript is always listed as *`disabled / unidentified`* for Mobile devices.

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
