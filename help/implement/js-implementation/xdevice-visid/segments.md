---
description: Vous pouvez créer un segment chaque fois qu’une association se produit pour un cookie identifiant visiteur.
keywords: Mise en œuvre d’Analytics
seo-description: Vous pouvez créer un segment chaque fois qu’une association se produit pour un cookie identifiant visiteur.
seo-title: Création de segments
solution: Analytics
title: Création de segments
topic: Développeur et mise en œuvre
uuid: 476 a 4667-033 c -4 e 53-961 d-ad 67 e 7 c 2 b 045
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Création de segments

>[!IMPORTANT]
>
>Cette méthode d'identification des visiteurs sur l'ensemble des périphériques n'est plus recommandée. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Vous pouvez créer un segment chaque fois qu’une association se produit pour un cookie identifiant visiteur.

Based on the [previous table](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), if you created a segment where visit number equals 9, it would include server calls 12 and 13. Même si, d’un point de vue technique, l’appel au serveur 11 faisait partie de la même visite, les données historiques correspondantes ne sont pas modifiées et le numéro de visite reste inchangé.
