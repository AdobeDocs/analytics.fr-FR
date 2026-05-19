---
description: Ce document décrit la marche à suivre dans Adobe Analytics pour prendre en charge les droits d’accès et de suppression en vertu du CCPA pour vos titulaires de données.
title: Adobe Analytics et le CCPA
feature: Data Governance
role: Admin
exl-id: 1f37e72b-99e4-4833-a506-98c8ec415757
TQID: https://experienceleague.adobe.com/medgbA9EBG0fE2xttZ7HLKT42-RBr7rlMGGGGrAyoKw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 75%

---

# Adobe Analytics et le CCPA

Ce document décrit la marche à suivre dans Adobe Analytics pour prendre en charge les droits d’accès et de suppression en vertu du CCPA pour vos titulaires de données.

## Présentation d’Adobe

>[!IMPORTANT]
>
>Le contenu de ce document ne constitue pas un avis juridique et ne vise pas à en remplacer un. Veuillez consulter le service juridique de votre entreprise pour obtenir des conseils concernant le CCPA.

Le 1er janvier 2020, le California Consumer Privacy Act (CCPA), loi sur la confidentialité des données, entrera en vigueur. Pour plus d’informations sur la réponse d’Adobe et sur ce que cela signifie pour vous en tant que client Adobe, consultez [Adobe Privacy Center.](https://www.adobe.com/fr/privacy.html)

Lorsqu’Adobe fournit des logiciels et des services à une entreprise, elle agit en tant que responsable du traitement des données pour toutes les données personnelles qu’elle reçoit et stocke pour le compte de ses clients, dans le cadre de la prestation de ces services. En tant qu’entité de traitement des données, Adobe traite les données personnelles conformément aux autorisations et aux instructions de votre société (par exemple, tel qu’énoncé dans votre accord avec Adobe).

En tant que contrôleuse ou contrôleur de données, vous déterminez les données personnelles qu’Adobe traite et stocke pour vous. Si vous utilisez les solutions Adobe CX Enterprise, Adobe peut héberger des données personnelles pour vous en fonction des solutions que vous utilisez et des informations que vous choisissez d’envoyer à votre compte Adobe CX Enterprise. Pour obtenir une liste d’exemples, voir [Confidentialité d’Adobe CX Enterprise.](https://www.adobe.com/fr/privacy/experience-cloud.html#collect)

## Comment Adobe gère les données relatives au CCPA

Adobe CX Enterprise fournit une solution intégrée qui connecte l’infrastructure de gouvernance des données de votre marque aux outils Adobe qu’elle utilise pour créer et gérer les expériences client. Les fonctionnalités de gouvernance des données d’Adobe CX Enterprise permettent de lier directement la politique de gouvernance des données à l’utilisation des données.

Familiarisez-vous avec [la façon dont Adobe Analytics gère le RGPD](https://www.adobe.com/fr/data-analytics-cloud/analytics/general-data-protection-regulation.html) qui explique les étapes de préparation à la confidentialité et comment intégrer l’API Adobe CX Enterprise Privacy Service.

## Préparation au CCPA et vos données Adobe Analytics

Adobe a conscience que vous connaissez mieux les données personnalisées de vos suites de rapports et nous vous donnons la possibilité de définir vos paramètres et préférences en matière de gouvernance des données.
Pour ce faire, Adobe Analytics fournit une interface utilisateur de gouvernance des données qui vous permet, en tant que contrôleur des données, de définir des [étiquettes de confidentialité](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels) sur vos suites de rapports Analytics et toutes les dimensions et mesures de ces suites de rapports. Vous pouvez identifier les colonnes de votre ensemble de données qui contiennent des données directement ou indirectement identifiables afin de pouvoir soumettre vos demandes d’accès et de suppression pour traiter ces données. Pour chaque demande, les étiquettes définies dans l’interface utilisateur de gouvernance des données d’Analytics seront attribuées à l’identifiant spécifique correspondant à cette requête.

Consultez [Étiqueter les données d’une suite de rapports](/help/admin/tools/privacy-labeling/labeling-overview.md) pour plus d’informations sur la façon de définir les étiquettes.
