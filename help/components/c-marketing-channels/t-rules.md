---
description: Créez des règles de traitement des canaux marketing qui déterminent si l’accès d’un visiteur satisfait aux critères affectés à un canal.
subtopic: Marketing channels
title: Création de règles de traitement des canaux marketing
topic: Reports and analytics
uuid: 0e47634f-3c69-46db-8af4-8d0b3d15f7a8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Création de règles de traitement des canaux marketing

Créez des règles de traitement des canaux marketing qui déterminent si l’accès d’un visiteur satisfait aux critères affectés à un canal.

Elle utilise une règle de courriel comme exemple. Cet exemple part du principe que vous avez ajouté un canal de courriel à votre liste de canaux sur la page Gestionnaire de canaux marketing.

1. Cliquez sur **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Suites de rapports]**.
1. Sélectionnez une suite de rapports.

   La page [!UICONTROL Canaux marketing : Configuration automatique] s’affiche si aucun canal n’est défini dans votre suite de rapports.

   Reportez-vous à la section [Exécution de la configuration automatique](/help/components/c-marketing-channels/c-channel-autosetup.md).

1. Cliquez sur **[!UICONTROL Modifier les paramètres]** &gt; **[!UICONTROL Canaux marketing]** &gt; **[!UICONTROL Règles de traitement des canaux marketing]**.

   ![Résultat de l’étape](assets/marketing_channel_rules.png)

1. Dans le menu **[!UICONTROL Ajouter un nouveau jeu de règles]**, sélectionnez **[!UICONTROL Courriel]**.

   Dans le cas présent, vous ne sélectionnez pas le canal, mais le modèle qui renseigne quelques-uns des paramètres nécessaires de la règle.

   ![Résultat de l’étape](assets/example_email.png)

   Utilisez la logique booléenne (instructions si / alors) pour configurer une règle. Par exemple, dans une règle de canal de courriel, indiquez les paramètres ou les informations mis en évidence dans l’instruction de règle suivante :

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   Dans cet exemple, *`<value>`* est le paramètre de chaîne de requête utilisé pour votre campagne par courrier électronique, tel que *`eml`*,
1. Pour continuer à créer des règles, cliquez sur **[!UICONTROL Ajouter une règle]**.
1. Pour classer les règles par priorité, faites-les glisser à l’emplacement souhaité.
1. Cliquez sur **[!UICONTROL Enregistrer.]**

>[!MORELIKETHIS]
>
>* [Questions fréquentes et exemples](/help/components/c-marketing-channels/c-faq.md)

