---
description: Ce document décrit la marche à suivre dans Adobe Analytics pour prendre en charge les droits d’accès et de suppression en vertu du règlement général sur la protection des données (RGPD) pour vos sujets des données.
title: Adobe Analytics et le Règlement général sur la protection des données (RGPD)
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 100%

---


# Adobe Analytics et le Règlement général sur la protection des données (RGPD)

Ce document décrit la marche à suivre dans Adobe Analytics pour prendre en charge les droits d’accès et de suppression en vertu du règlement général sur la protection des données (RGPD) pour vos sujets des données.

## Présentation d’Adobe {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT]
>
>Le contenu de ce document ne constitue pas un avis juridique et ne vise pas à remplacer un avis juridique. Veuillez consulter le service juridique de votre entreprise pour obtenir des conseils concernant le règlement général sur la protection des données (RGPD).

Le 25 mai 2018, le Règlement général sur la protection des données (RGPD) de l’Union européenne est entré en vigueur. Pour plus d’informations sur la réponse d’Adobe et sur ce que cela signifie pour vous en tant que client Adobe, voir [Le RGPD et votre entreprise.](https://www.adobe.com/fr/privacy/general-data-protection-regulation.html)

Lorsqu’Adobe fournit des logiciels et des services à une entreprise, elle agit en tant qu’entité de traitement des données pour toutes les données personnelles qu’elle reçoit et stocke pour le compte de nos clients, dans le cadre de la prestation de ces services. En tant qu’entité de traitement des données, Adobe traite les données personnelles conformément aux autorisations et aux instructions de votre société (par exemple, tel qu’énoncé dans votre accord avec Adobe).

En tant que contrôleur des données, vous déterminez les données personnelles qu’Adobe traite et stocke pour vous. Si vous utilisez les solutions Adobe Experience Cloud, Adobe peut héberger des données personnelles pour vous en fonction des solutions que vous utilisez et des informations que vous choisissez d’envoyer sur votre compte Adobe Experience Cloud. Pour obtenir une liste d’exemples, voir [Confidentialité Adobe Experience Cloud.](https://www.adobe.com/fr/privacy/experience-cloud.html#collect)

![](assets/privacy_ready.png)

## Comment Adobe gère les données relatives au RGPD {#section_A20BCC08A80B410D97601BFB1CAF83F1}

Adobe Cloud Platform (ACP) fournit une solution intégrée qui relie l’infrastructure de gouvernance des données de votre marque aux outils Adobe qu’elle utilise pour créer et gérer les expériences des consommateurs. Les fonctions de gouvernance des données d’Adobe Cloud Platform permettent d’établir un lien direct entre la politique de gouvernance des données et l’utilisation des données.

Familiarisez-vous avec la section [Comment Adobe Analytics gère les données relatives au RGPD](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) qui explique les étapes nécessaires pour se préparer au RGPD et comment intégrer l’API relative au RGPD d’Adobe Experience Cloud.

## Préparation au RGPD et vos données Adobe Analytics {#section_9A47CDCD614C42238F6E05CFF0180195}

Adobe a conscience que vous connaissez mieux les données personnalisées de vos suites de rapports et nous vous donnons la possibilité de définir vos paramètres et préférences en matière de gouvernance des données.

Pour ce faire, Adobe Analytics fournit une interface utilisateur de gouvernance des données qui vous permet, en tant que contrôleur des données, de définir des [étiquettes de confidentialité](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) sur vos suites de rapports Analytics et toutes les dimensions et mesures de ces suites de rapports. Vous pouvez identifier les colonnes de votre ensemble de données qui contiennent des données directement ou indirectement identifiables afin de pouvoir soumettre vos demandes d’accès et de suppression pour traiter ces données. Pour chaque demande, les étiquettes définies dans l’interface utilisateur de gouvernance des données d’Analytics seront attribuées à l’identifiant spécifique correspondant à cette requête.

Voir [Étiqueter les données d’une suite de rapports](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) pour plus d’informations sur la façon de définir les étiquettes.

## Conditions préalables {#section_3C766371CE0641C0821FE8E750E5AE0C}

* Familiarisez-vous avec la [terminologie relative au règlement général sur la protection des données (RGPD).](/help/admin/c-data-governance/gdpr-terminology.md)
* Associez votre société de connexion à une organisation Experience Cloud, si ce n’est pas déjà fait. Contactez l’assistance clientèle d’Adobe et reportez-vous à la section [Organisations et liaison de comptes.](https://docs.adobe.com/content/help/fr-FR/core-services/interface/manage-users-and-products/organizations.html)
* Mappez toute suite de rapports Adobe Analytics que vous souhaitez configurer pour la gouvernance des données dans [votre organisation Experience Cloud.](https://docs.adobe.com/content/help/fr-FR/core-services/interface/about-core-services/report-suite-mapping.html)
* Définissez une politique de conservation des données pour chaque suite de rapports afin que les demandes d’accès et de suppression en vertu du RGPD puissent être honorées.

   >[!NOTE]
   >
   >Adobe Analytics ne peut pas vous aider à traiter les demandes de l’API relative au règlement général sur la protection des données (RGPD), c’est-à-dire traiter les demandes d’accès ou de suppression que vous recevez de vos utilisateurs finaux, si la période de conservation des données n’a pas été définie dans Adobe Analytics. Veuillez contacter votre gestionnaire du succès client pour définir votre période de conservation des données.

* Vérifiez vos autorisations : pour utiliser l’interface de gestion de la gouvernance des données dans Adobe Analytics, vous devez être un administrateur d’Adobe Analytics.
