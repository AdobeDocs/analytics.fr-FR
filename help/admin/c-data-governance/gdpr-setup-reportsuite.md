---
description: Étiqueter les données de la suite de rapports signifie que vous attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports donnée.
title: Étiqueter les données d’une suite de rapports
feature: Data Governance
exl-id: d1bd833c-3fd4-4572-a5dc-d7bab8a79cb8
source-git-commit: bb5204584ebcd5be3254f34b0954f53e6fb11ea4
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 50%

---

# Étiqueter les données d’une suite de rapports

>[!NOTE]
>
>Cette interface utilisateur mise à jour est actuellement en test limité.

Étiqueter les données de la suite de rapports signifie que vous attribuez des étiquettes d’identité, de sensibilité et de gouvernance des données à chaque variable dans une suite de rapports donnée. Assurez-vous d’abord de vous familiariser avec le [libellés et leurs définitions](/help/admin/c-data-governance/gdpr-labels.md).

>[!NOTE]
>
>Souvenez-vous que l’étiquetage doit être vérifié chaque fois qu’une nouvelle suite de rapports est créée ou qu’une nouvelle variable est activée dans une suite de rapports existante. Il peut également être nécessaire de vérifier l’étiquetage lors de l’activation de nouvelles intégrations à des solutions puisque celles-ci peuvent exposer de nouvelles variables nécessitant un étiquetage. Une nouvelle implémentation de vos applications mobiles ou sites web peut modifier la manière dont les variables existantes sont utilisées, rendant nécessaire la mise à jour des étiquettes.

## Attribuer ou modifier des étiquettes de confidentialité de suite de rapports {#assign-edit}

**Exemple** : en tant que contrôleur des données, vous prévoyez de collecter des adresses électroniques et des ID de cookie auprès des sujets des données pour traiter leurs demandes relatives à la Confidentialité des données. Ces ID de cookie sont stockés dans une suite de rapports dans Adobe Analytics. Pour créer un libellé pour les adresses électroniques et les ID de cookie, vous devez utiliser la structure DULE (Data Usage Labeling &amp; Enforcement) de la plateforme Adobe Experience Cloud dans Analytics.

1. Dans Adobe Analytics, accédez à **[!UICONTROL Administration]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Configuration et collecte des données]** > **[!UICONTROL Gouvernance des données]**.

   ![Étiquetage de la confidentialité](assets/privacy_rs_settings.png)

1. Sélectionnez une suite de rapports dans le **[!UICONTROL Suites de rapports]** sélecteur dans la partie supérieure.

1. Dans la section des filtres située à gauche, sélectionnez les groupes de variables à étiqueter. Vous ne pouvez étiqueter qu’un seul groupe de variables à la fois.

   * **Composants standard** - Les composants standard sont des dimensions et des mesures Analytics prêtes à l’emploi qui sont collectées par défaut dans une implémentation Analytics.
   * **Variables de conversion** - La variable de conversion Custom Insight (ou l’eVar) est placée dans le code d’Adobe sur les pages web sélectionnées de votre site. Son principal objectif est de segmenter les mesures de succès de conversion dans les rapports marketing personnalisés. Un eVar peut être basé sur les visites et fonctionner de la même manière que les cookies. Les valeurs transmises dans des variables eVar suivent l’utilisateur pendant une période prédéfinie.
   * **Variables de liste** - Les variables de liste sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Elles fonctionnent de la même manière que les eVars, sauf qu’elles peuvent contenir plusieurs valeurs dans le même accès. Les variables de liste n’ont pas de limite de caractères.
   * **Variables de trafic** - Les variables de trafic Custom Insight (ou props) vous permettent de mettre en corrélation des données personnalisées avec des événements liés au trafic spécifiques. Les variables prop sont intégrées au code de mise en œuvre dans chaque page de votre site web.
   * **Événements de succès** - Les événements de succès (également appelés événements de conversion ou événements personnalisés) sont des actions qui peuvent faire l’objet d’un suivi. Il vous appartient de déterminer ce qu’est un événement de succès. Par exemple, si un visiteur achète un article, l’achat peut être considéré comme un événement de succès..
   * **Classifications** - Les ventilations de classification sont utilisées pour mapper les données de rapport Analytics aux propriétés associées. Les classifications peuvent être utilisées à diverses fins, mais sont le plus souvent utilisées pour classer les codes de suivi de campagne (internes et externes) et les identifiants de produit.

1. Sélectionnez une variable en cochant sa case, puis cliquez sur **[!UICONTROL Modifier les étiquettes de confidentialité]** dans la barre bleue qui s’affiche en bas de l’écran.

   ![Modifier](assets/edit-label.png)

   Cet écran affiche les libellés actuellement appliqués et vous permet d’appliquer des libellés supplémentaires. Il se peut que vous ne puissiez pas appliquer ni modifier toutes les étiquettes, selon le composant.

   ![Libellés appliqués](assets/edit-labels2.png)

   >[!NOTE]
   >
   >Le cadre DULE (Data Usage Labeling &amp; Enforcement) est conçu pour fournir un moyen uniforme au sein des Solutions/Services/Plateformes pour capturer, communiquer et utiliser les métadonnées relatives aux données dans Adobe Experience Cloud. Les métadonnées aident les contrôleurs des données à indiquer quelles données sont des informations personnelles, des données sensibles et à définir les restrictions contractuelles associées aux données.

1. Cliquez sur **[!UICONTROL Appliquer]** une fois l’étiquetage terminé.

