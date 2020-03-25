---
description: Utilisez l’assistant de configuration des Data Connectors Adobe pour configurer l’intégration.
title: Activation de l’intégration
uuid: 3b2acdb8-9a1f-4f17-92f2-6a3780a8f626
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Activation de l’intégration {#activate-the-integration}

Utilisez l’assistant de configuration des Data Connectors Adobe pour configurer l’intégration.

1. Démarrez [Data Connectors](https://marketing.adobe.com/resources/help/fr_FR/genesis/c_overview.html) et cliquez sur **[!UICONTROL + Ajouter nouveau]** pour [ajouter une nouvelle intégration](https://marketing.adobe.com/resources/help/fr_FR/genesis/t_add_integration.html).
1. Dans la liste **[!UICONTROL Affichage]**, sélectionnez **[!UICONTROL Par nom]** et faites glisser l’intégration du [!DNL ~Partner~] vers un emplacement de plug-in vide.
1. Renseignez l’assistant d’intégration à l’aide des informations du tableau suivant :

| Champ | Description |
|--- |--- |
| Suite de rapports | Suite de rapports qui reçoit les données de cette intégration. |
| Nom d’intégration | Indiquez le nom de l’intégration que les Data Connectors affichent dans la liste d’intégration active de la suite de rapports. |
| Adresse électronique | Précisez une adresse électronique où recevoir le rapport. |
| ID de compte | Identificateur unique attribué à votre organisation par votre fournisseur de services de messagerie. Il sera utilisé lors de la demande de données de campagne par e-mail (ex. # Envoyé, # Ouvert, # Cliqué, etc.) à partir des segments de visiteurs et envoyé à votre fournisseur de services de messagerie. |
| Recipient ID | Cet identifiant est une représentation codée ou numérique d’une adresse électronique du système optivo® broadmail. Cet « ID de destinataire » est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui provient du système optivo® broadmail et peut être utilisé à des fins de remarketing. |
| ID de message | (Obligatoire) Stocke l’ID de publipostage unique. Ces dimensions de classification sont créées par l’assistant des Data Connectors pour l’ID de message : <br>a)**Campaigns** : campagnes associées au message. <br>b)**Canal** : le canal de transmission, il s’agit pour l’instant de « optivo Broadmail ». <br>c)**Code pays** : ce champ contient le code pays du pays d’origine de l’expéditeur. C’est un « DE » constant. <br>d) **Outil de livraison** : méthode de transmission, toujours « E-mail ».<br> e) **Nom du message** : nom du publipostage, tel qu’il est configuré dans optivo® Broadmail. <br>f) **Date de début** : horodatage du début de ce publipostage. |
| Heure post click | (Obligatoire) Cette donnée est nécessaire pour transmettre des informations sur une action du destinataire à optivo® broadmail, une fois que le destinataire a cliqué sur un lien dans un mail. |
| Produit post click | (Obligatoire) Cette donnée est nécessaire pour transmettre des informations sur une action du destinataire à optivo® broadmail, une fois que le destinataire a cliqué sur un lien dans un mail. |
| Type d’actions post click | (Obligatoire) Cette donnée est nécessaire pour transmettre des informations sur une action du destinataire à optivo® broadmail, une fois que le destinataire a cliqué sur un lien dans un mail. |
| Hard Bounce | (Obligatoire) Indiquez l’événement Adobe Analytics qui stocke les données des hard bounces importées depuis le système de messagerie. Nombre de messages électroniques qui n’ont pas été remis aux destinataires et sont considérés comme non livrables de façon permanente. |
| Soft Bounce | (Obligatoire) Indiquez l’événement Adobe Analytics qui stocke les données des soft bounces importées depuis le système de messagerie. Nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de livraison. |
| Cliqué | (Obligatoire) Indiquez l’événement Adobe Analytics qui stocke les données Cliqué du courrier électronique importées depuis le système de messagerie. L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. |
| Ouvert | (Obligatoire) Indiquez l’événement Adobe Analytics qui stocke les données Ouvert du courrier électronique importées du système de messagerie. L’événement Ouvert vous permet d’afficher le nombre de visiteurs qui ont ouvert le message électronique. |
| Envoyé | (Obligatoire) Indiquez l’événement Adobe Analytics qui stocke les données Envoyé du courrier électronique importées du système de messagerie. L’événement Envoyé vous permet d’afficher le nombre de messages électroniques envoyés. |
| Désabonné | (Obligatoire) Indiquez l’événement Adobe Analytics qui stocke les données Désabonné du courrier électronique importées du système de messagerie. L’événement Désabonné vous permet d’afficher le nombre de visiteurs qui ont ouvert le message électronique, mais qui ont cliqué sur le lien Se désabonner pour ne plus recevoir à l’avenir de messages électroniques de votre organisation. |
| Segments | Activez les segments existants à utiliser avec cette intégration (facultatif). |
| Demandes d’accès | Activez les privilèges d’accès recommandés. |
| Collecte de données | Sélectionnez **Plug-in JavaScript** si vous souhaitez utiliser le plug-in s_code.js comme modèle de collecte pour cette intégration. Sélectionnez **Solution automatisée** si vous souhaitez utiliser un modèle de collecte automatisée pour cette intégration, puis spécifiez les identifiants uniques utilisés pour cette intégration. Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration :<ul><li>Paramètre de chaîne de requête l’ID de message : cette valeur représente l’ID de message associé à l’URL de la page d’entrée par votre partenaire de messagerie.</li><li>Paramètre de chaîne de requête de l’ID de destinataire : cette valeur représente l’ID de destinataire associé à l’URL de la page d’entrée par votre partenaire de messagerie.</li></ul> |
| Génération de tableaux de bord et de signets | Générez automatiquement un tableau de bord et des signets pour l’intégration. |
