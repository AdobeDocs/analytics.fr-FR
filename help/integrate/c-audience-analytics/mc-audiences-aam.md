---
description: Adobe Audience Manager (Adobe Audience Manager) est une puissante plateforme de gestion des données qui vous permet de créer des profils d’audience uniques à partir d’intégrations de données propriétaires, secondaires/partenaires et tierces. Ces profils d’audience permettent aux annonceurs de définir les segments à plus forte valeur dans n’importe quel canal numérique.
solution: Analytics
title: Audience Analytics - Aperçu
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
TQID: 'https://experienceleague.adobe.com/WPB1fEJx1MaWpUNRCZ48ghAVyKyc5IwoGOdgQQ-tPhI'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
subfeature_v2:
  - id: a97e0d8c-238a-47ee-8d81-16bd45309bed
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 522
ht-degree: 41%

---

# Audience Analytics - Aperçu

Adobe Audience Manager (Adobe Audience Manager) est une puissante plateforme de gestion des données qui vous permet de créer des profils d’audience uniques à partir d’intégrations de données propriétaires, secondaires/partenaires et tierces. Ces profils d’audience permettent aux annonceurs de définir les segments à plus forte valeur dans n’importe quel canal numérique.

Une fois l’intégration d’Audience Analytics en place, vous pouvez intégrer à n’importe quel workflow Analytics des données d’audience Adobe Audience Manager telles que des informations démographiques (par exemple, le genre ou le niveau de revenu), des informations psychographiques (par exemple, les intérêts et les passe-temps), des données de gestion de la relation client et des données sur les impressions publicitaires.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Audience Analytics](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/audience-manager/audience-analytics-integrate-aam-segments-into-analytics){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Avantages clés {#benefits}

L’intégration d’Audience Analytics offre les avantages clés suivants :

* Il s’agit de la première intégration productisée entre une plateforme de gestion des données et un moteur d’analyse disponible sur le marché.
* Les segments sont partagés de Adobe Audience Manager vers Analytics en temps réel, afin d’informer la découverte, la segmentation et l’optimisation des audiences.
* Tous les segments Adobe Audience Manager sont partagés par défaut, ce qui enrichit entièrement les profils clients dans Analytics.
* Les administrateurs de solution peuvent activer l’intégration dans l’interface utilisateur en effectuant des modifications de code minimales.
* Seuls les segments conformes aux contrôles des exportations de données d’Audience Manager sont partagés.

## Fonctionnement d’Audience Analytics {#works}

![](assets/mc-aud-dataflow.png)

1. Chaque fois qu’un utilisateur se rend sur vos propriétés numériques, les accès sont collectés et envoyés à Analytics.
1. Grâce au [transfert côté serveur](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md), chaque accès enregistré par Analytics est automatiquement envoyé à Adobe Audience Manager en temps réel.
1. Grâce à l’intégration d’Audience Analytics, pour chaque accès, l’appartenance à l’audience d’un visiteur est recherchée dans Adobe Audience Manager et une liste d’identifiants de segment est renvoyée à Analytics pour traitement en temps réel.

Comme les segments Adobe Audience Manager sont insérés sur la base du même accès, vous pouvez être sûr que toutes les données disponibles dans Adobe Audience Manager sur un visiteur ne seront pas manquantes et mises à jour pour cet accès. Cette fonctionnalité est supérieure à un module d’extension AppMeasurement dans la mesure où un module externe rend ces segments disponibles uniquement lors de l’accès suivant (et non l’accès actuel).

En outre, nous classons automatiquement les identifiants de segment Adobe Audience Manager en fonction de leurs noms conviviaux, de sorte que vous n’ayez pas à consulter d’identifiants alphanumériques dans les rapports Analytics.

## Conditions préalables {#prerequisites}

Assurez-vous que les conditions préalables suivantes sont réunies :

* Vous êtes à la fois client d’Audience Manager et d’Adobe Analytics.
* Vous êtes un administrateur d’Audience Manager.
* Vous utilisez Identity Service version 1.5 ou ultérieure.
* Les suites de rapports Adobe Audience Manager et Adobe Analytics sont mappées à la même organisation CX Enterprise.
* Vous utilisez la [redirection côté serveur](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md) et avez mis en œuvre le [module de gestion de l’audience](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=fr) (pas de code DIL) - AppMeasurement 1.5 ou une version ultérieure.

Ces conditions préalables sont décrites dans le [Workflow Audience Analytics](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md).
