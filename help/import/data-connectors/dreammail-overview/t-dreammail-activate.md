---
description: Utilisez l’assistant de configuration des connecteurs de données Adobe pour configurer l’intégration.
seo-description: Utilisez l’assistant de configuration des connecteurs de données Adobe pour configurer l’intégration.
seo-title: Activer l’intégration
title: Activer l’intégration
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
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
| UID d’intégration | Spécifiez votre UUID d'intégration DreamMail. |
| Nom du client | Indiquez le nom du client DreamMail. |
| Nom du site | Indiquez le nom du site DreamMail. |
| Rebonds | Nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de remise. |
| Livré | Nombre de remises de messages réussies. |
| Erreurs de remise | Envoi de messages infructueux. |
| Ouvre HTML | Nombre de visiteurs qui ont ouvert le message électronique. |
| Invalids | Nombre d'adresses électroniques non valides. |
| Campagne | Identifiant de campagne marketing. |
| Passe le long | L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. |
| Email eVar | Adresse électronique du système DreamMail. Cette "eVar de courriel" est associée au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) extrait dans le système DreamMail et peut être utilisé à des fins de remarketing. |
| Événement Spotlight | Événement pouvant être exporté dans des segments de remarketing. |
| Points phares des achats | Événement pouvant être exporté dans des segments de remarketing. |
| Points phares | Evénement de recettes pouvant être exporté dans des segments de remarketing. |
| TotalClics | L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. |
| Segments | Cette intégration crée les segments définis par les partenaires affichés dans la section Segments de partenaire. De plus, vous pouvez sélectionner des segments existants au niveau de la suite de rapports à inclure dans l’intégration. |
|  Demandes d’accès | Activez les privilèges d’accès recommandés. |
| Collecte de données | Sélectionnez Module **JavaScript** si vous souhaitez utiliser le module externe s_code.js comme modèle de collecte pour cette intégration (voir ). Sélectionnez Solution **** automatisée si vous souhaitez utiliser un modèle de collecte automatisée pour cette intégration, puis spécifiez les identifiants uniques utilisés pour cette intégration. Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration :<ul><li>Paramètre de chaîne de requête d’ID de message : Cette valeur représente l’ID de message ajouté à l’URL de la page d’entrée par votre partenaire de messagerie.</li><li>Paramètre de chaîne de requête d’ID de destinataire : Cette valeur représente l’ID du destinataire annexé à l’URL de la page d’entrée par votre partenaire de messagerie.</li></ul> |
| Génération de tableaux de bord et de signets | Générer automatiquement un tableau de bord et des signets pour l’intégration. |
