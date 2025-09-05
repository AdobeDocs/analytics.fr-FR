---
description: Découvrez comment mettre en œuvre le balisage multisuite afin dʼenvoyer une demande dʼimage à plusieurs suites de rapports.
title: Implémentation du balisage multisuite
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
role: Admin, Developer, Leader
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 93%

---

# Implémentation du balisage multisuite

[Le balisage multisuite](/help/admin/tools/manage-rs/rollup-report-suite.md) permet dʼenvoyer des demandes dʼimage non seulement à une suite de rapports globale, mais également à des suites de rapports enfants individuelles, afin de pouvoir fournir des sous-ensembles de données de la suite de rapports globale de votre entreprise à différents utilisateurs finaux.

Pour implémenter le balisage multisuite, vous devez inclure lʼidentifiant de suite de rapports (RSID) pour la suite de rapports globale, ainsi que les RSID pour les suites de rapports enfants applicables dans le code de suivi de vos pages web et applications.

* Pour les implémentations de balises Adobe Experience Platform, spécifiez chacune des suites de rapports de lʼ[[!DNL Analytics] extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=fr).

* Pour les implémentations JavaScript et SDK mobiles héritées, séparez les RSID par des virgules, sans espaces (`rsid1,rsid2,rsid3`, etc.).

* Pour les autres types dʼimplémentation, utilisez la syntaxe requise pour répertorier plusieurs RSID.

>[!TIP]
>
> Il est recommandé de répertorier dʼabord lʼidentifiant de suite de rapports globale ou lʼidentifiant de suite de rapports.

Le balisage multisuite entraîne plusieurs appels au serveur pour chaque demande dʼimage : un appel principal à la suite de rapports globale et un appel secondaire pour chaque suite de rapports enfant.

>[!NOTE]
>
> [Les suites de rapports virtuelles](/help/components/vrs/vrs-about.md), qui permettent également de fournir des sous-ensembles de données de la suite de rapports globale de votre entreprise à différents utilisateurs finaux, nʼentraînent pas dʼappels au serveur secondaire.

## Dois-je implémenter le balisage multisuite ou les suites de rapports virtuelles ?

Il est recommandé dʼutiliser les suites de rapports virtuelles au lieu du balisage multisuite, mais ce sont les besoins de votre entreprise qui détermineront la suite de rapports à adopter.

Pour savoir si les suites de rapports virtuelles constituent lʼoption la plus adaptée à vos besoins, consultez la section « [Considérations relatives aux suites de rapports virtuelles et au balisage multisuite](/help/components/vrs/vrs-considerations.md) ». Consultez également la section « [Suites de rapports virtuelles par rapport au balisage multisuite](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78) » pour une comparaison des fonctionnalités de balisage multisuite et de suite de rapports virtuelle.
