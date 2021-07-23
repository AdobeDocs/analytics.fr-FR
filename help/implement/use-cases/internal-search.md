---
title: Capture des termes de recherche interne
description: Utilisez une variable personnalisée pour capturer des termes de recherche interne.
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 2%

---


# Capture des termes de recherche interne

Les rapports de recherche interne font partie intégrante de nombreuses organisations et ne sont pas une dimension prête à l’emploi d’Adobe Analytics. Toutefois, avec un effort de mise en oeuvre minimal, les rapports de termes de recherche interne peuvent facilement être capturés.

## Conditions préalables

[Validation d’une mise en oeuvre de développement et publication en production](../launch/validate-publish-prod.md) : Cette page suppose que vous disposez d’une mise en oeuvre de base et que vous voyez des demandes d’image Adobe Analytics dans le débogueur Adobe.

## Créer un eVar pour la recherche interne

Suivez [L’administrateur des variables de conversion](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) pour créer un nouvel eVar dédié à la recherche interne. Donnez à l’eVar un nom facilement reconnaissable (par exemple, &quot;terme de recherche interne&quot;) et enregistrez le nouvel eVar dans le [document de conception de solution](../prepare/solution-design.md) de votre entreprise.

## Déterminer le mot-clé de recherche interne

La plupart des recherches internes utilisent des chaînes de requête pour transmettre des données de mots-clés entre les pages. Utilisez la recherche interne de votre site et notez l’URL sur la page des résultats de la recherche :

`https://example.com/search.html?q=kittens`

Si la recherche interne de votre site n’utilise pas l’URL, recherchez le terme recherché à d’autres emplacements, comme une couche de données ou un cookie. Contactez votre équipe de développement de site si vous ne savez pas où trouver le terme de recherche interne.

## Affectation du paramètre de chaîne de requête à un élément de données

Suivez la section [Mappage des objets de couche de données aux éléments de données](../launch/layer-to-elements.md). Lors de la sélection du **[!UICONTROL Type d’élément de données]**, sélectionnez **[!UICONTROL Paramètre de chaîne de requête]** au lieu de **[!UICONTROL Variable JavaScript]**. Insérez le paramètre de chaîne de requête souhaité (généralement `q`) dans le champ de texte.

## Mise en correspondance de l’élément de données avec l’eVar

Suivez la procédure [Mappage des éléments de données aux variables Analytics](../launch/elements-to-variable.md). Veillez à sélectionner le même eVar que celui créé dans les paramètres de la suite de rapports.

## Commencer à déployer des balises

Suivez la section [Déploiement d’une implémentation Analytics vers un environnement de développement](../launch/deploy-dev.md). Une fois que vous avez confirmé qu’il fonctionne dans votre environnement de développement, vous pouvez [valider une mise en oeuvre de développement et publier en production](../launch/validate-publish-prod.md).

## Création de rapports dans Workspace

Donnez un certain temps à votre mise en oeuvre pour collecter des données, puis vous pouvez commencer à utiliser la dimension dans Analysis Workspace.

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Si vous n’êtes pas automatiquement connecté à Adobe Analytics, cliquez sur l’icône à neuf carrés en haut à droite, puis sélectionnez **[!UICONTROL Analytics]**.
3. Cliquez sur l’onglet **[!UICONTROL Espace de travail]** et créez un projet.
4. Recherchez le nom de l’eVar que vous avez créé sous Dimensions et faites-le glisser sur le canevas de l’espace de travail.
