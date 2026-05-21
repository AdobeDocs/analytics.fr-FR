---
title: Copier les règles de traitement
description: Découvrez comment copier des règles de traitement d’une suite de rapports à une autre.
feature: Processing Rules
role: Admin
exl-id: bb34ecac-0512-4cff-9ef0-72db2dcabc03
TQID: https://experienceleague.adobe.com/oTt61LKoudFaDmgFqCXE3K3t-ni-Twjh5tHaHM4ATg0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 253
ht-degree: 0%

---

# Copie de règles de traitement entre des suites de rapports

La copie de règles de traitement vous évite de recréer manuellement la même logique dans plusieurs suites de rapports. Vous pouvez utiliser la fonction de copie pour partager facilement la fonctionnalité de règles de traitement dans de nombreuses suites de rapports ou pour copier la fonctionnalité testée d’une suite de rapports de développement vers une suite de rapports de production.

**[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > Sélectionner une suite de rapports > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de traitement]** > **[!UICONTROL Copier les règles de traitement]**

Cette interface offre deux options :

* **Remplacer toutes les règles de traitement** : cette option supprime toutes les règles de traitement de la suite de rapports de destination, puis ajoute toutes les règles de traitement à la suite de rapports de destination dans le même ordre. Impossible de sélectionner un nombre limité de règles de traitement à remplacer.
* **Ajouter des règles de traitement spécifiques** : cette option permet de sélectionner une ou plusieurs règles de traitement. Les règles ajoutées sont ajoutées à la fin de la liste des règles de traitement dans chaque suite de rapports de destination. Tenez compte de l’ordre des règles de traitement et des règles qui existent déjà lors de l’ajout de règles à chaque suite de rapports de destination.

Lors de la sélection de règles de traitement auxquelles ajouter ou de suites de rapports vers lesquelles copier des données, vous pouvez utiliser `Ctrl`/`Cmd` + `Click` pour sélectionner plusieurs règles de traitement ou suites de rapports. Une fois que vous avez sélectionné les suites de rapports vers lesquelles effectuer la copie, cliquez sur **[!UICONTROL Copier]** et confirmez la fenêtre modale qui s’affiche.

>[!WARNING]
>
>Les règles de traitement affectent directement la collecte de données et peuvent entraîner une perte de données si elles sont utilisées de manière incorrecte. Testez toujours les règles de traitement dans une suite de rapports de développement avant de les copier dans une suite de rapports de production afin de limiter les problèmes de qualité des données.
