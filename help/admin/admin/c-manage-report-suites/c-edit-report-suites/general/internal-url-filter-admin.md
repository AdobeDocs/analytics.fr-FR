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

**[!UICONTROL Analytics]** > **[!UICONTROL Administration]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Filtres URL internes]**

Un référent, ou une page référente, est habituellement la page à partir de laquelle un visiteur arrive sur votre site. Pour éviter de biaiser les données, vous pouvez filtrer les référents. Les Dimensions qui reposent sur des filtres URL internes incluent : [Référent](/help/components/dimensions/referrer.md), [Domaine référent](/help/components/dimensions/referring-domain.md), [Canaux marketing](/help/components/dimensions/marketing-channel.md), ainsi que d’autres dimensions de source de trafic.

[Règles de traitement des canaux marketing](../marketing-channels/c-rules.md) fournir &quot;[!UICONTROL Correspond aux filtres URL internes]&quot; comme critères de règle possibles.

>[!IMPORTANT]
>
>Certaines suites de rapports possèdent un filtre d’URL interne d’un point (`.`) configuré par défaut. Lorsque ce filtre existe, tout le trafic est classé comme interne. Les rapports Référent ne fonctionnent pas tant que ce filtre n’est pas supprimé et remplacé par un ou plusieurs domaines internes souhaités.

* Afficher tous les filtres existants sous le **[!UICONTROL Filtres actuels]** .
* Ajoutez un filtre à l’aide de la zone de texte située sous la balise **[!UICONTROL Ajouter un filtre]** , puis cliquez sur **[!UICONTROL Ajouter]**.

Les filtres fonctionnent avec **contains** par rapport à l’URL complète. Adobe recommande d’ignorer le protocole (`https://`) et des sous-domaines lors de la création de filtres, sauf si le trafic de sous-domaines distincts est souhaité en tant que trafic externe.
