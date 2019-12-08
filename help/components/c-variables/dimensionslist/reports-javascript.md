---
description: Affiche des mesures selon que JavaScript est activé, désactivé ou comptabilisé en tant que « non identifié » sur le périphérique.
title: Prise en charge de JavaScript
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Prise en charge de JavaScript

Affiche des mesures selon que JavaScript est activé, désactivé ou comptabilisé en tant que « non identifié » sur le périphérique.

> [!NOTE] Début novembre 2016, nous prévoyons de supprimer la restriction qui répertorie systématiquement JavaScript comme *`disabled / unidentified`* pour les appareils mobiles.

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
