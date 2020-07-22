---
title: Durée totale en secondes
description: Nombre total cumulé de secondes passées sur l’élément de dimension.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 9%

---


# Durée totale en secondes

La mesure &quot;Total secondes passées&quot; montre le nombre agrégé de secondes passées par un visiteur sur un élément de dimension donné. Cette mesure s’avère utile lorsque vous souhaitez obtenir la quantité brute de temps passé sur un élément de dimension donné et non pas des moyennes comme les autres offres des mesures de durée de la visite.

Dans le créateur de rapports, cette mesure est nommée &quot;Durée totale de la visite&quot;.

## Méthode de calcul de cette mesure

Cette mesure utilise les étapes suivantes pour mesurer le calcul :

1. Pour un accès donné, observez l’horodatage.
2. Comparez cet accès à l’horodatage du prochain accès de la visite. La vue de page et le suivi des liens comptabilisent tous les accès.
3. La durée en secondes écoulée entre les deux accès contribue à l’élément de dimension.

Les variables persistantes, telles que les [eVars](../dimensions/evar.md), comptent pour le total des secondes passées. Les variables de trafic, telles que [props](../dimensions/prop.md), incluent les secondes passées lors des appels de suivi de liens suivants.

>[!TIP]
>
>La durée de la visite n’est pas mesurée pour le dernier accès de la visite, car aucune demande d’image ultérieure ne permet de mesurer le temps écoulé. Ce concept s’applique également aux visites consistant en un seul accès (un rebond).

Voir Présentation [de la](time-spent.md) durée de la visite pour obtenir des informations plus générales sur la durée de la visite.
