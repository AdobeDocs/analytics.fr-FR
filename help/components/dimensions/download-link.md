---
title: Lien de téléchargement
description: Nom du lien de téléchargement.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 74%

---

# Lien de téléchargement

La dimension [Lien de téléchargement](overview.md) indique les noms des liens de téléchargement implémentés sur votre site. Cette dimension est utile pour en savoir plus sur le comportement des visiteurs vis-à-vis des liens de téléchargement, par exemple :

* Savoir quels fichiers sont téléchargés le plus souvent de votre site.
* Déterminer si certains fichiers sont téléchargés plus souvent pendant des périodes spécifiques.
* Vérifier que les visiteurs téléchargent différents types de fichier s’ils sont proposés.

## Renseignement de cette dimension avec des données

Cette dimension collecte les données de la [`pev2` chaîne de requête &#x200B;](/help/implement/validate/query-parameters.md) dans les demandes d’image pour les accès qui contiennent également la chaîne de requête `pe` avec la valeur `lnk_d`. Si la chaîne de requête `pe` a une valeur différente dans l’accès, cette dimension ne collecte pas de données. La longueur maximale de cette dimension est de 100 octets.

Si vous souhaitez envoyer des données à cette dimension à l’aide d’AppMeasurement, envoyez une demande d’image [`tl()`](/help/implement/vars/functions/tl-method.md) avec un argument de type de lien `"d"`. Renseignez l’argument nom du lien avec la valeur souhaitée :

```js
s.tl(true,"d","Example download link");
```

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports.
