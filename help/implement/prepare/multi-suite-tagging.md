---
description: Découvrez comment mettre en oeuvre le balisage multisuite pour envoyer une demande d’image à plusieurs suites de rapports.
title: Implémentation du balisage multisuite
exl-id: null
source-git-commit: 81da9ff9b00a69c49c028fc7f006c161d8ff21d4
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---


# Implémentation du balisage multisuite

[Le ](/help/admin/c-manage-report-suites/rollup-report-suite.md) balisage multisuite vous permet d’envoyer des demandes d’image non seulement à une suite de rapports globale, mais également à des suites de rapports enfants individuelles, afin que vous puissiez fournir des sous-ensembles des données de suite de rapports globale de votre entreprise à différents utilisateurs finaux.

Pour implémenter le balisage multisuite, vous devez inclure l’identifiant de suite de rapports (RSID) pour la suite de rapports globale, ainsi que les RSID pour les suites de rapports enfants applicables dans le code de suivi de vos pages web et applications.

* Pour les implémentations Adobe Experience Platform Launch, spécifiez chacune des suites de rapports pour l’[[!DNL Analytics] extension](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html).

* Pour les implémentations JavaScript et SDK mobiles héritées, séparez les RSID par des virgules, sans espaces (`rsid1,rsid2,rsid3`, etc.).

* Pour les autres types d’implémentation, utilisez la syntaxe requise pour répertorier plusieurs RSID.

>[!TIP]
>
> La bonne pratique consiste à répertorier d’abord l’identifiant global de suite de rapports ou de suite de rapports.

Le balisage multisuite génère plusieurs appels serveur pour chaque demande d’image : un appel Principal à la suite de rapports globale et un appel secondaire pour chaque suite de rapports enfant.

>[!NOTE]
>
> [Les suites de rapports virtuelles](/help/components/vrs/vrs-about.md), qui vous permettent également de fournir des sous-ensembles des données de suite de rapports globale de votre entreprise à différents utilisateurs finaux, n’impliquent pas d’appels au serveur secondaire.

## Dois-je implémenter le balisage multisuite ou les suites de rapports virtuelles ?

L’utilisation de suites de rapports virtuelles au lieu du balisage multi-suite est souvent une bonne pratique, mais les besoins de votre entreprise déterminent la meilleure approche de suite de rapports pour votre entreprise.

Pour savoir si les suites de rapports virtuelles constituent votre meilleure approche, voir &quot;[Suites de rapports virtuelles et considérations sur le balisage multisuite](/help/components/vrs/vrs-considerations.md)&quot;. Voir aussi &quot;[Suites de rapports virtuelles par rapport au balisage multisuite](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot; pour une comparaison du balisage multisuite et de la fonctionnalité des suites de rapports virtuelles.
