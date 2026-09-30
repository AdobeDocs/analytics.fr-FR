---
description: Découvrez comment mettre en œuvre le balisage multisuite afin dʼenvoyer une demande dʼimage à plusieurs suites de rapports.
title: Implémentation du balisage multisuite
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/djrzQEjvc--wnh2wR1HNV-LVEn6RPcyiaLKLha5pfSY'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
    internal-label: Mobile SDK
  - id: df312454-73c4-43f6-a90e-18f5043f074c
    internal-label: Tags
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 93%
---
# Implémentation du balisage multisuite

[Le balisage multisuite](/help/admin/tools/manage-rs/rollup-report-suite.md) permet dʼenvoyer des demandes dʼimage non seulement à une suite de rapports globale, mais également à des suites de rapports enfants individuelles, afin de pouvoir fournir des sous-ensembles de données de la suite de rapports globale de votre entreprise à différents utilisateurs finaux.

Pour mettre en œuvre le balisage multisuite, vous devez inclure lʼidentifiant de suite de rapports (RSID) de la suite de rapports globale, ainsi que les RSID des suites de rapports enfants applicables dans le code de suivi de vos pages web et applications.

* Pour les implémentations de balises Adobe Experience Platform, spécifiez chacune des suites de rapports de lʼ[[!DNL Analytics] extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=fr).

* Pour les implémentations JavaScript et SDK mobiles héritées, séparez les RSID par des virgules, sans espaces (`rsid1,rsid2,rsid3`, etc.).

* Pour les autres types de mise en œuvre, utilisez la syntaxe requise pour répertorier plusieurs RSID.

>[!TIP]
>
> La bonne pratique consiste à répertorier dʼabord la suite de rapports globale ou son identifiant de suite de rapports.

Le balisage multisuite entraîne plusieurs appels au serveur pour chaque demande dʼimage : un appel principal à la suite de rapports globale et un appel secondaire pour chaque suite de rapports enfant.

>[!NOTE]
>
> [Les suites de rapports virtuelles](/help/components/vrs/vrs-about.md), qui permettent également de fournir des sous-ensembles de données de la suite de rapports globale de votre entreprise à différents utilisateurs finaux, nʼentraînent pas dʼappels au serveur secondaire.

## Dois-je mettre en œuvre le balisage multisuite ou des suites de rapports virtuelles ?

Il est généralement recommandé d’utiliser des suites de rapports virtuelles plutôt que le balisage multisuite, mais ce sont vos besoins qui déterminent l’approche la mieux adaptée à votre organisation en matière de suites de rapports.

Pour savoir si les suites de rapports virtuelles constituent lʼoption la plus adaptée à vos besoins, consultez la section « [Considérations relatives aux suites de rapports virtuelles et au balisage multisuite](/help/components/vrs/vrs-considerations.md) ». Consultez également la section « [Suites de rapports virtuelles par rapport au balisage multisuite](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78) » pour une comparaison des fonctionnalités de balisage multisuite et de suite de rapports virtuelle.
