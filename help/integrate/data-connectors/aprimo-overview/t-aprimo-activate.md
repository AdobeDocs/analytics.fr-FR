---
description: Utilisez l'assistant de configuration des connecteurs de données Adobe pour configurer l'intégration.
seo-description: Utilisez l'assistant de configuration des connecteurs de données Adobe pour configurer l'intégration.
seo-title: Activer l'intégration
title: Activer l'intégration
uuid: 0 a 5 d 2 d 45-5133-4259-96 ce-c 992 a 1 e 314 ee
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a3310ec57ce4c68539f07e0d294c8175742c49dc

---


# Activate the Integration {#activate-the-integration}

Utilisez l'assistant de configuration des connecteurs de données Adobe pour configurer l'intégration.

1. Start [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Terminez l'Assistant d'intégration à l'aide des informations du tableau suivant :

| Champ | Description |
|--- |--- |
| Suite de rapports | Suite de rapports qui reçoit les données de cette intégration. |
| Nom d’intégration | Spécifiez le nom d'intégration affiché par les Connecteurs de données dans la liste d'intégration active de la suite de rapports. |
| ID de compte | Indiquez votre ID de compte Aprimo. |
| Recipient ID | Cet ID est une représentation numérique ou numérique d'une adresse électronique à partir du système Aprimo. Cet « ID de destinataire » est associé au comportement des visiteurs en aval sur l'ID du destinataire du site (abandon de panier, achats, etc.) extrait dans le système Aprimo et peut être utilisé à des fins de remarketing. |
| Cliqué | (Obligatoire) Spécifiez l'événement Adobe Analytics qui stocke les données avec clic sur les données importées depuis le système de courrier électronique. L'événement Clicked vous permet de voir le nombre de visiteurs qui ont cliqué sur le courriel. |
| ID de message | (Obligatoire) Stocke l'identifiant de messagerie unique. |
| Ouvert | (Obligatoire) Spécifiez l'événement Adobe Analytics qui stocke les données ouvertes par courrier électronique importées à partir du système de courrier électronique. L'événement Ouvert vous permet de voir le nombre de visiteurs qui ont ouvert le courriel. |
| Recipient ID | (Obligatoire) Stocke l'identifiant visiteur unique. |
| Envoyé | (Obligatoire) Spécifiez l'événement Adobe Analytics qui stocke les données envoyées par courrier électronique importées à partir du système de courrier électronique. L'événement Envoyé vous permet de voir le nombre de courriers électroniques envoyés. |
| Rebonds | (Obligatoire) Spécifiez l'événement Adobe Analytics qui stocke les données de l'e-mail Total bounces importées depuis le système de courrier électronique. L'événement Total-retours vous permet de voir le nombre de messages électroniques qui n'ont pas été remis aux destinataires en raison d'un problème de remise. |
| Désabonné | (Obligatoire) Spécifiez l'événement Adobe Analytics qui stocke les données de désabonnement de courriel importées du système de courrier électronique. L'événement Non abonné vous permet de voir le nombre de visiteurs qui ont ouvert le courriel mais, d'autre part, cliquent sur le lien Désabonner pour exclure les futurs courriers électroniques de votre organisation. |
| Segments | Cette intégration crée les segments définis par le partenaire affichés dans la section Segments partenaires. De plus, vous pouvez sélectionner des segments au niveau de la suite de rapports existants à inclure dans l'intégration. |
| Demandes d'accès | Activez les privilèges d'accès recommandés. |
| Collecte de données | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. |
Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration :
<ul><li>Paramètre de chaîne de requête d'ID de message : Cette valeur représente l'ID de message annexé à l'URL de la page d'entrée par votre partenaire de courrier électronique.</li>
<li>Paramètre de chaîne de requête d'ID du destinataire : Cette valeur représente l'ID de destinataire annexe à l'URL de la page d'entrée par votre partenaire de messagerie.</li></ul>|
| Tableau de bord Génération de signets | Générez automatiquement un tableau de bord et des signets pour l'intégration.|
