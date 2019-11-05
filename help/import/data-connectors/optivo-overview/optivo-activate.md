---
description: Utilisez l’assistant de configuration des connecteurs de données Adobe pour configurer l’intégration.
seo-description: Utilisez l’assistant de configuration des connecteurs de données Adobe pour configurer l’intégration.
seo-title: Activer l’intégration
title: Activer l’intégration
uuid: 3b2acdb8-9a1f-4f17-92f2-6a3780a8f626
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# Activer l’intégration{#activate-the-integration}

Utilisez l’assistant de configuration des connecteurs de données Adobe pour configurer l’intégration.

1. Démarrez [Data Connectors](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) et cliquez sur **[!UICONTROL + Ajouter nouveau]** pour [ajouter une nouvelle intégration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. Dans la liste **[!UICONTROL Afficher]** , sélectionnez **[!UICONTROL Par nom]** et faites glisser l'intégration du [!DNL ~partenaire~] vers un emplacement de module externe vide.
1. Renseignez l’assistant d’intégration à l’aide des informations du tableau suivant :

| Champ | Description |
|--- |--- |
| Suite de rapports | Suite de rapports qui reçoit les données de cette intégration. |
| Nom d’intégration | Spécifiez le nom d’intégration que les Connecteurs de données affichent dans la liste d’intégration active de la suite de rapports. |
| Adresse électronique | Indiquez une adresse électronique pour recevoir des informations relatives à l’intégration. |
| ID de compte | Identificateur unique attribué à votre organisation par votre fournisseur de services de messagerie. Elle sera utilisée lors de la demande de données de campagne par courrier électronique (ex. # Envoyé, # Ouvert, # Cliqué, etc.) à partir des segments de visiteurs et de les envoyer à votre fournisseur de services de messagerie. |
| Recipient ID | Cet ID est une représentation codée ou numérique d'une adresse électronique du système de messagerie optivo®. Cet "ID de destinataire" est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui est extrait dans le système de messagerie optivo® et peut être utilisé à des fins de remarketing. |
| ID du message | (Obligatoire) Stocke l’ID de publipostage unique. Ces dimensions de classification sont créées par l’assistant Connecteurs de données pour l’ID de message : <br>a)**Campagnes**: Campagnes associées au message. <br>b)**Canal**: Le canal de transmission, c'est constamment "optivo Broadmail". <br>c)Code **** pays : Ce champ contient le code pays du pays d’origine de l’expéditeur. C'est un "DE" constant. <br>d) Outil **de** livraison : Méthode de transmission, toujours "Email".<br> e) Nom **du** message : Nom de l'envoi, tel qu'il est configuré dans optivo® Broadmail. <br>f) Date **de** début : Horodatage du début de cet envoi. |
| Heure de clic après publication | (Obligatoire) Cette opération est nécessaire pour transmettre des informations sur une action de destinataire à optivo® Broadmail après que le destinataire a cliqué sur un lien dans un courrier. |
| Produit après clic | (Obligatoire) Cette opération est nécessaire pour transmettre des informations sur une action de destinataire à optivo® Broadmail après que le destinataire a cliqué sur un lien dans un courrier. |
| Action de post-clic | (Obligatoire) Cette opération est nécessaire pour transmettre des informations sur une action de destinataire à optivo® Broadmail après que le destinataire a cliqué sur un lien dans un courrier. |
| Rebond net | (Obligatoire) Spécifiez l’événement Adobe Analytics qui stocke les données de rebonds en dur importées à partir du système de messagerie électronique. Nombre de messages électroniques qui n’ont pas été envoyés aux destinataires et qui sont considérés comme non livrables en permanence. |
| Rebond léger | (Obligatoire) Spécifiez l’événement Adobe Analytics qui stocke les données de rebonds logiciels importées du système de messagerie électronique. Nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de remise. |
| Cliqué | (Obligatoire) Spécifiez l’événement Adobe Analytics qui stocke les données sur les clics par courrier électronique importées du système de messagerie. L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. |
| Ouvert | (Obligatoire) Spécifiez l’événement Adobe Analytics qui stocke les données ouvertes par courrier électronique importées du système de messagerie. L’événement Ouvert vous permet de voir le nombre de visiteurs qui ont ouvert le message électronique. |
| Envoyé | (Obligatoire) Spécifiez l’événement Adobe Analytics qui stocke les données envoyées par courrier électronique importées du système de messagerie. L’événement Envoyé vous permet de voir le nombre de messages électroniques envoyés. |
| Non abonné | (Obligatoire) Spécifiez l’événement Adobe Analytics qui stocke les données de désabonnement par courrier électronique importées du système de messagerie. L’événement Désabonné vous permet de voir le nombre de visiteurs qui ont ouvert le message électronique, puis cliqué sur le lien Désabonner pour exclure les futurs messages électroniques de votre organisation. |
| Segments | Activez les segments existants à utiliser avec cette intégration (facultatif). |
|  Demandes d’accès | Activez les privilèges d’accès recommandés. |
| Collecte de données | Sélectionnez Module **JavaScript** si vous souhaitez utiliser le module externe s_code.js comme modèle de collecte pour cette intégration. Sélectionnez Solution **** automatisée si vous souhaitez utiliser un modèle de collecte automatisée pour cette intégration, puis spécifiez les identifiants uniques utilisés pour cette intégration. Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration :<ul><li>Paramètre de chaîne de requête d’ID de message : Cette valeur représente l’ID de message ajouté à l’URL de la page d’entrée par votre partenaire de messagerie.</li><li>Paramètre de chaîne de requête d’ID de destinataire : Cette valeur représente l’ID du destinataire annexé à l’URL de la page d’entrée par votre partenaire de messagerie.</li></ul> |
| Génération de tableaux de bord et de signets | Générer automatiquement un tableau de bord et des signets pour l’intégration. |
