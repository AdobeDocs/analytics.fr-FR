---
description: Utilisez l’assistant de configuration des connecteurs de données Adobe pour configurer l’intégration.
title: Activer l’intégration
uuid: 93c59f8e-3cf5-44c1-9a04-22460af93d5d
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

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
| Cliqué | Nombre total de clics par courrier électronique. |
| ID de campagne | Stocke l’ID de message unique. Ceci est souvent stocké dans la variable de campagne. |
| Ouvert | Nombre total d'ouvertures de courrier électronique. |
| Clics sur une personne | Nombre de personnes qui ont cliqué. |
| Traitée | Nombre total de courriers électroniques traités. |
| Broadlog ID | Cet identifiant est une représentation codée ou numérique d’une adresse électronique du système Neolane. Ce "Broadlog ID" est associé au comportement des visiteurs en aval sur le site (abandons, achats, etc.) qui est extrait dans le système Neolane et peut être utilisé à des fins de remarketing. |
| Planifié | Nombre de messages électroniques programmés pour la remise. |
| Envoyé | Nombre de messages électroniques envoyés. |
| Rebonds totaux | Nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de remise. |
| Clics uniques | Nombre de clics distincts. |
| Ouvrages uniques | Nombre d’ouvertures distinctes. |
| Non abonné | Nombre de visiteurs qui ont ouvert le message électronique, puis cliqué sur le lien Désabonner pour exclure les futurs messages électroniques de votre entreprise. |
| Segments | Cette intégration crée les segments définis par les partenaires affichés dans la section Segments de partenaire. De plus, vous pouvez sélectionner des segments existants au niveau de la suite de rapports à inclure dans l’intégration. |
| Demandes d’accès | Activez les privilèges d’accès recommandés. |
| Collecte de données | Sélectionnez Module **JavaScript** si vous souhaitez utiliser le module externe s_code.js comme modèle de collecte pour cette intégration. Sélectionnez Solution **** automatisée si vous souhaitez utiliser un modèle de collecte automatisée pour cette intégration, puis spécifiez les identifiants uniques utilisés pour cette intégration. Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration : <ul><li>Paramètre de chaîne de requête d’ID de message : Cette valeur représente l’ID de message ajouté à l’URL de la page d’entrée par votre partenaire de messagerie.</li><li>Paramètre de chaîne de requête d’ID de destinataire : Cette valeur représente l’ID du destinataire annexé à l’URL de la page d’entrée par votre partenaire de messagerie.</li></ul> |
| Génération de tableaux de bord et de signets | Générer automatiquement un tableau de bord et des signets pour l’intégration. |
