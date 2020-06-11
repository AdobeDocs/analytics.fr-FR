---
title: Server (Serveur)
description: Nom du serveur.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 1%

---


# Server (Serveur)

La dimension &quot;Serveur&quot; liste généralement le nom d’hôte du site. Pour les suites de rapports qui combinent plusieurs domaines ou sous-domaines, cette dimension est utile pour identifier les domaines ou sous-domaines les plus performants.

Cette dimension est liée aux dimensions des sections [](page.md) Page [et](site-section.md) Site. La page est la plus granulaire, le serveur est la moins granulaire et la section du site est comprise entre les deux.

## Renseigner cette dimension avec des données

Cette dimension récupère les données de la chaîne [`server` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. AppMeasurement collecte ces données à l’aide de la [`server`](/help/implement/vars/page-vars/server.md) variable.

## Valeurs de dimension

Les valeurs de dimension incluent les serveurs de votre site. Votre organisation détermine les valeurs de dimension spécifiques que vous souhaitez utiliser. Certaines organisations utilisent `window.location.hostname`, tandis que d’autres formulent des valeurs personnalisées. Quelle que soit la méthode utilisée, assurez-vous qu’elle est cohérente et que vous l’enregistrez dans un document [de conception de](/help/implement/prepare/solution-design.md)solution.
