---
description: Comprenez comment un flux interdimensionnel vous permet d’examiner les chemins d’accès des utilisateurs sur différentes dimensions.
title: Flux interdimensionnels
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
TQID: https://experienceleague.adobe.com/9OjAFYHo5uhcfbQQOB46jfG1R2wIQCBHXEr842EcZQ0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 338
ht-degree: 95%

---

# Flux interdimensionnels

Un flux interdimensionnel vous permet d’examiner les chemins d’accès pour les utilisateurs et utilisatrices sur plusieurs dimensions.

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Inter-dimensional flows](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/text-wrapping-and-multi-dimensional-flow){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

Cet article montre comment utiliser ce flux pour deux cas d’utilisation : les interactions et les événements d’applications mobiles, et la manière dont les campagnes génèrent des visites web.

## Interactions et événements des applications mobiles

La dimension [!UICONTROL Nom de l’écran] est utilisée dans cet exemple de flux pour voir comment les utilisateurs et utilisatrices utilisent les différents écrans (scènes) dans l’application. L’écran supérieur renvoyé est **[!UICONTROL luma: content: ios: en: home]**, qui est la page d’accueil de l’application :

![Flux affichant l’élément ajouté.](assets/flowapp.png)

Pour explorer l’interaction entre les écrans et les types d’événement (tels que l’ajout au panier, les achats, etc.) dans cette application, effectuez un glisser-déposer de la dimension **[!UICONTROL Types d’événement]** :

* En plus de toute étape disponible dans le flux, pour remplacer cette dimension, procédez comme suit :

  ![Flux présentant la dimension Page placée dans plusieurs zones.](assets/flowapp-replace.png)

* En dehors de la visualisation de flux actuelle, pour ajouter la dimension, procédez comme suit :

  ![Flux affichant la dimension Page placée dans l’espace blanc à la fin.](assets/flowapp-add.png)

La visualisation de flux ci-dessous montre le résultat de l’ajout de la dimension **[!UICONTROL Types d’événement]**. La visualisation fournit des informations sur la manière dont les utilisateurs et utilisatrices d’applications mobiles se déplacent sur différents écrans de l’application avant d’ajouter des produits à un panier, de fermer l’application, de se voir présenter une offre, etc.

![Flux affichant les résultats de la dimension Page en haut de la liste.](assets/flowapp-result.png)

## Génération de visites web par les campagnes

Vous souhaitez analyser les campagnes qui génèrent des visites sur le site web. Vous créez une visualisation de flux avec la dimension **[!UICONTROL Nom de la campagne]**.

![Dimension du nom de la campagne web de flux](assets/flowweb.png)

Vous remplacez la dernière dimension **[!UICONTROL Nom de la campagne]** par la dimension **[!UICONTROL Nom de page formaté]** et ajoutez une autre dimension **[!UICONTROL Nom de page formaté]** à la fin de la visualisation de flux.

![Nom de campagne web de flux et dimension de page web](assets/flowweb-replace.png)

Vous pouvez pointer sur n’importe quel flux pour afficher plus de détails. Par exemple, les campagnes qui ont généré un passage en caisse du panier.

![Nom de campagne web de flux et pointage sur la dimension de page web](assets/flowweb-hover.png)
