---
title: Hiérarchie
description: Dimension personnalisée que vous pouvez utiliser dans les rapports.
feature: Dimensions
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 22%

---

# Hiérarchie

>[!IMPORTANT]
>
>Cette dimension a été abandonnée et n’est pas une dimension disponible dans Analysis Workspace. Adobe recommande d’utiliser plutôt des [eVars](evar.md) et des classifications.

Les hiérarchies sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Elles ne persistent pas au-delà de l’accès défini. Jusqu’à 5 hiérarchies sont disponibles si votre contrat avec Adobe le prend en charge.

## Renseignement des hiérarchies avec des données

Chaque hiérarchie collecte des données de la variable [`h1` - `h5` chaîne de requête](/help/implement/validate/query-parameters.md) dans les demandes d’image. Par exemple, la variable `h1` le paramètre de chaîne de requête collecte des données pour Hiérarchie 1, tandis que la variable `h4` le paramètre de chaîne de requête collecte des données pour la hiérarchie 4.

AppMeasurement, qui compile les variables JavaScript en une demande d’image pour la collecte de données, utilise les variables `hier1` - `hier5`. Voir [hier](/help/implement/vars/page-vars/hier.md) dans le guide d’utilisation de la mise en oeuvre pour obtenir des instructions de mise en oeuvre.

## Éléments de dimension

Comme les hiérarchies contiennent des chaînes personnalisées dans votre implémentation, votre organisation détermine les éléments de dimension de chaque hiérarchie. Veillez à enregistrer l’objectif de chaque hiérarchie et les éléments de dimension standard dans une [document de conception de solution](/help/implement/prepare/solution-design.md).
