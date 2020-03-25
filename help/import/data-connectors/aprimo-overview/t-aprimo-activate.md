---
description: Utilisez l’assistant de configuration des Data Connectors Adobe pour configurer l’intégration.
title: Activation de l’intégration
uuid: 0a5d2d45-5133-4259-96ce-c992a1e314ee
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
| ID de compte | Indiquez votre ID de compte Aprimo. |
| Recipient ID | Cet ID est une représentation codée ou numérique d’une adresse électronique du système Aprimo. Cet « ID de destinataire » est associé au comportement du visiteur en aval sur l’identifiant destinataire du site (abandons de panier, achats, etc.) qui est transmis dans le système Aprimo et peut être utilisé à des fins de remarketing. |
| Cliqué | (Obligatoire) Indiquez l’événement Adobe Analytics qui stocke les données Cliqué du courrier électronique importées du système de messagerie. L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. |
| ID de message | (Obligatoire) Stocke l’ID de publipostage unique. |
| Ouvert | (Obligatoire) Indiquez l’événement Adobe Analytics qui stocke les données Ouvert du courrier électronique importées du système de messagerie. L’événement Ouvert vous permet d’afficher le nombre de visiteurs qui ont ouvert le message électronique. |
| Recipient ID | (Obligatoire) Stocke l’identifiant visiteur unique. |
| Envoyé | (Obligatoire) Indiquez l’événement Adobe Analytics qui stocke les données Envoyé du courrier électronique importées du système de messagerie. L’événement Envoyé vous permet d’afficher le nombre de messages électroniques envoyés. |
| Retours | (Obligatoire) Indiquez l’événement Adobe Analytics qui stocke les données Rebonds au total du courrier électronique importées du système de messagerie. L’événement Rebonds au total vous permet d’afficher le nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de livraison. |
| Désabonné | (Obligatoire) Indiquez l’événement Adobe Analytics qui stocke les données Désabonné du courrier électronique importées du système de messagerie. L’événement Désabonné vous permet d’afficher le nombre de visiteurs qui ont ouvert le message électronique, mais qui ont cliqué sur le lien Se désabonner pour ne plus recevoir à l’avenir de messages électroniques de votre organisation. |
| Segments | Cette intégration crée les segments définis par les partenaires affichés dans la section Segments de partenaire. De plus, vous pouvez sélectionner des segments existants au niveau de la suite de rapports à inclure dans l’intégration. |
| Demandes d’accès | Activez les privilèges d’accès recommandés. |
| Collecte de données | Sélectionnez **Plug-in JavaScript** si vous souhaitez utiliser le plug-in s_code.js comme modèle de collecte pour cette intégration. |
Sélectionnez **Solution automatisée** si vous souhaitez utiliser un modèle de collecte automatisée pour cette intégration, puis spécifiez les identifiants uniques utilisés pour cette intégration. Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration :
<ul><li>Paramètre de chaîne de requête de l’ID de message : cette valeur représente l’ID de message associé à l’URL de la page d’entrée par votre partenaire de messagerie.</li>
<li>Paramètre de chaîne de requête de l’ID de destinataire : cette valeur représente l’ID de destinataire associé à l’URL de la page d’entrée par votre partenaire de messagerie.</li></ul>|
|Génération des tableaux de bord et des signets|Génère automatiquement un tableau de bord et des signets pour l’intégration.|
