---
title: Personnes avec un ID Experience Cloud
description: Nombre de personnes dans les analyses entre appareils qui disposent d’un identifiant Experience Cloud.
source-git-commit: eaf0c3b751a5fbdc70ad6bef501dbf9e8400339c
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 21%

---

# Personnes avec un ID Experience Cloud

&quot;Personnes avec ID Experience Cloud&quot; est une mesure [Analyses entre appareils](../cda/overview.md) qui indique le nombre de [personnes](people.md) qui ont été identifiées par Adobe à l’aide du [service d’ID Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr).

## Méthode de calcul de cette mesure

Compte tenu de chaque [personne](people.md) (identifiée ou non), cette mesure augmente si l’accès contient la chaîne de requête `mid` (basée sur le cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=fr)).

Vous pouvez créer la mesure calculée `[People with ECID] ÷ [People]` pour obtenir le pourcentage de visiteurs sur votre site à l’aide du service d’ID.

Pour plus d’informations sur l’importance de l’identifiant Experience Cloud et le débogage de votre configuration, voir la mesure équivalente non-CDA [Visiteurs avec un identifiant Experience Cloud](visitors-with-ecid.md) .