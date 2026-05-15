---
description: Les administrateurs et administratrices sont chargés de surveiller l’intégrité du dictionnaire de données. Cela inclut le fait de savoir si les composants collectent des données, sont approuvés, contiennent des descriptions et sont exempts de doublons.
title: Surveiller l’intégrité du dictionnaire de données
feature: Components
role: Admin
exl-id: 82176931-2bd9-4f4e-9ca7-4214d44151a8
TQID: https://experienceleague.adobe.com/q-wAiW4oUc9kH-ywKVLfNKtXHdEfnIr01GXSK-g0YqY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ba438d61e6834acb07c86cd0af58f95b88c1de7
workflow-type: tm+mt
source-wordcount: 361
ht-degree: 66%

---

# Surveiller l’intégrité du dictionnaire de données {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_share_primary"
>title="Partager le composant principal"
>abstract="Lorsque cette option est sélectionnée, le composant principal est partagé avec toutes les personnes ayant accès aux composants en double (les propriétaires et les personnes avec lesquelles les composants sont partagés). Ces utilisateurs peuvent ensuite sélectionner le composant principal dans la liste des composants pour les projets futurs. Cependant, il ne peut pas modifier le composant, même s’il était propriétaire d’un composant en double qui a été consolidé. <br/>Cette option est disponible uniquement lorsque le composant principal est un segment, une mesure calculée ou une période. Les mesures et dimensions sont toujours disponibles pour tous les utilisateurs et utilisatrices.
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_delete_duplicates"
>title="Supprimer les doublons remplacés"
>abstract="Lorsque cette option est sélectionnée, les doublons consolidés ne sont plus disponibles. Désélectionnez cette option si vous souhaitez que les doublons restent disponibles."

<!-- markdownlint-enable MD034 -->

Les administrateurs et administratrices d’Analytics sont chargées de maintenir l’intégrité du dictionnaire de données.

## Caractéristiques d’un dictionnaire de données intègre

Dans un dictionnaire de données intègre, tous les composants :

* sont utilisés et collectent des données ;

* contiennent des descriptions utiles pour que les utilisateurs et utilisatrices sachent comment les utiliser au mieux ;

* sont exempts de doublons superflus ;

* sont approuvés par l’administrateur ou l’administratrice.

## Vérifier l’intégrité de votre dictionnaire de données

Pour identifier les problèmes d’intégrité dans votre dictionnaire de données :

1. Ouvrez un projet Analysis Workspace.

1. Sélectionnez l’icône du dictionnaire de données sur le côté gauche d’Analysis Workspace. (Les autres méthodes d’accès au dictionnaire de données sont décrites dans « Accéder au dictionnaire de données » dans la [présentation du dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   La fenêtre Dictionnaire de données s’affiche.

   ![Vue d’administration du dictionnaire de données.](assets/data-dictionary-admin.png)

1. Assurez-vous que la bonne suite de rapports est sélectionnée dans le menu déroulant.

1. Sur l’onglet [!UICONTROL **Intégrité du dictionnaire**], sélectionnez [!UICONTROL **Affichage**] en regard de l’une des options suivantes :

   * [!UICONTROL **composants sans description**],

   * [!UICONTROL **composants avec doublons**],

   * [!UICONTROL **composants sans données connectées**].

   Selon ce que vous sélectionnez, le filtre approprié est appliqué au dictionnaire de données et seuls les composants appropriés sont affichés.

1. Modifiez l’un des composants pour améliorer l’intégrité du dictionnaire de données. Pour plus d’informations sur la modification d’un composant dans le dictionnaire de données, voir [Modifier les entrées de composant dans le dictionnaire de données](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).
