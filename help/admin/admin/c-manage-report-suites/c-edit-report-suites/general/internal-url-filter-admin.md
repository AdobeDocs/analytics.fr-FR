---
description: Les filtres URL internes identifient les référents que vous considérez comme internes à votre site. Ils permettent de compiler des données dans les rapports de sources de données et de filtrer le trafic interne.
title: Filtres URL internes
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 2beb4cd38fc8b48e2b34468a4570f7168aeacb78
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 30%

---


# Filtres URL internes

Les filtres URL internes vous permettent d’identifier les référents que vous considérez comme internes à votre site. Ils permettent de compiler des données dans les rapports de sources de données et de filtrer le trafic interne.

Un référent, ou une page référente, est habituellement la page à partir de laquelle un visiteur arrive sur votre site. Pour éviter de biaiser les données, vous pouvez filtrer les référents. Les rapports excluent les référents filtrés de la  dimension [Référent](/help/components/dimensions/referrer.md), de la dimension [domaines référents](/help/components/dimensions/referring-domain.md) et d’autres dimensions de source de trafic.

## Affichage des filtres d’URL internes existants

>[!NOTE]
>
>Certaines suites de rapports ont un filtre d’URL interne d’un point (.) configuré par défaut. Lorsque ce filtre existe, tout le trafic est classé comme interne. Les rapports Référent ne fonctionnent pas avant le point (.) est supprimé.

Pour vérifier quels filtres d’URL internes sont configurés pour une suite de rapports : <!-- I don't see the period in my instance? Is the following information valid? "To avoid this, remove the rule listing a period (.) as a filter, and add your own site. The reason why a period is the default internal URL filter is to allow data to be collected in the Pages report. If hits do not match internal URL filters, all pages come up as Other. A period is always somewhere in the URL, which guarantees the Pages report is populated.")-->

1. Sélectionner **[!UICONTROL Administration]** > **[!UICONTROL Suites de rapports]** pour accéder au Gestionnaire de suites de rapports.

1. Sélectionnez la suite de rapports dans laquelle vous souhaitez vérifier les filtres d’URL internes configurés, puis sélectionnez **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Filtres URL internes]**.

   Tous les filtres existants sont répertoriés dans la variable [!UICONTROL **Filtres actuels**] .

## Ajout d’un filtre d’URL interne à une suite de rapports

1. Sélectionner **[!UICONTROL Administration]** > **[!UICONTROL Suites de rapports]** pour accéder au Gestionnaire de suites de rapports.

1. Sélectionnez la suite de rapports dans laquelle vous souhaitez ajouter un filtre URL interne, puis sélectionnez **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Filtres URL internes]**.

1. Dans la section Ajouter un filtre , dans le champ fourni, commencez à saisir l’URL de la page à filtrer, puis sélectionnez [!UICONTROL **Ajouter**].

   L’URL que vous avez ajoutée est maintenant visible dans la variable [!UICONTROL **Filtres actuels**] .
