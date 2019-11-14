---
description: Analytics comptabilise une visite chaque fois qu’un appel au serveur se produit avec un numéro de page de la visite égal à 1.
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: Visites
topic: Developer and implementation
uuid: 3035be8f-6adc-45df-a3f2-5de6d3ed99ce
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visites

>[!IMPORTANT]
>
>Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la documentation [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Analytics comptabilise une visite chaque fois qu’un appel au serveur se produit avec un numéro de page de la visite égal à 1.

Si vous observez le [tableau précédent](/help/implement/js-implementation/xdevice-visid/visit-example.md), cela s’est produit à quatre reprises : aux accès 1, 9, 11 et 12. Comme c’est le cas pour les visiteurs, cette valeur revient à la normale après l’association initiale, dans la mesure où le [!UICONTROL numéro de page de la visite] est rétabli sur 1 en raison du changement de l’[!UICONTROL identifiant visiteur] effectif.
