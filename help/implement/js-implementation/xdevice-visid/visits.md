---
description: 'Analytics comptabilise une visite chaque fois qu’un appel au serveur se produit avec un numéro de page de la visite égal à 1. '
keywords: Mise en œuvre d’Analytics
seo-description: 'Analytics comptabilise une visite chaque fois qu’un appel au serveur se produit avec un numéro de page de la visite égal à 1. '
seo-title: Visites
solution: Analytics
subtopic: Visiteurs
title: Visites
topic: Développeur et mise en œuvre
uuid: 3035 be 8 f -6 adc -45 df-a 3 f 2-5 de 6 d 3 ed 99 ce
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Visites

>[!IMPORTANT]
>
>Cette méthode d&#39;identification des visiteurs sur l&#39;ensemble des périphériques n&#39;est plus recommandée. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Analytics comptabilise une visite chaque fois qu’un appel au serveur se produit avec un numéro de page de la visite égal à 1. 

If you look at the [previous table](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), this occurred 4 times: at hits 1, 9, 11, and 12. Comme c’est le cas pour les visiteurs, cette valeur revient à la normale après l’association initiale, dans la mesure où le [!UICONTROL numéro de page de la visite] est rétabli sur 1 en raison du changement de l’[!UICONTROL identifiant visiteur] effectif.
