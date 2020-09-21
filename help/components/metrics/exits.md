---
title: Sorties
description: Une instance de la dernière valeur d’une visite.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '186'
ht-degree: 100%

---


# Sorties

*Cette page d’aide décrit le fonctionnement des sorties en tant que mesure. Pour plus d’informations sur le fonctionnement des sorties en tant que dimension, consultez [Dimensions de sortie](../dimensions/exit-dimensions.md).*

La mesure « Sorties » indique le nombre de fois qu’un élément de dimension donné est capturé comme dernière valeur d’une visite. Cette mesure s’avère utile lorsque vous souhaitez en savoir plus sur le dernier élément que les visiteurs voient avant de quitter votre site. L’affichage des dernières valeurs d’une dimension peut vous aider à comprendre et à optimiser l’expérience du visiteur avant de quitter le site.

## Méthode de calcul de cette mesure

Une fois la [visite](visits.md) terminée, enregistrez l’élément de dimension le plus récent comme sortie. Il n’existe qu’une seule sortie par dimension et par visite. Il ne s’agit pas nécessairement du dernier accès de la visite si la dimension a été définie au cours d’accès précédents. Il s’agit d’une mesure basée sur les visites. Elle s’applique rétroactivement à tous les accès de la visite.

>[!TIP]
>
>Si vous définissez cette mesure sur une dimension qui n’est pas toujours définie à chaque visite, vous pouvez masquer l’élément de dimension « Non spécifié » dans Analysis Workspace. Cliquez sur l’icône de filtre, puis décochez la case [!UICONTROL Inclure non spécifié (Aucun)].
