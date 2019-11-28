---
description: Ce document décrit la marche à suivre dans Adobe Analytics pour prendre en charge les droits d’accès et de suppression en vertu du CCPA pour vos sujets des données.
title: Adobe Analytics et le CCPA
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: ht
source-git-commit: 12a7452337307ca019c005dc20e3b551d96e1289

---


# Adobe Analytics et le CCPA

Ce document décrit la marche à suivre dans Adobe Analytics pour prendre en charge les droits d’accès et de suppression en vertu du CCPA pour vos sujets des données.

## Présentation d’Adobe

>[!IMPORTANT] Le contenu de ce document ne constitue pas un avis juridique et ne vise pas à remplacer un avis juridique. Veuillez consulter le service juridique de votre entreprise pour obtenir des conseils concernant le CCPA.

Le 1er janvier 2020, le California Consumer Privacy Act (CCPA), loi sur la confidentialité des données, entrera en vigueur. Pour plus d’informations sur la réponse d’Adobe et sur ce que cela signifie pour vous en tant que client Adobe, consultez [Adobe Privacy Center.](https://www.adobe.com/fr/privacy.html)

Lorsqu’Adobe fournit des logiciels et des services à une entreprise, elle agit en tant qu’entité de traitement des données pour toutes les données personnelles qu’elle reçoit et stocke pour le compte de nos clients, dans le cadre de la prestation de ces services. En tant qu’entité de traitement des données, Adobe traite les données personnelles conformément aux autorisations et aux instructions de votre société (par exemple, tel qu’énoncé dans votre accord avec Adobe).

En tant que contrôleur des données, vous déterminez les données personnelles qu’Adobe traite et stocke pour vous. Si vous utilisez les solutions Adobe Experience Cloud, Adobe peut héberger des données personnelles pour vous en fonction des solutions que vous utilisez et des informations que vous choisissez d’envoyer sur votre compte Adobe Experience Cloud. Pour obtenir une liste d’exemples, voir [Confidentialité Adobe Experience Cloud.](https://www.adobe.com/fr/privacy/experience-cloud.html#collect)

## Comment Adobe gère les données relatives au CCPA

Adobe Cloud Platform (ACP) fournit une solution intégrée qui relie l’infrastructure de gouvernance des données de votre marque aux outils Adobe qu’elle utilise pour créer et gérer les expériences des consommateurs. Les fonctions de gouvernance des données d’Adobe Cloud Platform permettent d’établir un lien direct entre la politique de gouvernance des données et l’utilisation des données.

Familiarisez-vous avec la section [Comment Adobe Analytics gère les données relatives au RGPD](https://www.adobe.com/fr/data-analytics-cloud/analytics/general-data-protection-regulation.html) qui explique les étapes nécessaires pour se préparer à la confidentialité et comment intégrer l’API relative aux services de confidentialité d’Adobe Experience Cloud.

## Préparation au CCPA et vos données Adobe Analytics

Adobe a conscience que vous connaissez mieux les données personnalisées de vos suites de rapports et nous vous donnons la possibilité de définir vos paramètres et préférences en matière de gouvernance des données.
Pour ce faire, Adobe Analytics fournit une interface utilisateur de gouvernance des données qui vous permet, en tant que contrôleur des données, de définir des [étiquettes de confidentialité](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) sur vos suites de rapports Analytics et toutes les dimensions et mesures de ces suites de rapports. Vous pouvez identifier les colonnes de votre ensemble de données qui contiennent des données directement ou indirectement identifiables afin de pouvoir soumettre vos demandes d’accès et de suppression pour traiter ces données. Pour chaque demande, les étiquettes définies dans l’interface utilisateur de gouvernance des données d’Analytics seront attribuées à l’identifiant spécifique correspondant à cette requête.

Voir [Étiqueter les données d’une suite de rapports](/help//admin/c-data-governance/gdpr-setup-reportsuite.md) pour plus d’informations sur la façon de définir les étiquettes.

## Conditions préalables

* Familiarisez-vous avec la [terminologie relative au règlement général sur la protection des données (RGPD).](/help/admin/c-data-governance/gdpr-terminology.md)
* Associez votre société de connexion à une organisation Experience Cloud, si ce n’est pas déjà fait. Contactez l’assistance clientèle d’Adobe et reportez-vous à la section [Organisations et liaison de comptes.](https://marketing.adobe.com/resources/help/fr_FR/mcloud/organizations.html)
* Mappez toute suite de rapports Adobe Analytics que vous souhaitez configurer pour la gouvernance des données dans [votre organisation Experience Cloud.](https://marketing.adobe.com/resources/help/fr_FR/mcloud/report-suite-mapping.html)
* Définissez une politique de conservation des données pour chaque suite de rapports afin que les demandes d’accès et de suppression en vertu du CCPA puissent être honorées.

   Adobe Analytics ne peut pas vous aider à traiter les demandes de l’API relative aux Services de confidentialité, c’est-à-dire traiter les demandes d’accès ou de suppression que vous recevez de vos utilisateurs finaux, si la période de conservation des données n’a pas été définie dans Adobe Analytics. Veuillez contacter votre gestionnaire du succès client pour définir votre période de conservation des données.

* Vérifiez vos autorisations : pour utiliser l’interface de gestion de la gouvernance des données dans Adobe Analytics, vous devez être un administrateur d’Adobe Analytics.
* Envisagez de mettre en œuvre les [Variables de gestion du consentement](/help/admin/c-data-governance/consent-variables.md) pour effectuer le suivi de l’état du consentement au niveau de l’accès.
