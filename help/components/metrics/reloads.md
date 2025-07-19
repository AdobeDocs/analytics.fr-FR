---
title: Actualisations
description: Nombre d’actualisations de la page.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
source-git-commit: c9b7c32adfb44a04ab792d12ca049106b3009710
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 21%

---

# Actualisations

La [mesure Rechargements](overview.md) indique le nombre de fois qu’un élément de dimension était présent lors d’un rechargement. Un visiteur actualisant son navigateur est la méthode la plus courante pour déclencher une actualisation.

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre d’accès pour lesquels la dimension [Page](../dimensions/page.md) contient la même valeur que l’accès précédent.

Le concept de rechargement s’applique à la dimension Page , quelle que soit la dimension que vous utilisez dans les rapports. Par exemple, si vous utilisez [eVar1](../dimensions/evar.md) comme dimension et Rechargements comme mesure, le tableau indique le nombre de fois où chaque valeur eVar était présente lors d’un rechargement (deux valeurs de page consécutives). Il n’affiche pas le nombre de fois que deux valeurs eVar1 consécutives étaient présentes.
