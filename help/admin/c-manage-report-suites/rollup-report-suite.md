---
description: Descriptions des types de Report Suites et comparaison des Report Suites globales et des Report Suites de cumul.
title: Approches des suites de rapports
feature: Outils d’administration
uuid: c90b8e38-2c95-4318-8165-a362106b6142
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 27%

---

# Approches des suites de rapports

<!-- change filename since page name changed? -->

Vous pouvez configurer vos suites de rapports en tant que *suites de rapports globales* ou *suites de rapports de cumul*.

## Suites de rapports globales

Une suite de rapports globale collecte les données de tous les domaines et applications dont votre entreprise est propriétaire. Elle nécessite une implémentation pour envoyer toutes les demandes d’image à une seule suite de rapports.

Dans la plupart des cas, Adobe recommande de mettre en œuvre une suite de rapports globale. Voir &quot;[Considérations relatives aux suites de rapports globales](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html)&quot; pour connaître les avantages de la mise en oeuvre d’une suite de rapports globale.

Vous pouvez fournir des sous-ensembles de données de suite de rapports globale de votre société à différents utilisateurs finaux à l’aide des approches *balisage multi-suite* et *suite de rapports virtuelle* :

* **Balisage** multi-suite : Le balisage multi-suite vous permet d’envoyer des demandes d’image non seulement à une suite de rapports globale, mais également à des suites de rapports enfants individuelles. Les données de rapport globales sont dédupliquées dans toutes les suites de rapports.

   Par exemple, vous pouvez collecter toutes les données dans une suite de rapports globale et configurer des suites de rapports secondaires en fonction de la marque, de la région ou d’un autre facteur de différenciation. Les différentes équipes de votre société peuvent alors se concentrer sur les données des suites de rapports qui les concernent.

   Pour utiliser le balisage multi-suite, implémentez des suites de rapports enfants et une suite de rapports globale qui inclut toutes les données des enfants. Le code de suivi de vos pages Web et de vos applications comprend l&#39;identifiant de suite de rapports (RSID) pour la suite de rapports globale et également les RSID pour les suites de rapports enfants applicables.<!-- Wording/be more specific? And include any links? -->

   Un appel serveur distinct est effectué à chaque suite de rapports dans la demande d’image. Les appels aux suites de rapports enfants sont des appels secondaires.

* **Suite** de rapports virtuelle : Une suite de rapports  [virtuelle ](/help/components/vrs/vrs-about.md) est une requête sur des segments spécifiés collectés dans une suite de rapports globale et disponible pour des groupes d’utilisateurs spécifiés. Les suites de rapports virtuelles vous permettent de traiter des éléments de rapport pour différents utilisateurs finaux sans utiliser de balisage multi-suite, évitant ainsi les appels au serveur secondaire.

   Pour utiliser des suites de rapports virtuelles, implémentez une suite de rapports globale, puis analysez les données afin de créer des suites de rapports virtuelles avec des segments spécifiques appliqués et avec des autorisations de groupe spécifiques. Vous pouvez créer des suites de rapports virtuelles dans le Gestionnaire de suites de rapports virtuelles ([!UICONTROL Composants] > [!UICONTROL Suites de rapports virtuelles]). Voir &quot;[Processus des suites de rapports virtuelles](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)&quot; pour plus d’informations.

L’utilisation de suites de rapports virtuelles au lieu du balisage multi-suite est souvent recommandée, mais les suites de rapports virtuelles présentent certaines limites. Voir &quot;[Suites de rapports virtuelles et considérations relatives au balisage multi-suite](/help/components/vrs/vrs-considerations.md)&quot; pour déterminer quelle approche de suite de rapports constitue le meilleur choix pour vos besoins professionnels. Pour une comparaison approfondie des suites de rapports virtuelles et de la fonctionnalité de balisage multi-suite, voir &quot;[Suites de rapports virtuelles par rapport au balisage multi-suite](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot;.

## Rapports de cumul

>[!NOTE]
>
>[!DNL Reports & Analytics] est le seul outil qui prend en charge les rapports de cumul et l’Adobe ne recommande plus l’utilisation de cumuls. Envisagez plutôt d’utiliser une suite de rapports globale avec un balisage multi-suite ou des suites de rapports virtuelles.

Un rapport de cumul est une simple agrégation de données provenant de plusieurs suites de rapports, sans déduplication ni segmentation ni ventilation de données. Les cumuls ne nécessitent pas l’implémentation du code. Pour utiliser les rapports de cumul, [implémentez les suites de rapports enfants](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md), puis [combinez-les dans un rapport de cumul](/help/admin/c-manage-report-suites/t-rollups.md) à l&#39;aide des [!UICONTROL outils d&#39;administration].

Les rapports de cumul sont gratuits : les suites de rapports enfants exécutent leurs propres appels serveur, mais le cumul n’entraîne pas d’appels supplémentaires. Les cumuls sont une fonctionnalité héritée qui présente de nombreuses limites.

### Limites des rapports de cumul {#limitations-rollups}

* Les cumuls fournissent des données totales, mais ils ne génèrent pas de rapports sur des valeurs individuelles. Par exemple, les valeurs eVar1 ne sont pas incluses, mais le total de leur agrégat peut l’être.
* Les données ne sont pas dédupliquées lorsque le cumul combine des données entre des suites de rapports.
* Les cumuls s&#39;exécutent tous les soirs à minuit.
* Lorsque vous ajoutez une suite de rapports à un cumul existant, les données historiques ne sont pas incluses dans le cumul.
* Toutes les suites de rapports enfants doivent contenir des données pour qu’un cumul fonctionne. Si de nouvelles Report Suites sont incluses dans un cumul, veillez à envoyer au moins une vue de page à chacune de ces Report Suites.
* Les suites de rapports de cumul peuvent inclure un maximum de 40 suites enfants.
* Les suites de rapports de cumul peuvent contenir un maximum de 100 événements.
* Les données contenues dans les suites de rapports de cumul ne prennent pas en charge les ventilations ou les segments.
* Le rapport Pages est remplacé par le rapport Sites les plus populaires, qui tient compte des mesures au niveau de la suite enfant.

## Comparaison des fonctionnalités des Report Suites globales et des rapports de cumul

**Deuxième appel serveur** : les cumuls n’impliquent aucun appel au serveur supplémentaire au-delà de ce qu’une seule suite de rapports collecte. Si votre entreprise utilise le balisage multisuite, un deuxième appel serveur est effectué pour chaque suite de rapports supplémentaire incluse dans une demande d’image.

>[!TIP]
>
>Si vous utilisez uniquement une suite de rapports globale avec des [suites de rapports virtuelles](/help/components/vrs/vrs-considerations.md), aucun deuxième appel serveur n’est nécessaire.

**Modifications de l’implémentation** : les cumuls ne nécessitent aucune modification de l’implémentation, tandis que les suites de rapports globales nécessitent que vous incluiez l’identifiant de suite de rapports globale dans votre implémentation.

**Duplication** : contrairement aux cumuls, les suites de rapports globales dédupliquent les visiteurs uniques. Ainsi, si un utilisateur visite trois ou quatre de vos domaines le même jour, les cumuls comptabilisent trois visiteurs uniques par jour. Quant aux suites de rapports globales, elles n’en comptabilisent qu’un seul.

**Période** : les cumuls ne sont traités qu’à minuit, tous les jours, alors que les suites de rapports globales génèrent des rapports sur les données avec une latence standard.

**Étendue** : les cumuls n’offrent aucun moyen de communiquer entre les suites de rapports. Les suites de rapports globales peuvent attribuer du crédit aux variables de conversion entre les suites de rapports et fournir un cheminement entre les suites de rapports.

**Données historiques** : les cumuls peuvent agréger des données historiques, alors que les suites de rapports globales ne génèrent des rapports qu’à partir du point où les données ont été implémentées.

**Rapports** : les suites de rapports globales fournissent des données sur l’ensemble des dimensions. Les cumuls ne fournissent des données agrégées que sur les rapports de haut niveau.

**Produits pris en charge** : les cumuls ne peuvent être utilisés que dans Reports &amp; Analytics. Ils ne sont pas pris en charge en Analysis Workspace ou en Data Warehouse. Les suites de rapports globales peuvent être utilisées pour tous les produits.

**Nombre de suites de rapports agrégées** : les cumuls ne prennent en charge que 40 suites de rapports enfants au maximum. Les suites de rapports globales peuvent être implémentées sur n’importe quel nombre de domaines ou d’applications que vous détenez.
