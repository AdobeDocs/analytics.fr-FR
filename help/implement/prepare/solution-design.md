---
title: Création d'un document de conception de solution
seo-title: Création d'un document de conception de solution
description: Découvrez ce qu'est un document de conception de solution et comment vous pouvez l'utiliser dans votre organisation.
seo-description: Découvrez ce qu'est un document de conception de solution et comment vous pouvez l'utiliser dans votre organisation.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Création d'un document de conception de solution

Un document de conception de solution (également appelé référence de conception de solution ou document de configuration de la solution) est essentiellement le plan directeur de votre implémentation Analytics. Il définit les critères identifiés par les parties prenantes dans toute votre organisation et les traduit en variables dans Adobe Analytics. Sans aucune, les organisations ont un temps difficile de coordonner les rapports et tendent à ne pas collecter de données importantes.

## Conditions préalables

[Validation de la mise en œuvre et de la publication d'Analytics en production](../implement-with-launch/validate-publish-prod.md) : bien qu'elles ne soient pas directement requises, Adobe conseille de mettre en place une implémentation de base afin que les données critiques soient collectées alors que des besoins d'entreprise supplémentaires sont établis et implémentés.

## Propriété et emplacement du document de conception

* **Déterminez qui dans votre organisation sera responsable de la maintenance du document de conception de la solution.** Ce rôle peut être une personne ou une équipe. Veiller à ce que la conservation de la conception de la solution soit préservée, même par le biais de modifications de rôles ou de restructurations d'organisations. Il s'agit d'un document vivant qui doit être correctement conservé.
* **Déterminez où réside votre document de solution.** Il n'y a pas de meilleur emplacement pour que les documents de conception de solution résident, mais ils restent généralement dans un emplacement interne largement accessible. Par exemple, une feuille de calcul partagée ou un espace de travail collaboratif tel que sharepoint ou un wiki interne. Il n'est pas nécessaire d'être modifiable pour tous, mais il est intéressant que ceux qui ont accès à la création de rapports puissent au moins l'afficher.

## Définition des besoins commerciaux

Lorsque vous déterminez les données à collecter, il est facile de dire « tout », mais cela peut rapidement devenir difficile à gérer et même fournir moins de valeur que de collecter des quantités de données plus concises.

1. **Déterminez vos indicateurs de performances clés.** Que souhaitez-vous finalement faire aux visiteurs ? La réponse à cette question varie selon le secteur industriel et verticalement et peut être plusieurs éléments. Par exemple les achats, les abonnements ou les clics publicitaires.
1. **Déterminez les données les plus importantes à collecter.** Posez vos questions professionnelles à des réponses spécifiques. Les réponses à ces questions fournissent des informations sur la manière d'améliorer vos indicateurs clés de performance.
1. **Répondez à ces questions et déterminez les besoins de votre suivi.** Regroupez-les en dimensions et mesures.
   * Les dimensions sont des variables qui contiennent du texte. Les exemples incluent le terme de recherche interne, la catégorie de produit ou le nom d'une zone sur laquelle un visiteur a cliqué.
   * Les mesures sont des événements spécifiques que vous souhaitez qu'un visiteur effectue : lorsqu'il effectue une action de votre choix, le nombre augmente d'une unité. Voici quelques exemples : envoi d'une commande, abonnement à un bulletin d'information ou envoi d'une réponse à une enquête.
1. **Faites correspondre les dimensions et les mesures dans une page ou une feuille de calcul.** Cette page ou ce tableau devient finalement votre document de conception de solution. Certaines colonnes ou puces utiles à inclure :
   * Etat de mise en œuvre : Planifié, Actif, Inactif, Problèmes, etc. Cela informe les lecteurs du document de l'état de la variable, s'il est implémenté ou s'il existe des problèmes avec la collecte de données.
   * Nom de variable : Par exemple, « Termes de recherche interne ». Il s'agira de ce que les analystes voient lorsqu'ils travaillent dans Analytics.
   * Variable Analytics associée à : Variable Analytics par défaut ou personnalisée dont vous choisissez d'affecter des valeurs. Les dimensions appartiennent généralement aux evars, tandis que les mesures tombent sous des événements.
   * Logique : Description de la définition de la variable et de ce qui détermine sa valeur. Par exemple, « Uniquement défini sur les pages de recherche interne ». Prend la valeur du paramètre de chaîne de requête q.  » »
   * Toute autre note que vous souhaitez inclure à la variable

## Ressources supplémentaires

La définition d'un document de conception de solution est un projet relativement complexe, en particulier pour les organisations qui n'en ont pas encore créé un. Si vous avez besoin d'aide supplémentaire, Adobe propose des consultants spécialisés pour aider votre organisation à utiliser Adobe Analytics. Contactez votre gestionnaire de compte si vous souhaitez inscrire les services professionnels d'Adobe. A [Technical pre-implementation questionnaire](assets/technical-pre-implementation-questionnaire.pdf) can be filled out so Adobe knows exactly how to help based on your organization's needs.

Il existe aussi plusieurs partenaires Adobe spécialisés dans la création d'un document de conception de solution et la mise en œuvre d'Adobe Analytics sur votre site.

> [!NOTE] Bien que les membres de la communauté Analytics trouvent les liens suivants utiles, ils ne sont pas détenus par Adobe. Tenez compte de cette remarque lorsque vous consultez leur contenu.

* [7 Étapes de configuration de votre conception de solution Analytics Web](https://resources.observepoint.com/blog/7-steps-solution-design-data-governance) par point d'observation
* [Une structure pour le processus d'analyse numérique](https://analyticsdemystified.com/analytics-strategy/framework-digital-analytics-process/) par Analytics Demystified
* [La référence de conception de la solution est en fait votre BFF](http://numericanalytics.com/why-a-simple-piece-of-documentation-is-the-key-to-analytics-success-the-solution-design-reference-is-actually-your-bff/) par Analyses numériques
* [Comment faire le balisage d'Adobe Analytics par](http://www.anttikoski.fi/how-to-make-adobe-analytics-tagging-map-aka-solution-design-requirements-for-sitecatalyst-implementation/) Antti Koski ?
* [Importance du document de conception de la solution](https://www.ebiquity.com/news-insights/analytics/the-importance-of-the-solution-design-document) par Ebiquity

## Étapes suivantes

Implémentez les variables dans votre document de conception de solution.

* Introduction aux evars : Découvrez ce qu'est une evar, comment elle fonctionne et comment l'utiliser dans votre implémentation
* Introduction aux événements : Découvrez ce qu'est un événement de réussite, comment son fonctionnement et comment l'utiliser dans votre implémentation
