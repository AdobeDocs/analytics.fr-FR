---
description: Adobe Analytics peut être mis en œuvre de différentes façons.
keywords: Mise en œuvre d’Analytics;méthode de mise en œuvre;Dynamic Tag Management;dtm;javascript
seo-description: Adobe Analytics peut être mis en œuvre de différentes façons.
seo-title: Choix d’une méthode de mise en œuvre
solution: Analytics
title: Choix d’une méthode de mise en œuvre
topic: Développeur et mise en œuvre
uuid: 20d3317f-7c63-4421-93e0-fff60dbd9f87
translation-type: ht
source-git-commit: b1e69abd65f171b804e7f56031e594890bbd27bb

---


# Choix d’une méthode de mise en œuvre

Adobe Analytics peut être mis en œuvre de différentes façons.

* [!UICONTROL Adobe Experience Platform Launch] (Recommandé)
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Adobe Experience Platform Launch] {#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Experience Platform Launch] est la nouvelle génération de fonctionnalités de gestion de SDK mobile et de balises de sites web. [!UICONTROL Experience Platform Launch] offre un moyen simple de déployer et gérer toutes les intégrations d’analyse, de marketing et de publicité nécessaires pour proposer des expériences client pertinentes.

[!UICONTROL Experience Platform Launch] permet à tous les utilisateurs de créer et gérer leurs propres intégrations avec [!DNL Experience Platform Launch], appelées extensions. Ces extensions sont disponibles pour les clients [!UICONTROL Experience Platform Launch] web et mobiles sous la forme d’une expérience de boutique d’applications qui leur permet d’installer, configurer et déployer rapidement leurs intégrations.

Pour plus d’informations, reportez-vous à la section [Prise en main d’Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL Dynamic Tag Management] automatise une grande partie du travail minutieux requis pour mettre en œuvre [!DNL Analytics]. Saisissez les informations requises dans une interface reposant sur des formulaires, et [!DNL Dynamic Tag Management] génère le code que vous devez ajouter à vos pages.
Il est utile de connaître JavaScript et de comprendre la terminologie de base d’Analytics, telle que

* Qu’est-ce qu’une [eVar](https://marketing.adobe.com/resources/help/fr_FR/reference/conversion_var_admin.html) et comment fonctionne-t-elle ?
* Quand utiliser un [événement personnalisé](../../implement/analytics-terminology-basics/c-props-evars/event-custom.md#concept_CDA3C98C85B24A71B4B5C71F24BF918F)

Pour plus d’informations sur l’accès à Dynamic Tag Management et sur son exécution, reportez-vous à la section [Prise en main](https://marketing.adobe.com/resources/help/fr_FR/dtm/get_started.html) dans la documentation du produit Dynamic Tag Management.

Pour plus d’informations, reportez-vous à la section [Mise en œuvre d’Analytics avec Dynamic Tag Management](../../implement/c-implement-with-dtm/dtm-implementation-overview.md).

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

La méthode de mise en œuvre avec JavaScript nécessite de configurer manuellement les codes JavaScript sur vos pages. Il est possible de simplifier cet effort en utilisant les méthodes de mise en œuvre d’Experience Platform Launch ou de Dynamic Tag Management. Certains utilisateurs peuvent toutefois nécessiter la méthode avec JavaScript.

La mise en œuvre avec JavaScript requiert :

* de solides compétences en JavaScript ;
* une bonne compréhension des concepts et de la terminologie d’Analytics.

Pour plus d’informations, voir [Mise en œuvre d’Analytics avec JavaScript](../../implement/js-implementation/javascript-implementation-overview.md).
