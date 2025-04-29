---
title: Lien personnalisé
description: Le nom du lien personnalisé.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 75%

---

# Lien personnalisé

La [dimension](overview.md) « Lien personnalisé » indique les noms des liens personnalisés implémentés sur votre site. Cette dimension est utile pour déterminer les types de liens les plus utilisés par les visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension collecte les données de la [`pev2` chaîne de requête ](/help/implement/validate/query-parameters.md) dans les demandes d’image pour les accès qui contiennent également la chaîne de requête `pe` avec la valeur `lnk_o`. Si la chaîne de requête `pe` a une valeur différente dans l’accès, cette dimension ne collecte pas de données. La longueur maximale de cette dimension est de 100 octets.

Si vous souhaitez envoyer des données à cette dimension à l’aide d’AppMeasurement, envoyez une demande d’image [`tl()`](/help/implement/vars/functions/tl-method.md) avec un argument de type de lien `"o"`. Renseignez l’argument du nom de lien avec la valeur souhaitée.

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports.
