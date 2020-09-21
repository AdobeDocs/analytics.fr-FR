---
title: Entrées
description: Instance de la première valeur d’une visite.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '191'
ht-degree: 100%

---


# Entrées

*Cette page d’aide décrit le fonctionnement des entrées en tant que mesure. Pour plus d’informations sur le fonctionnement des entrées en tant que dimension, consultez la dimension[Entrées](../dimensions/entry-dimensions.md).*

La mesure « Entrées » indique le nombre de fois où un élément de dimension donné est capturé comme première valeur d’une visite. Cette mesure s’avère utile lorsque vous souhaitez en savoir plus sur les premières impressions des visiteurs sur votre site. L’affichage des premières valeurs d’une dimension peut vous aider à comprendre et à optimiser l’expérience d’un nouveau visiteur.

## Méthode de calcul de cette mesure

Pour une dimension donnée, enregistrez le premier élément de dimension vu comme entrée dans une visite. Il n’existe qu’une seule entrée par dimension et par visite. Il ne s’agit pas nécessairement du premier accès de la visite si la dimension n’est pas initialement définie. Il s’agit d’une mesure basée sur la visite. Une fois qu’elle est liée à un élément de dimension, elle persiste pour le reste de la visite.

>[!TIP]
>
>Si vous définissez cette mesure sur une dimension qui n’est pas toujours définie à chaque visite, vous pouvez masquer l’élément de dimension « Non spécifié » dans Analysis Workspace. Cliquez sur l’icône de filtre, puis décochez la case [!UICONTROL Inclure non spécifié (Aucun)].
