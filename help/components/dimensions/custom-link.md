---
title: Lien personnalisé
description: Nom du lien personnalisé.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---


# Lien personnalisé

La dimension &quot;Lien personnalisé&quot; rapporte les noms des liens personnalisés implémentés sur votre site. Cette dimension est utile pour comprendre les types de liens sur lesquels les visiteurs cliquent le plus.

## Renseigner cette dimension avec des données

Cette dimension collecte les données de la chaîne [`pev2` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image pour les accès qui contiennent également la chaîne de `pe` requête avec la valeur `lnk_o`. Si la valeur de la chaîne de `pe` requête de l’accès est différente, cette dimension ne collecte pas de données.

Si vous souhaitez envoyer des données à cette dimension à l’aide d’AppMeasurement :

* Renseignez la [`linkName`](/help/implement/vars/config-vars/linkname.md) variable avec la valeur souhaitée.
* Set the [`linkType`](/help/implement/vars/config-vars/linktype.md) variable to `"o"`.
* Envoyez une demande d’ [`tl()`](/help/implement/vars/functions/tl-method.md) image.

## Éléments de dimension

Cette variable étant basée sur une chaîne personnalisée dans votre implémentation, votre organisation détermine les éléments de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins rapports.
