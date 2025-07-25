---
description: Comprenez comment un flux interdimensionnel vous permet d’examiner les chemins d’accès des utilisateurs sur différentes dimensions.
title: Flux interdimensionnels
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 96%

---

# Flux interdimensionnels

Dans un flux interdimensionnel, vous pouvez examiner le cheminement des utilisateurs dans plusieurs dimensions.

>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Flux interdimensionnels](https://video.tv.adobe.com/v/327470?quality=12&learn=on&captions=fre_fr){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

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
