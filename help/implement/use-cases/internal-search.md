---
title: Capture des termes de recherche interne
description: Utilisez une variable personnalisée pour capturer des termes de recherche interne.
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: ht
source-wordcount: '372'
ht-degree: 100%

---


# Capture des termes de recherche interne

Le compte rendu des performances de recherche interne fait partie intégrante de nombreuses organisations. Il ne s’agit pas d’une dimension d’usine d’Adobe Analytics. Toutefois, avec un effort d’implémentation minimal, le compte rendu des performances des termes de recherche interne peut facilement être capturé.

## Conditions préalables

[Validation d’une implémentation de développement et publication en production](../launch/validate-publish-prod.md) : cette page suppose que vous disposez d’une implémentation de base fonctionnelle et que vous voyez une demande d’image Adobe Analytics dans le débogueur Adobe.

## Création d’une eVar pour la recherche interne

Suivez l’[administrateur des variables de conversion](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) pour créer une eVar dédiée à la recherche interne. Donnez à l’eVar un nom facilement reconnaissable (par exemple, « terme pour la recherche interne ») et enregistrez-la dans le [document de conception de solution](../prepare/solution-design.md) de votre organisation.

## Détermination du mot-clé de recherche interne

La plupart des recherches internes utilisent des chaînes de requête pour transmettre des données de mots-clés entre les pages. Utilisez la recherche interne de votre site et notez l’URL sur la page des résultats de la recherche :

`https://example.com/search.html?q=kittens`

Si la recherche interne de votre site n’utilise pas l’URL, recherchez le terme de recherche à d’autres emplacements, comme une couche de données ou un cookie. Contactez l’équipe en charge du développement de votre site si vous ne savez pas où trouver le terme pour la recherche interne.

## Attribution du paramètre de chaîne de requête à un élément de données

Suivez [Mappage des objets de couche de données aux éléments de données](../launch/layer-to-elements.md). Lors de la sélection du **[!UICONTROL Type d’élément de données]**, sélectionnez **[!UICONTROL Paramètre de chaîne de requête]** au lieu de **[!UICONTROL Variable JavaScript]**. Insérez le paramètre de chaîne de requête souhaité (généralement `q`) dans le champ de texte.

## Mappage de l’élément de données à l’eVar

Suivez [Mappage des éléments de données aux variables Analytics](../launch/elements-to-variable.md). Assurez-vous de sélectionner la même eVar que celle créée dans les paramètres de la suite de rapports.

## Commencer à déployer des balises

Suivez [Déploiement d’une implémentation Analytics dans un environnement de développement](../launch/deploy-dev.md). Une fois son fonctionnement confirmé dans votre environnement de développement, vous pouvez procéder à la [Validation d’une implémentation de développement et publication en production](../launch/validate-publish-prod.md).

## Compte rendu des performances dans Workspace

Laissez le temps à votre implémentation de collecter des données. Vous pouvez ensuite commencer à utiliser la dimension dans Analysis Workspace.

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Si vous n’êtes pas automatiquement connecté à Adobe Analytics, cliquez sur l’icône en forme de grille à neuf cases en haut à droite, puis sélectionnez **[!UICONTROL Analytics]**.
3. Cliquez sur l’onglet **[!UICONTROL Workspace]** et créez un projet.
4. Recherchez le nom de l’eVar que vous avez créée sous Dimensions et faites-la glisser dans la zone de travail de Workspace.
