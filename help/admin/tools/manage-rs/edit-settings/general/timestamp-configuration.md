---
description: Combinez les données horodatées et non horodatées au sein d’une seule suite de rapports.
title: Configuration des horodatages
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
role: Admin
TQID: https://experienceleague.adobe.com/x4raBXJrinRqi2LpaWgc-zbzPoHKIELZ3zt5IV8oBWM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 6%

---

# Configuration des horodatages

La page d’administration « [!UICONTROL Configuration des horodatages] » vous permet d’activer **[!UICONTROL Horodatages facultatifs]** pour une ou plusieurs suites de rapports. Ce paramètre vous permet de combiner des données horodatées et non horodatées dans une seule suite de rapports.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Horodatages facultatifs]**

## Paramètre d’horodatage actuel

Cette section affiche la configuration actuelle de l’horodatage pour la suite de rapports sélectionnée. Il peut s’agir de l’une des trois valeurs possibles :

* **Horodatages non autorisés (paramètre `visitorID` pris en charge)**
* **Horodatages requis (le paramètre n’`visitorID` pas pris en charge)**
* **Horodatages facultatifs (le paramètre `visitorID` pris en charge, mais pas sur les accès horodatés)**

Sous ce texte se trouve une case à cocher intitulée **[!UICONTROL Convertir les suites de rapports sélectionnées en horodatages facultatifs]**. Cocher cette case et sélectionner **[!UICONTROL Enregistrer]** Active [!UICONTROL Horodatages facultatifs] pour les suites de rapports sélectionnées.

## Horodatages non autorisés

Lorsque vous envoyez des données à une suite de rapports à l’aide de cette configuration d’horodatage, l’horodatage correspond au moment où les serveurs de traitement Adobe reçoivent l’accès. Si vous tentez de définir la variable [`timestamp`](/help/implement/vars/page-vars/timestamp.md), l’accès est définitivement supprimé.

## Horodatages obligatoires

Lorsque vous envoyez des données à une suite de rapports à l’aide de cette configuration d’horodatage, chaque accès doit inclure la variable [`timestamp`](/help/implement/vars/page-vars/timestamp.md). S’il manque une variable d’implémentation `timestamp` à un accès, celui-ci est définitivement ignoré.

Les données de la session avec horodatage sont conservées pendant 92 jours au maximum. En d’autres termes, une visite est « maintenue ouverte » pendant 92 jours, ce qui permet d’inclure d’autres accès dans la même visite/session. Bien que vous puissiez ajouter des données aux sessions existantes, Adobe recommande d’ajouter les accès dans l’ordre par visiteur. Les accès reçus dans le désordre par visiteur peuvent produire des résultats de création de rapports inattendus, bien que nombre de ces limitations soient atténuées par le traitement de la période de rapport.

## Dates et heures facultatives

Le paramètre « [!UICONTROL Horodatages facultatifs] » vous permet d’intégrer et de générer des rapports sur plusieurs suites de rapports avec ou sans la variable [`timestamp`](/help/implement/vars/page-vars/timestamp.md) . Les cas d’utilisation idéaux pour les [!UICONTROL horodatages facultatifs] incluent :

* Combiner des données horodatées et non horodatées dans la même suite de rapports globale
* Envoyer des données de date et d’heure d’une application mobile vers une suite de rapports globale
* Mettre les applications à niveau pour utiliser le suivi hors ligne sans avoir à créer de suite de rapports

Ce paramètre est activé par défaut pour toutes les nouvelles suites de rapports, sauf si la nouvelle suite de rapports a été copiée à partir d’une suite de rapports avec un paramètre de configuration d’horodatage différent.

>[!WARNING]
>
>Si vous utilisez [!UICONTROL Horodatages facultatifs], ne définissez pas de [`visitorID`](/help/implement/vars/config-vars/visitorid.md) sur les données horodatées. Cette action peut entraîner des données dans le désordre et avoir un impact négatif sur les calculs de temps (comme le temps passé), l’attribution, le nombre de visites/nombres de visites et les rapports de cheminement.

Une fois que vous avez activé [!UICONTROL Horodatages facultatifs], vous ne pouvez plus le désactiver dans cette interface. Dans le scénario improbable où vous souhaitez revenir à un autre paramètre de configuration d’horodatage, contactez l’assistance clientèle d’Adobe.
