---
description: Explique comment extraire des ressources publiées du Report Builder dans Power BI Desktop
title: Extraction des éléments publiés dans Power BI Desktop
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
TQID: https://experienceleague.adobe.com/fS1xnUciNh8LdPw2ENYMJTDGLqo3C8u4lu39X-GYuZE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 69%

---

# Extraction des éléments publiés dans Power BI Desktop

{{legacy-arb}}

Explique comment extraire des ressources publiées du Report Builder dans Power BI Desktop

## Conditions préalables {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* La dernière version de Power BI Desktop doit être installée (version d’avril 2017)
* Ce processus suppose que vous avez déjà publié des tableaux ou des requêtes au format du Report Builder sur le service Power BI.

## Processus {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

Dans la mise à jour d’avril 2017 de Power BI Desktop, Microsoft a publié la possibilité de se connecter aux jeux de données dans le service Power BI. Cette fonctionnalité vous permet de créer des rapports sur les jeux de données existants que vous avez déjà publiés sur le cloud. Vous pouvez tirer parti de cette fonctionnalité pour améliorer la collaboration et réduire les efforts en double au sein de votre équipe.

1. Dans Power BI Desktop, sélectionnez **[!UICONTROL Fichier]** > **[!UICONTROL Options et paramètres]** > **[!UICONTROL Options]** > **[!UICONTROL Fonctionnalités en préversion.]**
1. Activez l’option **[!UICONTROL Connexion active du service Power BI]** et cliquez sur **[!UICONTROL OK]**. ![Cliquez sur Connexion active du service Power BI, puis sur OK. &#x200B;](assets/bi-preview-features.png)

1. Redémarrez Power BI Desktop.
1. Une fois que le desktop est redémarré, sélectionnez **[!UICONTROL Accueil]** > **[!UICONTROL Obtenir des données]** > **[!UICONTROL Plus...]**.
1. Recherchez et sélectionnez **[!UICONTROL Service Power BI]**.
1. En dessous de l’option **[!UICONTROL Service Microsoft Power BI]** > **[!UICONTROL Mon espace de travail]**, sélectionnez le jeu de données que vous avez précédemment publié à partir du Report Builder.

Pour plus d’informations, voir cet [article de blog de Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
