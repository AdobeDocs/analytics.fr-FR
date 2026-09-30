---
title: Analyses entre appareils
description: Découvrez comment remplacer vos données axées sur l’appareil par des données axées sur la personne en assemblant les données de l’appareil.
exl-id: e1c0d1e5-399d-45c2-864c-50ef93a77449
feature: CDA
role: Admin
TQID: 'https://experienceleague.adobe.com/SEHyUllyHtYjtfpaw9uI64WNytw3MMrR1Np9BN2Ckyk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
    internal-label: Report suites
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: f99536a1-75c7-4151-a2c8-073630632526
    internal-label: CDA
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 55%
---
# Analyses entre appareils

{{available-existing-customers}}

>[!WARNING]
>
>Le graphique d’appareil dans les analyses entre appareils est [obsolète](https://experienceleague.adobe.com/en/docs/discontinued/using/device-graph) et ne sera plus disponible à compter du **31 décembre 2025**. Veuillez basculer n’importe quelle suite de rapports virtuelle actuellement activée pour les graphiques d’appareils vers la méthode [ basée sur les champs](/help/components/cda/field-based-stitching.md).
>


Analytics sur l’ensemble des appareils (CDA) est une fonctionnalité qui transforme Analytics, en passant d’une vue centrée sur l’appareil à une vue centrée sur la personne. Dès lors, les analystes peuvent comprendre le comportement des utilisateurs qui s’étend sur plusieurs navigateurs, appareils ou applications. Adobe prend en charge le [groupement basé sur les champs](field-based-stitching.md) qui utilise uniquement une correspondance déterministe pour lier les appareils.
Le groupement basé sur les champs vous permet de choisir une variable Analytics comme base pour le groupement entre appareils dans une suite de rapports virtuelle.


Les analyses entre appareils vous permettent de répondre à des questions telles que :

* Combien de personnes interagissent avec ma marque ? Combien de types d’appareils utilisent-elles ? Comment se superposent-elles ?
* À quelle fréquence les utilisateurs commencent-ils une tâche sur un appareil mobile, puis passent-ils ensuite à un PC de bureau pour terminer la tâche ? Les clics publicitaires de campagne qui aboutissent sur un appareil conduisent-ils à une conversion ailleurs ?
* Comment ma compréhension de l’efficacité de la campagne change-t-elle si je prends en compte les parcours entre plusieurs appareils ? Comment mon analyse d’entonnoir change-t-elle ?
* Quels sont les chemins les plus courants empruntés par les utilisateurs d’un appareil à l’autre ? Où abandonnent-ils ? Où réussissent-ils ?
* En quoi le comportement des utilisateurs ayant plusieurs appareils diffère-t-il de celui des utilisateurs disposant d’un seul appareil ?

Lorsque des appareils sont liés, la persistance des variables est conservée d’un appareil à l’autre. Par exemple, un utilisateur consulte votre site pour la première fois par le biais d’une publicité reçue sur son ordinateur de bureau. Cet utilisateur trouve votre application mobile, l’installe et effectue un achat sur son appareil mobile. Avec Analytics sur plusieurs appareils, vous pouvez attribuer le chiffre d’affaires généré sur l’appareil mobile à l’annonce sur laquelle l’utilisateur ou l’utilisatrice a cliqué sur son ordinateur de bureau.



Consultez la [page Spark d’analyses entre appareils](https://express.adobe.com/page/8ZpjsX6Lp5XTM/) pour en savoir plus sur les fonctionnalités d’Analytics sur l’ensemble des appareils.

## Conditions préalables

L’utilisation d’Analytics sur l’ensemble des appareils nécessite [ groupement basé sur les champs ](field-based-stitching.md).

* Un contrat doit être signé avec Adobe et inclure Adobe Analytics Ultimate.
* Votre organisation choisit les suites de rapports pour lesquelles activer Analytics sur plusieurs appareils. Adobe recommande les suites de rapports qui contiennent des données multi-appareils, c’est-à-dire des données provenant de plusieurs types d’appareils/navigateurs/applications. Certaines organisations font référence à ce concept en tant que suite de rapports « globale », bien qu’il ne soit pas obligatoire que les analyses entre appareils soient globales d’un point de vue géographique.

## Limites

Analytics sur plusieurs appareils est une fonctionnalité innovante et robuste, mais elle présente des limites quant à la façon dont elle peut être utilisée. Le [groupement basé sur les champs](field-based-stitching.md) a également ses propres limites spécifiques.

* Les analyses entre appareils ne sont disponibles que via Analysis Workspace.
* Analytics sur plusieurs appareils ne fonctionne pas entre les suites de rapports et ne combine pas non plus les données de plusieurs suites de rapports.
* Les suites de rapports Adobe Analytics ne peuvent pas être associées à plus d’une ID d’organisation. Comme Analytics sur l’ensemble des appareils regroupe des appareils dans une suite de rapports donnée, il n’est pas possible d’utiliser Analytics sur l’ensemble des appareils pour regrouper des données sur plusieurs ID d’organisation.
* Les analyses entre appareils utilisent un pipeline de traitement complexe, avec plusieurs composants dépendants. Ce pipeline s’exécute en parallèle du workflow de création de rapports Analytics de base. Vous pouvez vous attendre à une incohérence des données d’environ 1 % pour le nombre total d’accès entre la suite de rapports d’origine et la suite de rapports virtuelle Analytics sur l’ensemble des appareils.
* Analytics sur plusieurs appareils utilise une suite de rapports virtuelle et un traitement des données au moment de l’exécution du rapport, qui ont leurs propres limites. Par exemple, ils ne prennent actuellement pas en charge les variables de canaux marketing. Voir [Suites de rapports virtuelles](/help/components/vrs/vrs-about.md) et [Traitement de la période de rapport](/help/components/vrs/vrs-report-time-processing.md) pour en savoir plus sur ces limitations.
* Private Graph utilise les mêmes synchronisations d’identifiants que celles utilisées par la fonctionnalité [Attributs du client](https://experienceleague.adobe.com/fr/docs/core-services/interface/services/customer-attributes/attributes) dans CX Enterprise et Adobe Analytics. Cependant, les suites de rapports virtuelles Analytics sur l’ensemble des appareils (qu’elles soient basées sur un graphique privé ou sur un groupement basé sur les champs) ne sont pas compatibles avec le reste de la fonctionnalité Attributs du client. En d’autres termes, les dimensions basées sur les attributs du client ne sont pas disponibles pour être utilisées avec les suites de rapports virtuelles Analytics sur l’ensemble des appareils.
* Les analyses entre appareils ne sont actuellement pas compatibles avec A4T.
* L’API 1.4 n’est pas prise en charge. Les connecteurs Power BI et Report Builder reposent tous les deux sur l’API 1.4 et ne sont donc pas compatibles avec Analytics sur plusieurs appareils.
* La surveillance active par Adobe du processus d’assemblage des analyses entre appareils se limite uniquement aux suites de rapports de production.
* Les analyses entre appareils ne sont actuellement pas compatibles avec l’API [Data Repair](https://developer.adobe.com/analytics-apis/docs/2.0/?lang=fr) Adobe Analytics
* Les données historiques de la suite de rapports virtuelle changent en fonction de la façon dont Adobe reconnaît les appareils et les rapproche. Les données de la suite de rapports source ne changent pas.
* Les données regroupées affichent une latence comprise entre 8 et 12 heures.
* Les données d’historique de mappage pour un appareil donné sont stockées pendant un an au maximum.
* Si un appareil atteint un nombre très élevé d’entrées d’historique de mappage au cours d’une année, l’historique de mappage est tronqué. La limite exacte dépend de l’option de rapprochement des appareils utilisée.
