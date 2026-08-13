---
title: Actualisations
description: Nombre d’actualisations de la page.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
TQID: https://experienceleague.adobe.com/Jhm8-usZH-SLOzUvNIC3hdoKDMkm9T5mnCUeeMRga7E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 132
ht-degree: 21%

---

# Actualisations

La [mesure Rechargements](overview.md) indique le nombre de fois qu’un élément de dimension était présent lors d’un rechargement. Un visiteur actualisant son navigateur est la méthode la plus courante pour déclencher une actualisation.

## Méthode de calcul de cette mesure

Cette mesure comptabilise le nombre d’accès pour lesquels la dimension [Page](../dimensions/page.md) contient la même valeur que l’accès précédent.

Le concept de rechargement s’applique à la dimension Page , quelle que soit la dimension que vous utilisez dans les rapports. Par exemple, si vous utilisez [eVar1](../dimensions/evar.md) comme dimension et Rechargements comme mesure, le tableau indique le nombre de fois où chaque valeur eVar était présente lors d’un rechargement (deux valeurs de page consécutives). Il n’affiche pas le nombre de fois que deux valeurs eVar1 consécutives étaient présentes.
