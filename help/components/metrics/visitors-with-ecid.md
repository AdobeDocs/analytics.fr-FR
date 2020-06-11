---
title: Visiteurs avec un Experience Cloud ID
description: Nombre d’visiteurs uniques utilisant le service Adobe Experience Cloud ID.
translation-type: tm+mt
source-git-commit: 0328de560185e716a3913080feda9cd078e0f206
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 19%

---


# Visiteurs avec un Experience Cloud ID

La mesure &quot;Visiteurs avec un ID Experience Cloud&quot; indique le nombre de visiteurs uniques qui ont été identifiés par Adobe à l’aide du service [d’ID](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html)Experience Cloud. Cette dimension est utile pour comparer à la mesure visiteurs [](unique-visitors.md) uniques afin de s’assurer que la majorité des visiteurs de votre site utilisent le service d’ID. Si une grande partie des visiteurs n’utilisent pas les cookies du service d’ID, cela peut indiquer un problème dans votre implémentation.

>[!NOTE] Cette mesure est particulièrement importante pour le débogage si vous utilisez plusieurs services Experience Cloud, tels que Adobe Cible ou Adobe Audience Manager. Les segments partagés entre les produits Experience Cloud n’incluent pas de visiteurs sans Experience Cloud ID.

## Méthode de calcul de cette mesure

Cette mesure est basée sur la mesure visiteurs [](unique-visitors.md) uniques, sauf qu’elle inclut uniquement les individus identifiés à l’aide de la chaîne de `mid` requête (en fonction du [`s_ecid`](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-analytics.html) cookie).

## Débogage de la configuration de votre ID Experience Cloud

La mesure &quot;Visiteurs avec un ID Experience Cloud&quot; peut s’avérer utile pour résoudre les problèmes d’intégration d’Experience Cloud ou pour identifier les zones de votre site où le service d’ID n’est pas déployé.

Faites glisser côte à côte &quot;Visiteurs avec Experience Cloud ID&quot; avec des visiteurs uniques pour les comparer :

![Comparaison de visiteurs uniques](assets/metric-mcvid1.png)

Dans cet exemple, notez que chaque page comporte le même nombre de &quot;Visiteurs uniques&quot; que &quot;Visiteurs avec un Experience Cloud ID&quot;. Néanmoins, le nombre total de visiteurs uniques est supérieur au nombre total de visiteurs avec un Experience Cloud ID. Vous pouvez créer une mesure [](../c-calcmetrics/cm-overview.md) calculée pour déterminer les pages qui ne définissent pas le service d’ID. Vous pouvez utiliser la définition suivante :

![Définition de mesure calculée](assets/metric-mcvid2.png)

En ajoutant la mesure calculée au rapport, vous pouvez trier le rapport Pages de sorte que les pages comportant le plus grand nombre de visiteurs sans MCID s’affichent :

![Pages sans service d’ID](assets/metric-mcvid3.png)

Notez que la valeur de dimension &quot;Vues rapides du produit&quot; n&#39;est pas correctement implémentée avec Identity Service. Vous pouvez collaborer avec les équipes appropriées de votre organisation pour mettre à jour ces pages le plus rapidement possible. Vous pouvez créer un rapport similaire avec n’importe quel type de dimension, tel que le type [de](../dimensions/browser-type.md)navigateur, la section [](../dimensions/site-section.md)Site ou toute [eVar](../dimensions/evar.md).
