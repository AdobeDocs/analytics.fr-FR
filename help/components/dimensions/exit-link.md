---
title: Lien de sortie
description: Le nom du lien de sortie.
translation-type: tm+mt
source-git-commit: 423e9b753a3b7b1e0a8e8b9748f9694d718abd18
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 80%

---


# Lien de sortie

La dimension « Lien de sortie » indique le nom des liens de sortie implémentés sur votre site. Cette dimension est utile pour identifier les liens les plus populaires qui pointent vers des domaines en dehors de votre site.

## Renseignement de cette dimension avec des données

Cette dimension collecte les données de la [`pev2` chaîne de requête ](/help/implement/validate/query-parameters.md) dans les demandes d’image pour les accès qui contiennent également la chaîne de requête `pe` avec la valeur `lnk_e`. Si la valeur de la chaîne de requête `pe` de l’accès est différente, cette dimension ne collecte pas de données.

Si vous souhaitez envoyer des données à cette dimension à l’aide d’AppMeasurement, envoyez une demande d’image [`tl()`](/help/implement/vars/functions/tl-method.md) avec un argument de type de lien `"e"`. Renseignez l’argument du nom de lien avec la valeur souhaitée.

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports.
