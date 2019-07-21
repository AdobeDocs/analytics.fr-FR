---
description: Créez des règles de traitement des canaux marketing qui déterminent si l’accès d’un visiteur satisfait aux critères affectés à un canal.
seo-description: Créez des règles de traitement des canaux marketing qui déterminent si l’accès d’un visiteur satisfait aux critères affectés à un canal.
seo-title: Création de règles de traitement des canaux marketing
solution: Analytics
subtopic: Canaux marketing
title: Création de règles de traitement des canaux marketing
topic: Reports and Analytics
uuid: 0 e 47634 f -3 c 69-46 db -8 af 4-8 d 0 b 3 d 15 f 7 a 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Création de règles de traitement des canaux marketing

Créez des règles de traitement des canaux marketing qui déterminent si l’accès d’un visiteur satisfait aux critères affectés à un canal.

Elle utilise une règle de courriel comme exemple. Cet exemple part du principe que vous avez ajouté un canal de courriel à votre liste de canaux sur la page Gestionnaire de canaux marketing.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Sélectionnez une suite de rapports.

   La page [!UICONTROL Canaux marketing : Configuration automatique] s’affiche si aucun canal n’est défini dans votre suite de rapports.

   Reportez-vous à la section [Exécution de la configuration automatique](/help/components/c-marketing-channels/c-channel-autosetup.md).

1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Résultat de l’étape](assets/marketing_channel_rules.png)

1. Dans le menu **Ajouter un nouveau jeu de règles**, sélectionnez **[!UICONTROL Courriel]**.

   Dans le cas présent, vous ne sélectionnez pas le canal, mais le modèle qui renseigne quelques-uns des paramètres nécessaires de la règle.

   ![Résultat de l’étape](assets/example_email.png)

   Utilisez la logique booléenne (instructions si / alors) pour configurer une règle. Par exemple, dans une règle de canal de courriel, indiquez les paramètres ou les informations mis en évidence dans l’instruction de règle suivante :

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   In this example, *`<value>`* is the query string parameter that you use for your email campaign, such as *`eml`*.
1. Pour continuer à créer des règles, cliquez sur **[!UICONTROL Ajouter une règle]**.
1. Pour classer les règles par priorité, faites-les glisser à l’emplacement souhaité.
1. Cliquez sur **[!UICONTROL Enregistrer.]**

>[!MORE_LIKE_THIS]
>
>* [Questions fréquentes et exemples](/help/components/c-marketing-channels/c-faq.md)

