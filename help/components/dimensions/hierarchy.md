---
title: Hiérarchie
description: (Retiré) Dimension personnalisée que vous pouvez utiliser dans les rapports.
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 86%

---

# Hiérarchie

>[!IMPORTANT]
>
>Cette dimension a été retirée et n’est pas disponible [dimension](overview.md) dans Analysis Workspace. Adobe recommande d’utiliser plutôt des [eVars](evar.md) et des classifications.

Les hiérarchies sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Elles ne persistent pas au-delà de l’accès défini. Si le contrat que vous avez conclu avec Adobe le prévoit, vous pouvez obtenir jusqu’à cinq hiérarchies.

## Renseigner les hiérarchies avec des données

Chaque hiérarchie collecte des données de la chaîne de requête [`h1` - `h5` &#x200B;](/help/implement/validate/query-parameters.md) dans les demandes d’image. Par exemple, le paramètre de chaîne de requête `h1` collecte des données pour Hiérarchie 1, tandis que le paramètre de chaîne de requête `h4` collecte des données pour Hiérarchie 4.

AppMeasurement, qui compile les variables JavaScript en une demande d’image pour la collecte de données, utilise les variables `hier1` - `hier5`. Consultez la section [hier](/help/implement/vars/page-vars/hier.md) dans le guide d’utilisation de l’implémentation pour obtenir des instructions de mise en œuvre.

## Éléments de dimension

Étant donné que les hiérarchies contiennent des chaînes personnalisées dans votre implémentation, votre entreprise détermine les éléments de dimension de chaque hiérarchie. Veillez à enregistrer l’objectif de chaque hiérarchie et des éléments de dimension standard dans un [document de conception de solution](/help/implement/prepare/solution-design.md).
