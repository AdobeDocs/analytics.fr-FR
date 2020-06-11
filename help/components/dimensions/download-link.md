---
title: Lien de téléchargement
description: Nom du lien de téléchargement.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 15%

---


# Lien de téléchargement

La dimension &quot;Lien de téléchargement&quot; indique le nom des liens de téléchargement implémentés sur votre site. Cette dimension est utile pour en savoir plus sur le comportement des visiteurs autour des liens de téléchargement, par exemple :

* Savoir quels fichiers sont téléchargés le plus souvent de votre site.
* Déterminer si certains fichiers sont téléchargés plus souvent pendant des périodes spécifiques.
* Vérifiez que les visiteurs téléchargent différents types de fichiers s’ils sont proposés.

## Renseigner cette dimension avec des données

Cette dimension collecte les données de la chaîne [`pev2` de](/help/implement/validate/query-parameters.md) requête dans les demandes d’image pour les accès qui contiennent également la chaîne de `pe` requête avec la valeur `lnk_d`. Si la valeur de la chaîne de `pe` requête de l’accès est différente, cette dimension ne collecte pas de données.

Si vous souhaitez envoyer des données à cette dimension à l’aide d’AppMeasurement :

* Renseignez la [`linkName`](/help/implement/vars/config-vars/linkname.md) variable avec la valeur souhaitée.
* Set the [`linkType`](/help/implement/vars/config-vars/linktype.md) variable to `"d"`.
* Envoyez une demande d’ [`tl()`](/help/implement/vars/functions/tl-method.md) image.

## Valeurs de dimension

Cette variable étant basée sur une chaîne personnalisée dans votre implémentation, votre organisation détermine les valeurs de dimension. Adobe recommande de regrouper les liens en catégories significatives en fonction de vos besoins rapports.
