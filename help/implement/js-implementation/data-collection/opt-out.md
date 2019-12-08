---
description: valeur nulle
keywords: Analytics Implementation
title: Implémentation des droits d’opposition Adobe
topic: Developer and implementation
uuid: fc3a411c-8476-409d-99de-05b34ace5019
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implémentation des droits d’opposition Adobe

Il se peut que des visiteurs de votre site web préfèrent que leurs informations de navigation ne soient pas agrégées et analysées par les produits et services Adobe Experience Cloud, ni utilisées en vue de diffuser des publicités et du contenu pertinents. Adobe vous offre la possibilité de fournir aux visiteurs le moyen d’exclure leurs informations de la collecte effectuée par les produits Adobe suivants :

* Adobe Analytics
* Adobe Target
* Adobe Audience Targeted Creative
* Adobe AudienceManager
* Adobe AdLens
* Adobe Experience Manager

## Recommandations relatives à la politique de confidentialité {#section_BBDEE21C259842F7881642E31FB3D9B7}

Adobe vous conseille de fournir aux visiteurs de votre site Web des informations claires et facilement accessibles concernant la possibilité d’exclure leurs informations de navigation de la collecte réalisée par les produits ou services Adobe.

Pour en savoir plus sur l’utilisation faite généralement par Adobe des informations collectées dans le cadre de la fourniture des produits et services aux clients, rendez-vous dans le [Centre de traitement des données personnelles d’Adobe](https://www.adobe.com/privacy.html). Cependant, dans le mesure où vous seul contrôlez l’implémentation de nos services sur vos sites Web, il vous appartient d’expliquer à vos visiteurs les méthodes spécifiques qu’ils appliquent pour utiliser nos produits et services. Vous êtes responsable de la création de votre propre politique de confidentialité, de son respect, du respect du contrat de service conclu avec Adobe, ainsi que du respect de toutes les lois en vigueur.

## Exclusions pour Adobe Analytics (y compris les rapports et analyses, l’entrepôt de données, et l’analyse ad hoc) {#section_8089B80CDA4043C9BC2DED49E484E8D7}

Adobe propose trois types d’exclusion pour Adobe Analytics (y compris les [!UICONTROL rapports et analyses], l’[!UICONTROL entrepôt de données] et les [!UICONTROL analyses ad hoc]) :

* Si vous implémentez des produits Adobe Analytics avec votre propre cookie interne, vous devez [développer votre propre lien d’exclusion personnalisé](/help/implement/js-implementation/data-collection/opt-out-link.md) pour les visiteurs de votre site web.
* Vos clients peuvent activer l’option d’exclusion dans les paramètres de cookies du navigateur. Voir [Activation des paramètres de confidentialité pour les cookies de navigateur](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/browser_cookie_settings.html) (en anglais).

Quel que soit le mécanisme d’exclusion choisi, Adobe conseille d’en décrire clairement la disponibilité dans votre politique de confidentialité, ou au titre d’autres exigences prévues par la loi ou selon les recommandations des bonnes pratiques en cours.
