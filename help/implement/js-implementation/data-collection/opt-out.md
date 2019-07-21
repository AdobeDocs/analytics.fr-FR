---
description: valeur nulle
keywords: Mise en œuvre d’Analytics
seo-description: valeur nulle
seo-title: Implémentation d'exclusions Adobe
solution: Analytics
title: Implémentation d'exclusions Adobe
topic: Développeur et mise en œuvre
uuid: fc 3 a 411 c -8476-409 d -99 de -05 b 34 ace 5019
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Implémentation d'exclusions Adobe

Il se peut que des visiteurs de votre site web préfèrent que leurs informations de navigation ne soient pas agrégées et analysées par les produits et services Adobe Experience Cloud, ni utilisées en vue de diffuser des publicités et du contenu pertinents. Adobe vous offre la possibilité de fournir aux visiteurs le moyen d’exclure leurs informations de la collecte effectuée par les produits Adobe suivants :

* Adobe Analytics
* Adobe Target
* Adobe Audience Targeted Creative
* Adobe AudienceManager
* Adobe AdLens
* Adobe Experience Manager

## Recommandations relatives à la politique de confidentialité {#section_BBDEE21C259842F7881642E31FB3D9B7}

Adobe vous conseille de fournir aux visiteurs de votre site Web des informations claires et facilement accessibles concernant la possibilité d’exclure leurs informations de navigation de la collecte réalisée par les produits ou services Adobe.

Pour en savoir plus sur l’utilisation faite généralement par Adobe des informations collectées dans le cadre de la fourniture des produits et services aux clients, rendez-vous dans le [Centre de traitement des données personnelles d’Adobe](https://www.adobe.com/privacy.html). Cependant, dans le mesure où vous seul contrôlez l’implémentation de nos services sur vos sites Web, il vous appartient d’expliquer à vos visiteurs les méthodes spécifiques qu’ils appliquent pour utiliser nos produits et services. Vous êtes responsable de la création de votre propre politique de confidentialité, de son respect, du respect du contrat de service conclu avec Adobe, ainsi que du respect de toutes les lois en vigueur.

## Opt-outs for Adobe Analytics (including Reports &amp; Analytics, Data Warehouse, Ad Hoc Analysis) {#section_8089B80CDA4043C9BC2DED49E484E8D7}

Adobe offers three types of opt-outs for Adobe Analytics (including [!UICONTROL Reports &amp; Analytics], [!UICONTROL Data Warehouse], [!UICONTROL Ad Hoc Analysis]):

* If you implement Adobe Analytics products with your own first-party cookie, you need to [develop your own customized opt-out link](../../../implement/js-implementation/data-collection/opt-out-link.md#concept_C2C4F19811A445EF9E9BEAC709B568A9) for your website visitors.
* Adobe propose également un mécanisme public d’exclusion pour les sites Web à l’aide des cookies définis à partir des domaines omtrdc.net et 2o7.net d’Adobe. Ce mécanisme est accessible dans le [Centre de traitement des données personnelles d’Adobe](https://www.adobe.com/privacy/opt-out.html).
* Vos clients peuvent activer l’option d’exclusion dans les paramètres de cookies du navigateur. Voir [Activation des paramètres de confidentialité pour les cookies de navigateur](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/?f=browser_cookie_settings) (en anglais).

Quel que soit le mécanisme d’exclusion choisi, Adobe conseille d’en décrire clairement la disponibilité dans votre politique de confidentialité, ou au titre d’autres exigences prévues par la loi ou selon les recommandations des bonnes pratiques en cours.
