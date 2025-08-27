---
description: Lorsqu’un rapport contient de nombreuses valeurs uniques, Adobe utilise l’élément de dimension Faible trafic pour améliorer les performances du rapport.
title: Valeur de faible trafic dans Adobe Analytics
feature: Metrics, Data Configuration and Collection
exl-id: 6c3d8258-cf75-4716-85fd-ed8520a2c9d5
source-git-commit: 42d044c3c56f13a232b721ef60f64bcf622ffa9f
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 8%

---

# Valeur [!UICONTROL  Faible trafic ] dans Adobe Analytics

Lorsqu’une dimension contient des millions de valeurs uniques, Adobe fournit des fonctionnalités permettant de s’assurer que les valeurs les plus importantes apparaissent dans votre rapport en temps voulu. Les valeurs uniques collectées au-delà d’un certain seuil sont répertoriées sous un élément de dimension intitulé **[!UICONTROL Faible trafic]**.

L’élément de dimension [!UICONTROL Faible trafic] permet à Adobe de s’assurer que les rapports sont renvoyés en temps opportun en prenant des valeurs uniques excessives et en les regroupant.

Notez que la logique [!UICONTROL Faible trafic] fonctionne mieux avec les dimensions dont les éléments se répètent plusieurs fois au cours du mois. Si les éléments de dimension sont presque ou entièrement uniques à chaque accès, le nombre de valeurs uniques atteint rapidement le seuil et toutes les valeurs suivantes pour le mois se retrouvent dans le compartiment [!UICONTROL Faible trafic].

## Saisie des valeurs [!UICONTROL Faible trafic]

Par défaut, un seuil de 2 000 000 **de valeurs uniques** est défini par dimension, par suite de rapports et par mois calendaire. Les éléments Dimension qui dépassent ce seuil de valeur unique sont regroupés sous [!UICONTROL Faible trafic].

* Les éléments Dimension collectés avant l’accès au seuil sont calculés normalement.
* Les éléments Dimension collectés après le dépassement du seuil sont regroupés sous [!UICONTROL Faible trafic].

>[!NOTE]
>La dimension [Page](../components/dimensions/page.md) utilise plusieurs colonnes du serveur principal qui sont toutes prises en compte dans le seuil unique, notamment `pagename`, `page_url`, `first_hit_pagename`, `first_hit_page_url`, `visit_pagename`, `visit_page_url` et `click_context`. Ces colonnes principales peuvent entraîner l’application de la logique [!UICONTROL Faible trafic] bien avant que le nombre d’éléments de dimension Page uniques dans Workspace n’atteigne le seuil.

La limite unique de 2 000 000 peut être modifiée sur une base par dimension. Voir [Modification des seuils de limite uniques](#changing-unique-limit-thresholds) ci-dessous. À la fin d’un mois calendaire, le nombre de valeurs uniques suivies est réinitialisé globalement.

## Comment les valeurs peuvent-elles échapper [!UICONTROL Faible trafic] après avoir dépassé le seuil ?

Si une dimension donnée collecte plus de 2 000 000 de valeurs uniques au cours d’un mois donné, les éléments de dimension individuels peuvent revenir à la création de rapports sur leur propre élément de dimension. Le principal cas d’utilisation de cette fonctionnalité est de permettre le compte rendu des performances des éléments de dimension essentiels qui peuvent recevoir une augmentation de popularité vers la fin du mois après le dépassement du seuil unique. Par exemple, si votre organisation gère un site contenant des millions d’articles et qu’un nouvel article devient populaire vers la fin du mois, vous pouvez toujours analyser la performance de cet article. Cette logique n’est pas destinée à dégrouper tout ce qui obtient un certain nombre d’instances, mais plutôt à offrir une méthode d’analyse du contenu qui reçoit un afflux de trafic.

Les exigences relatives à l’échappement d’un élément de dimension individuel [!UICONTROL Faible trafic] dépendent de nombreux facteurs, dont beaucoup empêchent la possibilité de calculer un seuil exact :

* **Nombre de serveurs qui traitent des données pour la suite de rapports** : les suites de rapports avec plus de trafic nécessitent plus d’instances d’un seul élément de dimension pour échapper [!UICONTROL Faible trafic].
* **Temps écoulé entre chaque instance d’élément de dimension** : les accès contenant un élément de dimension réparti sur la journée nécessitent plus d’instances qu’une vague concentrée d’accès.
* **Nombre de valeurs uniques pour la dimension** : chaque dimension comporte un second seuil défini sur une valeur de 2 100 000 valeurs uniques par défaut. Si le nombre de valeurs uniques dans une dimension dépasse ce seuil supérieur, un filtrage beaucoup plus agressif est appliqué.

Compte tenu des facteurs ci-dessus, attendez-vous à ce que des **centaines, voire des milliers** d’instances pour un seul élément de dimension s’échappent [!UICONTROL Faible trafic] si seul le premier seuil est dépassé. Attendez-vous à ce que des **milliers à des dizaines de milliers** d’instances pour un seul élément de dimension s’échappent [!UICONTROL Faible trafic] si le seuil supérieur est dépassé. Adobe ne garantit pas que les éléments de dimension s’échappent de manière fiable du compartiment [!UICONTROL Faible trafic]. Ce concept est généralement réservé aux éléments de dimension à volume exceptionnellement élevé en fin de mois.

Lorsqu’un élément de dimension échappe au compartiment [!UICONTROL Faible trafic], les instances collectées avant l’afflux de trafic restent sous [!UICONTROL Faible trafic].

## Modification des seuils de limite uniques

Les limites de seuil peuvent parfois être modifiées par dimension. Contactez l’assistance clientèle d’Adobe ou votre équipe Adobe en charge des comptes pour demander ce changement. La mesure dans laquelle les seuils peuvent être augmentés dépend de plusieurs facteurs ; Adobe ne garantit pas que toutes les demandes d’augmentation de seuil puissent être satisfaites. Lorsque vous demandez une modification, incluez :

* l’identifiant de la suite de rapports ;
* La dimension pour laquelle vous souhaitez augmenter le seuil
* Les premier et deuxième seuils souhaités :
   * Le premier seuil (regroupement initial) est défini sur 2 000 000 **** par défaut.
   * Le deuxième seuil (filtrage plus agressif) est défini sur 2 100 000 **** par défaut.

>[!IMPORTANT]
>
>Les modifications de seuils peuvent avoir un impact sur les performances des rapports. Adobe recommande vivement de faire preuve de bon sens lorsque vous demandez une augmentation des valeurs uniques pour une dimension. Augmentez uniquement les limites uniques pour les dimensions qui sont essentielles aux besoins de création de rapports de votre organisation.

Les seuils [!UICONTROL  Faible trafic ] ne sont pas visibles dans l’interface utilisateur d’Analytics. Contactez l’assistance clientèle d’Adobe si vous souhaitez plus d’informations sur les seuils existants.

## Interactions avec d’autres fonctionnalités

Différentes fonctionnalités traitent les valeurs [!UICONTROL Faible trafic] de différentes manières.

* **Data Warehouse:** Dans la plupart des cas, le nombre de valeurs uniques dans les rapports Data Warehouse n’est pas limité. Son architecture unique permet la création de rapports pour un nombre illimité de valeurs uniques. Cependant, les valeurs [!UICONTROL  Faible trafic ] peuvent toujours apparaître dans certains scénarios limités. Il s’agit par exemple des variables de liste, des props de liste, des eVars de marchandisage et des dimensions détaillées des canaux marketing.
* **Segmentation :** si le critère de segment comprend une dimension avec un grand nombre de valeurs uniques, les valeurs capturées sous [!UICONTROL Faible trafic] ne sont pas incluses.
* **Classifications :** les rapports de classification sont également soumis à des limites uniques. Si l’élément de dimension parent d’une classification est inclus sous [!UICONTROL Faible trafic], la valeur n’est pas classée.
   * Les valeurs [!UICONTROL  Faible trafic ] classées par l’intermédiaire de l’importateur sont visibles dans Data Warehouse. <!-- AN-115871 -->
   * [!UICONTROL Faible trafic] les valeurs classées par le créateur de règles *ne peuvent pas* être affichées dans Data Warehouse. <!-- AN-122872 -->
