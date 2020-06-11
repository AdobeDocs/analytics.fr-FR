---
title: Sorties
description: Instance de la dernière valeur d’une visite.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 1%

---


# Sorties

*Cette page d’aide décrit le fonctionnement des sorties en tant que mesure. Pour plus d’informations sur le fonctionnement des sorties en tant que dimension, voir Dimensions[de](../dimensions/exit-dimensions.md)sortie.*

La mesure &quot;Sorties&quot; indique le nombre de captures d’une valeur de dimension donnée en tant que dernière valeur d’une visite. Cette mesure s’avère utile lorsque vous souhaitez en savoir plus sur la dernière chose que les visiteurs voient avant de quitter votre site. L’affichage des dernières valeurs d’une dimension peut vous aider à comprendre et à optimiser l’expérience qu’un visiteur obtient avant qu’il ne s’en aille.

## Méthode de calcul de cette mesure

Après la fin d’une [visite](visits.md) , enregistrez la valeur de dimension la plus récente comme sortie. Il n’existe qu’une seule sortie par dimension par visite. Il ne s’agit pas nécessairement du dernier accès de la visite si la dimension a été définie dans les accès précédents. Il s’agit d’une mesure basée sur les visites ; elle s’applique rétroactivement à tous les accès de la visite.

>[!TIP] Si vous vue cette mesure sur une dimension qui n’est pas toujours définie à chaque visite, vous pouvez masquer la valeur de dimension Non spécifié dans Analyse Workspace. Cliquez sur l’icône de filtre, puis décochez la case [!UICONTROL Inclure non spécifié (Aucun)].
