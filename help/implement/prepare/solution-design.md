---
title: Création d’un document de conception de solution
description: Découvrez ce qu’est un document de conception de solution et comment l’utiliser dans votre entreprise.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Création d’un document de conception de solution

Un document de conception de solution (également connu sous le nom de document de référence de conception de solution ou de document d’exigences opérationnelles) est essentiellement le plan directeur de votre mise en œuvre d’Analytics. Il définit les critères identifiés par les parties prenantes à l’échelle de votre organisation et les traduit en variables dans Adobe Analytics. Sans lui, les organisations ont du mal à coordonner les besoins en matière de rapports et ont tendance à ne pas collecter certaines données importantes.

## Conditions préalables

[Validez votre mise en œuvre Analytics et publiez-la en production](../implement-with-launch/validate-publish-prod.md) - Bien qu’elle ne soit pas directement requise, Adobe conseille de mettre en place une mise en œuvre de base afin de collecter des données importantes, tout en définissant et en implémentant d’autres besoins opérationnels.

## Propriété et emplacement du document de conception

* **Déterminez qui, au sein de votre organisation, sera responsable de la gestion du document de conception de solution.** Ce rôle peut être confié à une personne ou à une équipe. Assurez-vous que la gestion de la conception de solution est préservée, même après des changements de fonction ou des restructurations de l’organisation. Il s’agit d’un document évolutif qui doit être correctement géré.
* **Déterminez où résidera votre document de solution.** Il n’existe pas de meilleur emplacement indiqué pour les documents de conception de solution, mais on les place généralement en un lieu interne facilement accessible. Par exemple, une feuille de calcul partagée ou un espace de travail collaboratif comme SharePoint ou un wiki interne. Il n’est pas nécessaire qu’il soit modifiable par tout le monde, mais il est préférable que les personnes qui peuvent accéder à la création de rapports soient au moins autorisées à le consulter.

## Définition des besoins opérationnels

Lors de la détermination des données à collecter, il est facile de dire « tout ». Cependant, cela peut rapidement devenir difficile à gérer, et même être moins bénéfique que de collecter des quantités de données plus raisonnables.

1. **Déterminez vos indicateurs de performances clés.** Que voulez-vous que les visiteurs fassent en fin de compte ? La réponse à cette question varie en fonction du secteur d’activité vertical et peut comporter divers éléments. À titre d’exemple, citons les achats, les enregistrements ou les clics publicitaires.
1. **Déterminez les données les plus importantes à collecter.** Posez des questions auxquelles vous souhaitez des réponses spécifiques. Les réponses à ces questions vous donneraient des informations sur la manière d’améliorer vos indicateurs de performances clés.
1. **Considérez ces questions et déterminez vos besoins en matière de suivi.** Regroupez-les en dimensions et en mesures.
   * Les dimensions sont des variables qui contiennent du texte. À titre d’exemple, citons un terme pour la recherche interne, une catégorie de produit ou le nom d’une section sur laquelle a cliqué un visiteur.
   * Les mesures sont des événements spécifiques que vous souhaitez voir réalisés par un visiteur. Par exemple, lorsqu’il effectue l’action que vous souhaitez, le nombre augmente de un. À titre d’exemple, citons l’envoi d’une commande, l’inscription à un bulletin d’information ou l’envoi d’une réponse à une enquête.
1. **Mappez les dimensions et les mesures dans une page ou une feuille de calcul.** Cette page ou ce tableau deviendra à terme votre document de conception de solution. Certaines colonnes ou puces utiles à inclure :
   * Statut de la mise en œuvre : planifiée, active, inactive, problèmes, etc. Cela permet d’informer les utilisateurs du document du statut de la variable, si elle a été implémentée ou s’il existe des problèmes liés à la collecte de données.
   * Nom de la variable : par exemple, « Termes pour la recherche interne ». Cette valeur correspond à ce que voient les analystes lorsqu’ils travaillent dans Analytics.
   * Variable Analytics associée à : à quelle variable Analytics par défaut ou personnalisée vous choisissez d’affecter des valeurs. Les dimensions dépendent généralement des eVars, tandis que les mesures dépendant des événements.
   * Logique : description de la définition de la variable et de ce qui détermine sa valeur. Par exemple, « Définir uniquement sur des pages de recherche interne. Prend la valeur du paramètre de chaîne de requête q. »
   * Toute autre remarque que vous souhaitez inclure au sujet de la variable.

## Ressources supplémentaires

La définition d’un document de conception de solution est un projet assez complexe, surtout pour les organisations qui n’en avaient pas encore créé. Si vous avez besoin d’une assistance supplémentaire, Adobe fournit des services de conseil spécialisés pour aider votre organisation à exécuter Adobe Analytics. Contactez votre gestionnaire de compte si vous souhaitez bénéficier des services professionnels d’Adobe. Vous pouvez remplir un [questionnaire technique préalable à l’implémentation](assets/technical-pre-implementation-questionnaire.pdf) afin qu’Adobe sache exactement comment vous aider en fonction des besoins de votre organisation.

Plusieurs partenaires Adobe se spécialisent également dans la création d’un document de conception de solution, ainsi que dans la mise en œuvre d’Adobe Analytics sur votre site.

> [!NOTE] Bien que les membres de la communauté Analytics aient trouvé les liens suivants utiles, ils ne sont pas la propriété d’Adobe. Tenez compte de cette remarque lorsque vous affichez leur contenu.

* [7 étapes pour configurer la conception](https://resources.observepoint.com/blog/7-steps-solution-design-data-governance) de votre solution Web Analytics par ObservePoint
* [Démystification d’une structure pour le processus](https://analyticsdemystified.com/analytics-strategy/framework-digital-analytics-process/) Digital Analytics par Analytics
* [La référence de conception de la solution est en fait votre fichier BFF](http://numericanalytics.com/why-a-simple-piece-of-documentation-is-the-key-to-analytics-success-the-solution-design-reference-is-actually-your-bff/) par Analyses numériques
* [Comment créer une carte](http://www.anttikoski.fi/how-to-make-adobe-analytics-tagging-map-aka-solution-design-requirements-for-sitecatalyst-implementation/) de balisage Adobe Analytics par Antti Koski
* [L'importance du document](https://www.ebiquity.com/news-insights/analytics/the-importance-of-the-solution-design-document) de conception de la solution par l'équité

## Étapes suivantes

Mettez en œuvre les variables dans votre document de conception de solution.

* Présentation des eVars : découvrez ce qu’est une eVar, son fonctionnement et comment l’utiliser dans votre implémentation
* Présentation des événements : découvrez ce qu’est un événement de succès, son fonctionnement et comment en utiliser un dans votre implémentation
