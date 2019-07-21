---
description: Adobe Analytics peut être mis en œuvre de différentes façons.
keywords: Implémentation d'Analytics ; implementation method ; gestion dynamique des balises ; dtm ; javascript
seo-description: Adobe Analytics peut être mis en œuvre de différentes façons.
seo-title: Choix d’une méthode de mise en œuvre
solution: Analytics
title: Choix d’une méthode de mise en œuvre
topic: Développeur et mise en œuvre
uuid: 20 d 3317 f -7 c 63-4421-93 e 0-fff 60 dbd 9 f 87
translation-type: tm+mt
source-git-commit: b1e69abd65f171b804e7f56031e594890bbd27bb

---


# Choix d’une méthode de mise en œuvre

Adobe Analytics peut être mis en œuvre de différentes façons.

* [!UICONTROL Lancement de la plateforme Adobe Experience Platform] (recommandé)
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Lancement d'Adobe Experience Platform]{#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Launch Platform Launch] est la prochaine génération de balises de site Web et de fonctionnalités de gestion du SDK mobile d'Adobe. [!UICONTROL Le lancement de Platform Platform vous] offre un moyen simple de déployer et de gérer toutes les intégrations d'analyse, de marketing et de publicité nécessaires pour alimenter les expériences client pertinentes.

[!UICONTROL Experience Platform Launch] permet aux utilisateurs de créer et de gérer leurs propres intégrations, [!DNL Experience Platform Launch]appelées Extensions. These extensions are available to web and mobile [!UICONTROL Experience Platform Launch] customers in an app-store experience, so customers can quickly install, configure, and deploy their integrations.

For more information, see [Getting Started with Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL La gestion dynamique des balises] automatise la majeure partie des tâches de détails à mettre en œuvre [!DNL Analytics]. Saisissez les informations requises dans une interface reposant sur des formulaires, et [!DNL Dynamic Tag Management] génère le code que vous devez ajouter à vos pages.
Il est utile de connaître JavaScript et de comprendre la terminologie Analytics de base, telle que

* ce qu’est une [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) et comment elle fonctionne ;
* quand utiliser un [événement personnalisé](../../implement/analytics-terminology-basics/c-props-evars/event-custom.md#concept_CDA3C98C85B24A71B4B5C71F24BF918F).

Pour plus d’informations sur l’obtention de l’accès à Dynamic Tag Management et son fonctionnement, voir [Prise en main](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) dans la documentation du produit de Dynamic Tag Management.

Pour plus d’informations, voir [Implémentation d'Analytics à l'aide de la gestion dynamique des balises](../../implement/c-implement-with-dtm/dtm-implementation-overview.md).

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

La méthode de mise en œuvre avec JavaScript nécessite de configurer manuellement les codes JavaScript sur vos pages. Une grande partie de cet effort peut être simplifiée si vous utilisez le lancement de la plateforme Expert ou les méthodes d'implémentation de la gestion dynamique des balises. Certains utilisateurs peuvent toutefois nécessiter la méthode avec JavaScript.

La mise en œuvre avec JavaScript requiert :

* de solides compétences en JavaScript ;
* une bonne compréhension des concepts et de la terminologie d’Analytics.

Pour plus d’informations, voir [Implémentation d'Analytics à l'aide de JavaScript](../../implement/js-implementation/javascript-implementation-overview.md).
