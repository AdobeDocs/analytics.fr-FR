---
title: Considérations relatives à la migration du service d’identification des visiteurs pour Adobe Analytics
description: Présentation de l’interface d’Adobe Analytics avec le service d’identification des visiteurs.
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# Considérations relatives à la migration du service d’identification des visiteurs pour Adobe Analytics

Si votre entreprise prévoit de passer au service d’identification des visiteurs avec une implémentation Analytics existante, certains sujets importants doivent être pris en compte. Ces considérations sont importantes pour conserver l’intégrité de l’identification des visiteurs et comprendre le fonctionnement du service d’ID en présence d’une implémentation Analytics existante.

## Interface du service d’identification des visiteurs avec les cookies des visiteurs Analytics hérités

AppMeasurement disposant de sa propre méthode pour identifier les visiteurs, certains visiteurs peuvent disposer de cookies Analytics hérités lorsqu’une organisation déploie le service d’identification des visiteurs. La liste suivante décrit la manière dont un visiteur est identifié dans diverses circonstances.

* **Aucun cookie visiteur présent** : le service d’ID attribue un Experience Cloud ID (`mid`).
* **Un cookie `s_vi` existe** : le service d’ID écrit l’ID Analytics hérité (`aid`) existant dans le cookie `AMCV` en plus d’un ID Experience Cloud (`mid`). Étant donné que la `aid` est supérieure dans l’[ordre des opérations](overview.md), l’ID Analytics hérité est l’identifiant du visiteur jusqu’à l’expiration ou l’effacement du cookie `AMCV`. Lorsqu’une période de grâce est activée, le service d’ID inclut le `mid` et le `aid` dans sa réponse.
* **Un cookie de secours existe** : le service d’ID n’écrit pas le cookie de secours (`fid`) dans le cookie `AMCV`. Au lieu de cela, les visiteurs reçoivent un Experience Cloud ID (`mid`) comme s’ils étaient un nouveau visiteur.

## Période de grâce du service d’identification des visiteurs

Si plusieurs implémentations envoient des données à la même suite de rapports et que vous ne pouvez mettre en œuvre le service d’identification des visiteurs que sur certaines implémentations, Adobe recommande de configurer un délai de grâce. Par exemple, si la section d’assistance de votre site est gérée par une solution de balisage distincte, il se peut que le service d’identification des visiteurs soit déployé sur le reste de votre site avant la section d’assistance. Sans période de grâce, les nouveaux visiteurs qui consultent la section d’assistance reçoivent un identifiant visiteur Analytics hérité, ce qui entraîne le comptage de deux visiteurs distincts. Avec une période de grâce, le service d’identification des visiteurs émet à la fois un Experience Cloud ID (`mid`) et un Analytics Visitor ID hérité (`aid`) afin que les zones de votre site sans le service d’identification restent cohérentes en identifiant les visiteurs.

Si vous coordonnez le déploiement du service d’identification des visiteurs dans toutes les zones de votre site, vous n’avez pas besoin de période de grâce. Pour configurer une période de grâce, contactez l’[Assistance clientèle Adobe](https://helpx.adobe.com/fr/marketing-cloud/contact-support.html).

## Suivi inter-domaines

Certaines implémentations d’identifiant visiteur Analytics héritées peuvent utiliser des « cookies tiers conviviaux », où deux domaines partagent le même cookie visiteur sur un domaine commun tel que `data.example.com`. Comme les cookies tiers conviviaux sont toujours des cookies tiers, la plupart des navigateurs modernes les rejettent, ce qui fait qu’Analytics s’appuie sur un identifiant de secours (`fid`) pour l’identification des visiteurs. Le passage au service d’ID permet à tous les domaines de définir le cookie `AMCV` dans un contexte propriétaire, ce qui augmente leur viabilité pour conserver un identifiant visiteur.

Bien que le service d’identification des visiteurs tente de définir un cookie tiers pour le suivi inter-domaines (le cookie [`demdex`](https://experienceleague.adobe.com/fr/docs/id-service/using/intro/cookies)), il est souvent rejeté par la plupart des navigateurs modernes. Envisagez d’utiliser la méthode [`appendVisitorIDsTo`](https://experienceleague.adobe.com/fr/docs/id-service/using/id-service-api/methods/appendvisitorid) pour transmettre les Experience Cloud ID entre les domaines que vous possédez.

## Tracking côté serveur

Vous pouvez appeler [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/fr/docs/id-service/using/id-service-api/methods/getmcvid) pour obtenir l’Experience Cloud ID (`mid`) et [`getAnalyticsVisitorID`](https://experienceleague.adobe.com/fr/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid) pour obtenir l’Analytics ID hérité (`aid`). Adobe recommande de vérifier les deux pour conserver la logique d’identification des visiteurs.
