---
description: Les filtres URL internes identifient les référents que vous considérez comme internes à votre site. Ils permettent de compiler des données dans les rapports de sources de données et de filtrer le trafic interne.
title: Filtres URL internes
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 31%

---


# Filtres d’URL internes

Les filtres URL internes vous permettent d’identifier les référents que vous considérez comme internes à votre site. Ils permettent de compiler des données dans les rapports de sources de données et de filtrer le trafic interne.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Filtres URL internes]**

Un référent, ou une page référente, est habituellement la page à partir de laquelle un visiteur arrive sur votre site. Pour éviter de biaiser les données, vous pouvez filtrer les référents. Les Dimensions qui reposent sur des filtres d’URL internes incluent [Referrer](/help/components/dimensions/referrer.md), [Domaine référent](/help/components/dimensions/referring-domain.md), [Canaux marketing](/help/components/dimensions/marketing-channel.md) et d’autres dimensions de source de trafic.

[Les règles de traitement des canaux marketing](../marketing-channels/c-rules.md) fournissent &quot;[!UICONTROL Correspond aux filtres d’URL internes]&quot; comme critères de règle possibles.

>[!IMPORTANT]
>
>Certaines suites de rapports ont un filtre URL interne d’un point (`.`) configuré par défaut. Lorsque ce filtre existe, tout le trafic est classé comme interne. Les rapports Référent ne fonctionnent pas tant que ce filtre n’est pas supprimé et remplacé par un ou plusieurs domaines internes souhaités.

* Affichez tous les filtres existants sous la section **[!UICONTROL Filtres actuels]**.
* Ajoutez un filtre à l’aide de la zone de texte sous la section **[!UICONTROL Ajouter un filtre]**, puis cliquez sur **[!UICONTROL Ajouter]**.

Les filtres fonctionnent à l’aide de la logique **contains** par rapport à l’URL complète. Adobe recommande d’omettre le protocole (`https://`) et les sous-domaines lors de la création de filtres, sauf si le trafic provenant de sous-domaines distincts est souhaité en tant que trafic externe.
