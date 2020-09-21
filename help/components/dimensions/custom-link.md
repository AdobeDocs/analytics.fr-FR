---
title: Lien personnalisé
description: Le nom du lien personnalisé.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '148'
ht-degree: 100%

---


# Lien personnalisé

La dimension « Lien personnalisé » indique le nom des liens personnalisés implémentés sur votre site. Cette dimension est utile pour déterminer les types de liens les plus utilisés par les visiteurs.

## Renseignement de cette dimension avec des données

Cette dimension collecte les données de la [`pev2` chaîne de requête ](/help/implement/validate/query-parameters.md) dans les demandes d’image pour les accès qui contiennent également la chaîne de requête `pe` avec la valeur `lnk_o`. Si la valeur de la chaîne de requête `pe` de l’accès est différente, cette dimension ne collecte pas de données.

Si vous souhaitez envoyer des données à cette dimension à l’aide d’AppMeasurement :

* Renseignez la variable [`linkName`](/help/implement/vars/config-vars/linkname.md) avec la valeur souhaitée.
* Définissez la variable [`linkType`](/help/implement/vars/config-vars/linktype.md) sur `"o"`.
* Envoyez une demande d’image [`tl()`](/help/implement/vars/functions/tl-method.md).

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée de votre implémentation, votre entreprise détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins pour les rapports.
