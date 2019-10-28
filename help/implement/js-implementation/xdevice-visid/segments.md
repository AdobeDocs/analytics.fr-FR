---
description: Vous pouvez créer un segment chaque fois qu’une association se produit pour un cookie identifiant visiteur.
keywords: Mise en œuvre d’Analytics
seo-description: Vous pouvez créer un segment chaque fois qu’une association se produit pour un cookie identifiant visiteur.
seo-title: Création de segments
solution: Analytics
title: Création de segments
topic: Développeur et mise en œuvre
uuid: 476a4667-033c-4e53-961d-ad67e7c2b045
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Création de segments

>[!IMPORTANT]
>
>Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la [documentation d’Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/fr_FR/mcdc/).

Vous pouvez créer un segment chaque fois qu’une association se produit pour un cookie identifiant visiteur.

Sur la base du [tableau précédent](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), si vous avez créé un segment dont le numéro de visite est égal à 9, les appels au serveur 12 et 13 seront inclus. Même si, d’un point de vue technique, l’appel au serveur 11 faisait partie de la même visite, les données historiques correspondantes ne sont pas modifiées et le numéro de visite reste inchangé.
