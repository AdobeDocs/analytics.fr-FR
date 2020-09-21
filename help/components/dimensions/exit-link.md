---
title: Lien de sortie
description: Le nom du lien de sortie.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '152'
ht-degree: 100%

---


# Lien de sortie

La dimension « Lien de sortie » indique le nom des liens de sortie implémentés sur votre site. Cette dimension est utile pour identifier les liens les plus populaires qui pointent vers des domaines en dehors de votre site.

## Renseignement de cette dimension avec des données

Cette dimension collecte les données de la [`pev2`chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image pour les accès qui contiennent également la chaîne de requête `pe` avec la valeur `lnk_e`. Si la valeur de la chaîne de requête `pe` de l’accès est différente, cette dimension ne collecte pas de données.

Si vous souhaitez envoyer des données à cette dimension à l’aide d’AppMeasurement :

* Renseignez la variable [`linkName`](/help/implement/vars/config-vars/linkname.md) avec la valeur souhaitée.
* Définissez la variable [`linkType`](/help/implement/vars/config-vars/linktype.md) sur `"e"`.
* Envoyez une demande d’image [`tl()`](/help/implement/vars/functions/tl-method.md).

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports.
