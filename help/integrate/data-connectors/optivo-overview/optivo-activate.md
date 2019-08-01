---
description: Utilisez l'assistant de configuration des connecteurs de données Adobe pour configurer l'intégration.
seo-description: Utilisez l'assistant de configuration des connecteurs de données Adobe pour configurer l'intégration.
seo-title: Activer l'intégration
title: Activer l'intégration
uuid: 3 b 2 acdb 8-9 a 1 f -4 f 17-92 f 2-6 a 3780 a 8 f 626
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d10546972c03efae1bc365b7391000a40a79b0a4

---


# Activate the Integration{#activate-the-integration}

Utilisez l'assistant de configuration des connecteurs de données Adobe pour configurer l'intégration.

1. Start [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) and click **[!UICONTROL + Add New]** to [add a new integration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. In the **[!UICONTROL Show]** list, select **[!UICONTROL By Name]** and drag the [!DNL ~Partner~] integration to an empty plug-in slot.
1. Terminez l'Assistant d'intégration à l'aide des informations du tableau suivant :

| Champ | Description |
|--- |--- |
| Suite de rapports | Suite de rapports qui reçoit les données de cette intégration. |
| Nom d’intégration | Spécifiez le nom d'intégration affiché par les Connecteurs de données dans la liste d'intégration active de la suite de rapports. |
| Adresse e-mail | Fournissez une adresse électronique pour recevoir les informations liées à l'intégration. |
| ID de compte | Il s'agit de l'identifiant unique attribué à votre organisation par votre fournisseur de services de messagerie. Elle est utilisée lors de la demande de données de campagne par courriel (par exemple, # Sent, # Open, # Clicked, etc.) et d'envoyer des segments de visiteurs à votre fournisseur de services de messagerie. |
| Recipient ID | Cet ID est une représentation numérique ou numérique d'une adresse électronique issue du système de courrier broadmail optivo®. Cet « ID de destinataire » est associé au comportement des visiteurs en aval sur le site (abandon de panier, achats, etc.) extrait dans le système de messagerie d'optivo® et peut être utilisé à des fins de remarketing. |
| ID de message | (Obligatoire) Stocke l'identifiant de messagerie unique. These classification dimensions are created by the Data Connectors wizard for the Message ID: a)**Campaigns**: Campaigns associated with the message. b)**Channel**: The channel of transmission, this is constantly "optivo broadmail". c)**Country Code**: This field contains the country code of the origin sender country. Il s'agit d'une constante DE. d) **Delivery Tool**: Method of transmission, always "Email". e) **Message Name**: The name of the mailing, as it is configured in optivo® broadmail. f) **Start Date**: Timestamp of the start of this mailing. |
| Heure de clic sur la publication | (Obligatoire) Cette opération est nécessaire pour transmettre des informations sur l'action d'un destinataire à optivo® broadmail après que le destinataire a cliqué sur un lien dans un courrier électronique. |
| Publier un produit | (Obligatoire) Cette opération est nécessaire pour transmettre des informations sur l'action d'un destinataire à optivo® broadmail après que le destinataire a cliqué sur un lien dans un courrier électronique. |
| Action de clic sur les publications | (Obligatoire) Cette opération est nécessaire pour transmettre des informations sur l'action d'un destinataire à optivo® broadmail après que le destinataire a cliqué sur un lien dans un courrier électronique. |
| Rebond hard | (Obligatoire) Spécifiez l'événement Adobe Analytics qui stocke les données hard bounces importées depuis le système de courrier électronique. nombre de messages électroniques qui n'ont pas été remis aux destinataires et qui sont considérés comme non livrables définitivement. |
| Rebond Soft | (Obligatoire) Spécifiez l'événement Adobe Analytics qui stocke les données soft bounces importées depuis le système de courrier électronique. nombre de messages électroniques non distribués aux destinataires en raison d'un problème de remise. |
| Cliqué | (Obligatoire) Spécifiez l'événement Adobe Analytics qui stocke les données d'importation par courrier électronique du système de courrier électronique. L'événement Clicked vous permet de voir le nombre de visiteurs qui ont cliqué sur le courriel. |
| Ouvert | (Obligatoire) Spécifiez l'événement Adobe Analytics qui stocke les données ouvertes par courrier électronique importées à partir du système de courrier électronique. L'événement Ouvert vous permet de voir le nombre de visiteurs qui ont ouvert le courriel. |
| Envoyé | (Obligatoire) Spécifiez l'événement Adobe Analytics qui stocke les données envoyées par courrier électronique importées à partir du système de courrier électronique. L'événement Envoyé vous permet de voir le nombre de courriers électroniques envoyés. |
| Désabonné | (Obligatoire) Spécifiez l'événement Adobe Analytics qui stocke les données de désabonnement par courrier électronique importées depuis le système de courrier électronique. L'événement Non abonné vous permet de voir le nombre de visiteurs qui ont ouvert le courriel mais, d'autre part, cliquent sur le lien Désabonner pour exclure les futurs courriers électroniques de votre organisation. |
| Segments | Activez les segments existants à utiliser avec cette intégration (facultatif). |
| Demandes d'accès | Activez les privilèges d'accès recommandés. |
| Collecte de données | Select **JavaScript Plug-in** if you want to use the s_code.js plug-in as the collection model for this integration. Select **Automated Solution** if you want to use an automated collection model for this integration, then specify the unique identifiers used for this integration. Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration :<ul><li>Paramètre de chaîne de requête d'ID de message : Cette valeur représente l'ID de message annexé à l'URL de la page d'entrée par votre partenaire de courrier électronique.</li><li>Paramètre de chaîne de requête d'ID du destinataire : Cette valeur représente l'ID de destinataire annexe à l'URL de la page d'entrée par votre partenaire de messagerie.</li></ul> |
| Génération de tableaux de bord et de signets | Générez automatiquement un tableau de bord et des signets pour l'intégration. |