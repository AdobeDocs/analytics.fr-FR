---
description: Utilisez l’assistant de configuration des Data Connectors Adobe pour configurer l’intégration.
title: Activation de l’intégration
uuid: 9084b691-291d-49f7-9fa4-abda507e060d
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
| UUID d’intégration | Spécifiez votre UUID d’intégration DreamMail. |
| Nom du client | Indiquez le nom du client DreamMail. |
| Nom du site | Indiquez le nom du site DreamMail. |
| Rebonds | Nombre de messages électroniques qui n’ont pas été remis aux destinataires en raison d’un problème de livraison. |
| Distribué | Nombre de messages distribués avec succès. |
| Erreurs de livraison | Envoi de messages infructueux. |
| Ouverture HTML | Nombre de visiteurs qui ont ouvert le message électronique. |
| Non valide | Nombre d’adresses électroniques non valides. |
| Campagne | Identifiant de campagne marketing. |
| Transmis | L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. |
| Email eVar | Adresse électronique du système DreamMail. Cet « Email eVar » est associé au comportement des visiteurs en aval sur le site (abandons de panier, achats, etc.) qui provient du système DreamMail et peut être utilisé à des fins de remarketing. |
| Événement Spotlight | Événement pouvant être exporté dans des segments de remarketing. |
| Achats Spotlight | Événement pouvant être exporté dans des segments de remarketing. |
| Valeurs Spotlight | Événement de chiffre d’affaires pouvant être exporté dans des segments de remarketing. |
| TotalClics | L’événement Cliqué vous permet d’afficher le nombre de visiteurs qui ont cliqué sur le message électronique. |
| Segments | Cette intégration crée les segments définis par les partenaires affichés dans la section Segments de partenaire. De plus, vous pouvez sélectionner des segments existants au niveau de la suite de rapports à inclure dans l’intégration. |
| Demandes d’accès | Activez les privilèges d’accès recommandés. |
| Collecte de données | Sélectionnez **Plug-in JavaScript** si vous souhaitez utiliser le plug-in s_code.js comme modèle de collecte pour cette intégration (voir ). Sélectionnez **Solution automatisée** si vous souhaitez utiliser un modèle de collecte automatisée pour cette intégration, puis spécifiez les identifiants uniques utilisés pour cette intégration. Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration :<ul><li>Paramètre de chaîne de requête de l’ID de message : cette valeur représente l’ID de message associé à l’URL de la page d’entrée par votre partenaire de messagerie.</li><li>Paramètre de chaîne de requête de l’ID de destinataire : cette valeur représente l’ID de destinataire associé à l’URL de la page d’entrée par votre partenaire de messagerie.</li></ul> |
| Génération de tableaux de bord et de signets | Générez automatiquement un tableau de bord et des signets pour l’intégration. |
