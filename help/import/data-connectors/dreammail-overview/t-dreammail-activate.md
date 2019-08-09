---
description: Utilisez l'assistant de configuration des connecteurs de données Adobe pour configurer l'intégration.
seo-description: Utilisez l'assistant de configuration des connecteurs de données Adobe pour configurer l'intégration.
seo-title: Activer l'intégration
title: Activer l'intégration
uuid: 9084 b 691-291 d -49 f 7-9 fa 4-abda 507 e 060 d
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
| UUID d'intégration | Spécifiez votre UUID d'intégration dreammail. |
| Nom du client | Indiquez votre nom de client dreammail. |
| Nom du site | Indiquez votre nom de site dreammail. |
| Retours retours | nombre de messages électroniques non distribués aux destinataires en raison d'un problème de remise. |
| Livré | Nombre de remises réussies de messages. |
| Erreurs de remise | Envoi de messages non validés. |
| Ouverture HTML | Nombre de visiteurs qui ont ouvert le courrier électronique. |
| Identifiants invalidés | Nombre d'adresses électroniques non valides. |
| Campagne | Identifiant de campagne marketing. |
| Transmettre les cadres | L'événement Clicked vous permet de voir le nombre de visiteurs qui ont cliqué sur le courriel. |
| Email eVar | Adresse électronique du système dreammail. Cette « evar Email » est associée au comportement des visiteurs en aval sur le site (abandon de panier, achats, etc.) extrait dans le système dreammail et peut être utilisé à des fins de remarketing. |
| Evénement Spotlight | Evénement pouvant être exporté dans des segments de remarketing. |
| Achats Spotlight | Evénement pouvant être exporté dans des segments de remarketing. |
| Valeur Spotlight | Evénement Recettes pouvant être exporté dans les segments de remarketing. |
| Totalclicks | L'événement Clicked vous permet de voir le nombre de visiteurs qui ont cliqué sur le courriel. |
| Segments | Cette intégration crée les segments définis par le partenaire affichés dans la section Segments partenaires. De plus, vous pouvez sélectionner des segments au niveau de la suite de rapports existants à inclure dans l'intégration. |
| Demandes d'accès | Activez les privilèges d'accès recommandés. |
| Collecte de données | Sélectionnez **Module JavaScript** si vous souhaitez utiliser le module externe s_ code. js comme modèle de collecte pour cette intégration (voir). Sélectionnez **la solution automatisée** si vous souhaitez utiliser un modèle de collecte automatisé pour cette intégration, puis spécifiez les identifiants uniques utilisés pour cette intégration. Si vous sélectionnez cette option, spécifiez les identifiants uniques utilisés pour cette intégration :<ul><li>Paramètre de chaîne de requête d'ID de message : Cette valeur représente l'ID de message annexé à l'URL de la page d'entrée par votre partenaire de courrier électronique.</li><li>Paramètre de chaîne de requête d'ID du destinataire : Cette valeur représente l'ID de destinataire annexe à l'URL de la page d'entrée par votre partenaire de messagerie.</li></ul> |
| Génération de tableaux de bord et de signets | Générez automatiquement un tableau de bord et des signets pour l'intégration. |