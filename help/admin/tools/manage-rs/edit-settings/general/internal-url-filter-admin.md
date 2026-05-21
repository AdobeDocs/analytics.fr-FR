---
description: Les filtres URL internes identifient les référents que vous considérez comme internes à votre site. Ils permettent de compiler des données dans les rapports de sources de données et de filtrer le trafic interne.
title: Filtres URL internes
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
TQID: https://experienceleague.adobe.com/J78ImTXRPFm6aMHqrxJXZOUVyG-ETnutipYYo2wrofc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 221
ht-degree: 31%

---

# Filtres d’URL internes

Les filtres d’URL internes vous permettent d’identifier les référents que vous considérez comme internes à votre site. Ils permettent de compiler des données dans les rapports de sources de données et de filtrer le trafic interne.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Filtres d’URL internes]**

Un référent, ou une page référente, est habituellement la page à partir de laquelle un visiteur arrive sur votre site. Pour éviter de biaiser les données, vous pouvez filtrer les référents. Les dimensions qui reposent sur des filtres d’URL internes incluent [Référent](/help/components/dimensions/referrer.md), [Domaine référent](/help/components/dimensions/referring-domain.md), [Canaux marketing](/help/components/dimensions/marketing-channel.md) et d’autres dimensions de source de trafic.

[Règles de traitement des canaux marketing](../marketing-channels/mc-proc-rules.md) indiquez « [!UICONTROL Correspond aux filtres d’URL internes] » comme critères possibles de la règle.

>[!IMPORTANT]
>
>Certaines suites de rapports comportent un filtre d’URL interne d’un point (`.`) configuré par défaut. Lorsque ce filtre existe, tout le trafic est classé comme interne. Les rapports du référent ne fonctionnent pas tant que ce filtre n’est pas supprimé et remplacé par un ou plusieurs domaines internes souhaités.

* Affichez tous les filtres existants sous la section **[!UICONTROL Filtres actuels]**.
* Ajoutez un filtre à l&#39;aide de la zone de texte située sous la section **[!UICONTROL Ajouter un filtre]**, puis cliquez sur **[!UICONTROL Ajouter]**.

Les filtres fonctionnent en utilisant la logique **contient** par rapport à l’URL complète. Adobe recommande d’omettre le protocole (`https://`) et les sous-domaines lors de la création de filtres, sauf si le trafic provenant de sous-domaines distincts est souhaité comme trafic externe.
