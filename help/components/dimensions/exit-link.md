---
title: Lien de sortie
description: Le nom du lien de sortie.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 75%

---

# Lien de sortie

La [dimension](overview.md) « Lien de sortie » indique les noms des liens de sortie implémentés sur votre site. Cette dimension est utile pour identifier les liens les plus populaires qui pointent vers des domaines en dehors de votre site.

## Renseignement de cette dimension avec des données

Cette dimension collecte les données de la [`pev2` chaîne de requête &#x200B;](/help/implement/validate/query-parameters.md) dans les demandes d’image pour les accès qui contiennent également la chaîne de requête `pe` avec la valeur `lnk_e`. Si la chaîne de requête `pe` a une valeur différente dans l’accès, cette dimension ne collecte pas de données. La longueur maximale de cette dimension est de 100 octets.

Si vous souhaitez envoyer des données à cette dimension à l’aide d’AppMeasurement, envoyez une demande d’image [`tl()`](/help/implement/vars/functions/tl-method.md) avec un argument de type de lien `"e"`. Renseignez l’argument du nom de lien avec la valeur souhaitée.

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports.
