---
title: Personnes avec un Experience Cloud ID
description: Nombre de personnes dans les analyses entre appareils qui disposent d’un Experience Cloud ID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 100%

---

# Personnes avec un Experience Cloud ID

« Personnes avec identifiant Experience Cloud » est une mesure [Analyses entre appareils](../cda/overview.md) qui indique le nombre de [personnes](people.md) qui ont été identifiées par Adobe à l’aide du [service Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr).

## Méthode de calcul de cette mesure

Compte tenu de chaque [personne](people.md) (identifiée ou non), cette mesure augmente si l’accès contient la chaîne de requête `mid` (basée sur le cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=fr)).

Vous pouvez créer la mesure calculée `[People with ECID] ÷ [People]` pour obtenir le pourcentage de visiteurs sur votre site à l’aide du service d’identification.

Pour plus d’informations sur l’importance de l’Experience Cloud ID et le débogage de votre configuration, voir la mesure équivalente non-CDA [Visiteurs avec un Experience Cloud ID](visitors-with-ecid.md).
