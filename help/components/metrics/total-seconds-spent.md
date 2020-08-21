---
title: Durée totale en secondes
description: Nombre total cumulé de secondes passées sur l’élément de dimension.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 64%

---


# Durée totale en secondes

La mesure &quot;Total secondes passées&quot; montre le nombre agrégé de secondes passées par un visiteur sur un élément de dimension donné. Cette mesure s’avère utile lorsque vous souhaitez obtenir la quantité brute de temps passé sur un élément de dimension donné et non pas des moyennes comme les autres offres des mesures de durée de la visite.

Dans Report Builder, cette mesure est intitulée « Durée totale de la visite ».

## Méthode de calcul de cette mesure

Cette mesure utilise les étapes suivantes pour mesurer le calcul :

1. Pour un accès donné, consultez la date et l’heure.
2. Comparez cet accès à l’horodatage du prochain accès de la visite. L’accès de suivi des pages vues et des liens est important.
3. La durée en secondes écoulée entre les deux accès contribue à l’élément de dimension.

Les variables persistantes, telles que les [eVars](../dimensions/evar.md), sont comptabilisées dans la durée totale en secondes. Les variables de trafic, telles que [props](../dimensions/prop.md), comprennent les secondes passées lors des appels de suivi des liens suivants.

>[!TIP]
>
>Le temps passé n’est pas mesuré pour le dernier accès de la visite, puisqu’il n’existe aucune demande d’image ultérieure pour mesurer le temps écoulé. Ce concept s’applique également aux visites composées d’un seul accès (un rebond).

Consultez [Présentation de la durée de consultation](time-spent.md) pour obtenir des informations plus générales sur la durée de consultation.
