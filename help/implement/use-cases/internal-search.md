---
title: Capturer les termes de recherche interne
description: Utilisez une variable personnalisée pour capturer les termes de recherche interne.
translation-type: tm+mt
source-git-commit: 091e4b859addc1780d94d90c8b59748277890241
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 2%

---


# Capturer les termes de recherche interne

Le rapports de recherche interne fait partie intégrante de nombreuses organisations et n&#39;est pas une dimension prête à l&#39;emploi avec Adobe Analytics. Cependant, avec un minimum d&#39;efforts d&#39;implémentation, le rapports des termes de recherche interne peut facilement être capturé.

## Conditions préalables

[Validez une mise en oeuvre de développement et publiez en production](../launch/validate-publish-prod.md): Cette page suppose que vous disposez d’une mise en oeuvre de base et que vous voyez des demandes d’image Adobe Analytics dans le débogueur d’Adobe.

## Créer un eVar pour répondre à la recherche interne

Suivez l’administration [des variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) de conversion pour créer un nouvel eVar dédié à la recherche interne. Attribuez à l’eVar un nom facilement reconnaissable (tel que &quot;terme de recherche interne&quot;) et enregistrez le nouvel eVar dans le document [de conception de](../prepare/solution-design.md)solution de votre entreprise.

## Détermination du mot-clé de recherche interne

La plupart des recherches internes utilisent des chaînes de requête pour transmettre des données de mot-clé entre les pages. Utilisez la recherche interne de votre site et notez l’URL sur la page des résultats de la recherche :

`https://example.com/search.html?q=kittens`

Si la recherche interne de votre site n’utilise pas l’URL, recherchez le terme recherché à d’autres emplacements, tels qu’une couche de données ou un cookie. Contactez votre équipe de développement de site si vous ne savez pas où trouver le terme de recherche interne.

## Affecter un paramètre de chaîne de requête à un élément de données

Follow [Map data layer objects to data elements](../launch/layer-to-elements.md). Lors de la sélection du type **[!UICONTROL d’élément de]** données, sélectionnez le paramètre **[!UICONTROL de chaîne de]** Requête au lieu de la variable **** JavaScript. Placez le paramètre de chaîne de requête souhaité (généralement `q`) dans le champ de texte.

## Faire correspondre l’élément de données à l’eVar

Follow [Map Launch data elements to Analytics variables](../launch/elements-to-variable.md). Veillez à sélectionner le même eVar que celui créé dans les paramètres de la suite de rapports.

## Début du processus de déploiement du lancement

Follow [Deploy an Analytics implementation to a development environment](../launch/deploy-dev.md). Une fois que vous avez confirmé qu’il fonctionne dans votre environnement de développement, vous pouvez [valider une mise en oeuvre de développement et la publier en production](../launch/validate-publish-prod.md).

## Rapports dans Workspace.

Donnez un peu de temps à votre implémentation pour collecter des données, puis vous pouvez début à l’aide de la dimension dans Analysis Workspace.

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Si vous n’êtes pas automatiquement connecté à Adobe Analytics, cliquez sur l’icône en forme de grille 9 en haut à droite de l’écran, puis sélectionnez **[!UICONTROL Analytics]**.
3. Cliquez sur l’onglet **[!UICONTROL Espace de travail]** et créez un projet.
4. Recherchez le nom de l&#39;eVar que vous avez créé sous Dimensions, puis faites-le glisser sur le canevas de l&#39;espace de travail.
