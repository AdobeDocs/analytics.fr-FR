---
description: Utilisez l'assistant de configuration des connecteurs de données Adobe pour configurer l'intégration.
seo-description: Utilisez l'assistant de configuration des connecteurs de données Adobe pour configurer l'intégration.
seo-title: Activer l'intégration
title: Activer l'intégration
uuid: 93 c 59 f 8 e -3 cf 5-44 c 1-9 a 04-22460 af 93 d 5 d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Activer l'intégration{#activate-the-integration}

Utilisez l'assistant de configuration des connecteurs de données Adobe pour configurer l'intégration.

1. Démarrez [les connecteurs de données](https://marketing.adobe.com/resources/help/en_US/genesis/c_overview.html) et cliquez **[!UICONTROL sur + Ajouter nouveau]** pour [ajouter une nouvelle intégration](https://marketing.adobe.com/resources/help/en_US/genesis/t_add_integration.html).
1. Dans la zone **[!UICONTROL Afficher]** , sélectionnez **[!UICONTROL Par nom]** et faites glisser l'intégration [!DNL ~Partenaire~] vers un emplacement de module externe vide.
1. Terminez l'Assistant d'intégration à l'aide des informations du tableau suivant :

| Champ | Description |
|--- |--- |
| Suite de rapports | Suite de rapports qui reçoit les données de cette intégration. |
| Nom d’intégration | Spécifiez le nom d'intégration affiché par les Connecteurs de données dans la liste d'intégration active de la suite de rapports. |
| Cliqué | Nombre total de clics par courrier électronique. |
| ID de campagne | Stocke l'ID de message unique. Elle est souvent stockée dans la variable campaign. |
| Ouvert | Nombre total d'ouvertures de courrier électronique. |
| Clics sur une personne | Nombre de personnes qui ont cliqué dessus. |
| Traité | Nombre total de courriers électroniques traités. |
| Broadlog ID | Cet ID est une représentation numérique ou numérique d'une adresse électronique à partir du système Neolane. Cet « ID Broadlog » est associé au comportement des visiteurs en aval sur le site (panier Broadlog ID abandons, achats, etc.) qui est extrait dans le système Neolane et peut être utilisé à des fins de remarketing. |
| Planifié | Nombre de messages électroniques planifiés pour la remise. |
| Envoyé | Nombre de messages électroniques envoyés. |
| Nombre total de rebonds | nombre de messages électroniques non distribués aux destinataires en raison d'un problème de remise. |
| Clics uniques | Nombre de clics distincts. |
| Ouvertures uniques | Nombre d'ouvertures distinctes. |
| Désabonné | Nombre de visiteurs qui ont ouvert le courrier électronique mais ont cliqué sur le lien Désabonner pour s'exclure des messages électroniques futurs de votre organisation. |
| Segments | Cette intégration crée les segments définis par le partenaire affichés dans la section Segments partenaires. De plus, vous pouvez sélectionner des segments au niveau de la suite de rapports existants à inclure dans l'intégration. |
| Demandes d'accès | Activez les privilèges d'accès recommandés. |
| Collecte de données | Sélectionnez **Module JavaScript** si vous souhaitez utiliser le module externe s_ code. js comme modèle de collecte pour cette intégration. Sélectionnez **la solution automatisée** si vous souhaitez utiliser un modèle de collecte automatisé pour cette intégration, puis spécifiez les identifiants uniques utilisés pour cette intégration. Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration : <ul><li>Paramètre de chaîne de requête d'ID de message : Cette valeur représente l'ID de message annexé à l'URL de la page d'entrée par votre partenaire de courrier électronique.</li><li>Paramètre de chaîne de requête d'ID du destinataire : Cette valeur représente l'ID de destinataire annexe à l'URL de la page d'entrée par votre partenaire de messagerie.</li></ul> |
| Génération de tableaux de bord et de signets | Générez automatiquement un tableau de bord et des signets pour l'intégration. |