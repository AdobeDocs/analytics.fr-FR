---
title: Entrées
description: Instance de la première valeur d’une visite.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 1%

---


# Entrées

*Cette page d’aide décrit le fonctionnement des entrées en tant que mesure. Pour plus d’informations sur le fonctionnement des entrées en tant que dimension, voir Dimensions[](../dimensions/entry-dimensions.md)d’entrée.*

La mesure Entrées indique le nombre de captures d’une valeur de dimension donnée en tant que première valeur d’une visite. Cette mesure s’avère utile lorsque vous souhaitez en savoir plus sur les premières impressions des visiteurs sur votre site. L’affichage des premières valeurs d’une dimension peut vous aider à comprendre et à optimiser l’expérience d’un nouveau visiteur.

## Méthode de calcul de cette mesure

Pour une dimension donnée, enregistrez la première valeur de dimension vue comme entrée dans une visite. Il n’existe qu’une seule entrée par dimension par visite. Il ne s’agit pas nécessairement du premier accès de la visite si la dimension n’est pas initialement définie. Il s’agit d’une mesure basée sur les visites ; une fois qu’il est lié à une valeur de dimension, il persiste pour le reste de la visite.

>[!TIP]
>
>Si vous définissez cette mesure sur une dimension qui n’est pas toujours définie à chaque visite, vous pouvez masquer la valeur de dimension Non spécifié dans l’Analysis Workspace. Cliquez sur l’icône de filtre, puis décochez la case [!UICONTROL Inclure non spécifié (Aucun)].
