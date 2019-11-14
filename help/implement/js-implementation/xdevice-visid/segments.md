---
description: Vous pouvez créer un segment chaque fois qu’une association se produit pour un cookie identifiant visiteur.
keywords: Analytics Implementation
solution: Analytics
title: Création de segments
topic: Developer and implementation
uuid: 476a4667-033c-4e53-961d-ad67e7c2b045
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Création de segments

>[!IMPORTANT]
>
>Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la documentation [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Vous pouvez créer un segment chaque fois qu’une association se produit pour un cookie identifiant visiteur.

Sur la base du [tableau précédent](/help/implement/js-implementation/xdevice-visid/visit-example.md), si vous avez créé un segment dont le numéro de visite est égal à 9, les appels au serveur 12 et 13 seront inclus. Même si, d’un point de vue technique, l’appel au serveur 11 faisait partie de la même visite, les données historiques correspondantes ne sont pas modifiées et le numéro de visite reste inchangé.
