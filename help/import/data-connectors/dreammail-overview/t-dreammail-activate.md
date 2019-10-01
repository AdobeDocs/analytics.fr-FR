---
description: Use the Adobe Data Connectors Configuration Wizard to set up the integration.
seo-description: Utilisez l’assistant de configuration des connecteurs de données Adobe pour configurer l’intégration.
seo-title: Activate the Integration
title: Activate the Integration
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Activate the Integration{#activate-the-integration}

Use the Adobe Data Connectors Configuration Wizard to set up the integration.

1. Start Data Connectors and click + Add New to add a new integration.[](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html)****[](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html)
1. In the Show list, select By Name and drag the Partner integration to an empty plug-in slot.********[!DNL ~~]
1. Complete the Integration Wizard using the information in the following table:

| Champ | Description |
|--- |--- |
| Suite de rapports | Suite de rapports qui reçoit les données de cette intégration. |
| Nom d’intégration | Spécifiez le nom d’intégration que les Connecteurs de données affichent dans la liste d’intégration active de la suite de rapports. |
| UID d’intégration | Spécifiez votre UUID d'intégration DreamMail. |
| Nom du client | Indiquez le nom du client DreamMail. |
| Nom du site | Indiquez le nom du site DreamMail. |
| Rebonds | Nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de remise. |
| Livré | Nombre de remises de messages réussies. |
| Erreurs de remise | Envoi de messages infructueux. |
| Ouvre HTML | Nombre de visiteurs qui ont ouvert le message électronique. |
| Invalids | Nombre d'adresses électroniques non valides. |
| Campagne | Identifiant de campagne marketing. |
| Pass Alongs | The Clicked event lets you see the number of visitors who clicked the email message. |
| Email eVar | An email address from the DreamMail system. This "Email eVar" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled into the DreamMail system and can be leveraged for remarketing purposes. |
| Spotlight Event | Event that can be exported in re-marketing segments. |
| Points phares des achats | Event that can be exported in re-marketing segments. |
| Spotlight Value | Revenue event that can be exported in re-marketing segments. |
| TotalClicks | The Clicked event lets you see the number of visitors who clicked the email message. |
| Segments | Cette intégration crée les segments définis par les partenaires affichés dans la section Segments de partenaire. De plus, vous pouvez sélectionner des segments existants au niveau de la suite de rapports à inclure dans l’intégration. |
|  Demandes d’accès | Activez les privilèges d’accès recommandés. |
| Collecte de données | Sélectionnez Module **JavaScript** si vous souhaitez utiliser le module externe s_code.js comme modèle de collecte pour cette intégration (voir ). Sélectionnez Solution **** automatisée si vous souhaitez utiliser un modèle de collecte automatisée pour cette intégration, puis spécifiez les identifiants uniques utilisés pour cette intégration. Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration :<ul><li>Paramètre de chaîne de requête d’ID de message : Cette valeur représente l’ID de message ajouté à l’URL de la page d’entrée par votre partenaire de messagerie.</li><li>Paramètre de chaîne de requête d’ID de destinataire : Cette valeur représente l’ID du destinataire annexé à l’URL de la page d’entrée par votre partenaire de messagerie.</li></ul> |
| Génération de tableaux de bord et de signets | Générer automatiquement un tableau de bord et des signets pour l’intégration. |