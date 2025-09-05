---
description: Étiqueter les données de la suite de rapports signifie que vous attribuez des libellés d’identité, de sensibilité et des étiquettes de gouvernance des données à chaque variable dans une suite de rapports donnée.
title: Présentation de l’étiquetage de confidentialité
feature: Data Governance
role: Admin
exl-id: d1bd833c-3fd4-4572-a5dc-d7bab8a79cb8
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 98%

---

# Présentation de l’étiquetage de confidentialité

Étiqueter les données de la suite de rapports signifie que vous attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports donnée. Assurez-vous d’abord de vous familiariser avec les [étiquettes et leurs définitions](/help/admin/tools/privacy-labeling/labels.md).

>[!NOTE]
>
>Souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes.

## Attribuer ou modifier des étiquettes de confidentialité de suites de rapports {#assign-edit}

**Exemple** : en tant que contrôleur de données, prévoyez de collecter des adresses e-mail et des ID de cookie auprès des titulaires de données pour traiter leurs demandes relatives à la Confidentialité des données. Ces ID de cookie sont stockés dans une suite de rapports dans Adobe Analytics.

1. Dans Adobe Analytics, accédez à **[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Configuration et collecte des données]** > **[!UICONTROL Gouvernance des données]**.

   ![Étiquetage de confidentialité](assets/privacy_rs_settings.png)

1. Sélectionnez une suite de rapports dans le sélecteur de **[!UICONTROL Suites de rapports]** en haut.

1. Dans la section de filtrage de gauche, sélectionnez les groupes de variables à étiqueter. Vous ne pouvez étiqueter qu’un seul groupe de variables à la fois.

   * **Composants standard** : les composants standard sont des dimensions et des mesures Analytics prêtes à l’emploi qui sont collectées par défaut dans une implémentation Analytics.
   * **Variables de conversion** : la variable de conversion Custom Insight (eVar) est placée dans le code Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés. Une eVar peut être basée sur les visites et fonctionner comme un cookie. Les valeurs transmises dans des variables eVar suivent l’utilisateur pendant une période prédéfinie.
   * **Variables de liste** : les variables de liste sont des variables personnalisées que vous pouvez utiliser à votre guise. Elles fonctionnent de la même manière que les eVars, sauf qu’elles peuvent contenir plusieurs valeurs dans le même accès. Les variables de liste n’ont pas de limite de caractères.
   * **Variables de trafic** : les variables de trafic Custom Insight (props) vous permettent d’établir des corrélations entre des données personnalisées et des événements liés à un trafic spécifiques. Les variables prop sont intégrées au code de mise en œuvre dans chaque page de votre site Web.
   * **Événements de succès** : les événements de succès (également appelés événements de conversion ou événements personnalisés) sont des actions dont le suivi peut être effectué. Il vous appartient de déterminer ce qu’est un événement de succès. Par exemple, si une personne achète un article, l’achat peut être considéré comme un événement de succès.
   * **Classification** : les répartitions de classification permettent de mettre en correspondance les données des rapports Analytics et les propriétés les concernant. Les classifications peuvent être utilisées à diverses fins. Toutefois, elles servent principalement à classer les codes de suivi de campagne (internes et externes), ainsi que les identifiants de produits.

1. Sélectionnez une variable en cochant sa case, puis cliquez sur **[!UICONTROL Modifier les étiquettes de confidentialité]** dans la barre bleue qui s’affiche en bas de l’écran.

   ![Modifier](assets/edit-label.png)

   Cet écran affiche les étiquettes actuellement appliquées et vous permet d’appliquer des étiquettes supplémentaires. Il se peut que vous ne puissiez pas appliquer ni modifier toutes les étiquettes, selon le composant.

   ![Étiquettes appliquées](assets/edit-labels2.png)

1. Cliquez sur **[!UICONTROL Appliquer]** une fois l’étiquetage terminé.

