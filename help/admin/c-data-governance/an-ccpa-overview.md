---
description: Ce document décrit ce que vous devez faire dans Adobe Analytics pour prendre en charge les droits d’accès CCPA et de suppression de vos personnes de données.
seo-description: Ce document décrit ce que vous devez faire dans Adobe Analytics pour prendre en charge les droits d’accès CCPA et de suppression de vos personnes de données.
seo-title: Adobe Analytics et CCPA
title: Adobe Analytics et CCPA
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: 3be4e96df12d5e53bf77b1960afc229a1ac6c046

---


# Adobe Analytics et CCPA

Ce document décrit ce que vous devez faire dans Adobe Analytics pour prendre en charge les droits d’accès CCPA et de suppression de vos personnes de données.

## Présentation d’Adobe

>[!IMPORTANT] Le contenu de ce document ne constitue pas un avis juridique et ne vise pas à remplacer un avis juridique. Veuillez consulter le service juridique de votre entreprise pour obtenir des conseils concernant l'ACCP.

Le 1er janvier 2020, la Loi sur la protection des renseignements personnels des consommateurs (LPCPC) de Californie entre en vigueur. For more information about Adobe's response and what this means for you as an Adobe customer, see [Adobe's Privacy Center.](https://www.adobe.com/privacy.html)

Lorsqu’Adobe fournit des logiciels et des services à une entreprise, elle agit en tant qu’entité de traitement des données pour toutes les données personnelles qu’elle reçoit et stocke pour le compte de nos clients, dans le cadre de la prestation de ces services. En tant que traitement de données, Adobe traite les données personnelles conformément aux autorisations et aux instructions de votre entreprise (telles que définies dans votre accord avec Adobe, par exemple).

En tant que contrôleur des données, vous déterminez les données personnelles qu’Adobe traite et stocke pour vous. Si vous utilisez les solutions Adobe Experience Cloud, Adobe peut héberger des données personnelles pour vous en fonction des solutions que vous utilisez et des informations que vous choisissez d’envoyer sur votre compte Adobe Experience Cloud. Pour obtenir une liste d’exemples, voir [Confidentialité Adobe Experience Cloud.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

## Gestion des données CCPA par Adobe

Adobe Cloud Platform (ACP) fournit une solution intégrée qui relie l’infrastructure de gouvernance des données de votre marque aux outils Adobe qu’elle utilise pour créer et gérer les expériences des consommateurs. Les fonctions de gouvernance des données d’Adobe Cloud Platform permettent d’établir un lien direct entre la politique de gouvernance des données et l’utilisation des données.

Familiarize yourself with [how Adobe Analytics handles GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) which discusses steps for privacy readiness and how to integrate with the Adobe Experience Cloud Privacy Service API.

## Préparation CCPA et données Adobe Analytics

Adobe a conscience que vous connaissez mieux les données personnalisées de vos suites de rapports et nous vous donnons la possibilité de définir vos paramètres et préférences en matière de gouvernance des données.
To that end, Adobe Analytics provides a Data Governance user interface that lets you, as the data controller, set [privacy labels](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) on your Analytics report suites and all the dimensions and metrics in those report suites. Vous pouvez identifier les colonnes de votre ensemble de données qui contiennent des données directement ou indirectement identifiables afin de pouvoir soumettre vos demandes d’accès et de suppression pour traiter ces données. Pour chaque demande, les étiquettes définies dans l’interface utilisateur de gouvernance des données d’Analytics seront attribuées à l’identifiant spécifique correspondant à cette requête.

Voir [Étiqueter les données d’une suite de rapports](/help//admin/c-data-governance/gdpr-setup-reportsuite.md) pour plus d’informations sur la façon de définir les étiquettes.

## Conditions préalables

* Familiarize yourself with [GDPR terminology.](/help/admin/c-data-governance/gdpr-terminology.md)
* Associez votre société de connexion à une organisation Experience Cloud, si ce n’est pas déjà fait. Contactez l’assistance clientèle d’Adobe et reportez-vous à la section [Organisations et liaison de comptes.](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)
* Mappez toute suite de rapports Adobe Analytics que vous souhaitez configurer pour la gouvernance des données dans [votre organisation Experience Cloud.](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)
* Définissez une stratégie de rétention des données pour chaque suite de rapports afin que les demandes de suppression et d’accès de l’ACCP puissent être exécutées.

   Adobe Analytics ne peut pas vous aider dans le traitement des requêtes de l’API des services de confidentialité, c’est-à-dire le traitement des demandes d’accès ou de suppression que vous recevez de vos utilisateurs finaux, si la période de rétention des données n’a pas été définie dans Adobe Analytics. Veuillez contacter votre gestionnaire du succès client pour définir votre période de conservation des données.

* Vérifiez vos autorisations : pour utiliser l’interface de gestion de la gouvernance des données dans Adobe Analytics, vous devez être un administrateur d’Adobe Analytics.
* Envisagez d’implémenter les variables [de gestion des](/help/admin/c-data-governance/consent-variables.md) consentements pour effectuer le suivi de l’état du consentement au niveau de l’accès.
