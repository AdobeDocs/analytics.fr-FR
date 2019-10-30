---
description: Analytics comptabilise chaque identifiant visiteur effectif unique comme un visiteur unique.
keywords: Mise en œuvre d’Analytics
seo-description: Analytics comptabilise chaque identifiant visiteur effectif unique comme un visiteur unique.
seo-title: Visiteurs
solution: Analytics
subtopic: Visiteurs
title: Visiteurs
topic: Développeur et mise en œuvre
uuid: 16cfdb64-a3c6-4056-97da-3227cddcf1cd
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Visiteurs

>[!IMPORTANT]
>
>Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la documentation [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Analytics comptabilise chaque identifiant visiteur effectif unique comme un visiteur unique.

Si vous observez le [tableau précédent](../../../implement/js-implementation/xdevice-visid/visit-example.md#concept_E3B32B8E539F4FDC8E3FA872328B87BA), cela s’est produit à trois reprises : aux accès 1, 9 et 10. Cela est dû au fait que l’[!UICONTROL identifiant visiteur] effectif est le même pour les deux appels au serveur et ce, bien que les visites aient été effectuées sur des périphériques différents à plusieurs heures d’intervalle.

Cela risque d’augmenter le nombre de visiteurs uniques affichés lorsque la fonction d’identification des visiteurs sur plusieurs périphériques est activée. Le visiteur peut ainsi être comptabilisé deux fois pour la même visite : une fois pour la visite initiale et une autre fois après son authentification.

Lorsqu’un nouveau visiteur affiche votre site, le cookie `s_vi`est alimenté et stocké. Sur le serveur de collecte de données, un nouveau profil du visiteur est créé pour cet identifiant utilisateur et l’[!UICONTROL identifiant utilisateur] effectif sur le profil est défini de manière à correspondre au cookie.

Lorsque la fonction d’identification des visiteurs sur plusieurs périphériques est activée, si une variable [!UICONTROL identifiant visiteur] est fournie au cours d’un accès ultérieur (après une authentification, par exemple), l’[!UICONTROL identifiant visiteur] effectif est mis à jour afin de correspondre à la valeur personnalisée. Cela peut se traduire par la modification de l’[!UICONTROL identifiant visiteur] effectif après l’authentification, d’où plusieurs comptabilisations du visiteur.

![](assets/visitors.png)

Après l’association initiale, le nombre de visites revient à la normale, car le visiteur est associé par le biais du cookie [!UICONTROL identifiant visiteur]. Si, par la suite, le visiteur consulte votre site, puis s’authentifie, le nombre de visites n’augmente pas, car l’[!UICONTROL identifiant visiteur effectif] reste inchangé après l’authentification.

![](assets/visitors_2.png)

