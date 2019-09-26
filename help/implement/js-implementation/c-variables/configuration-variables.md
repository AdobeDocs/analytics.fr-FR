---
description: Variables de configuration définies dans AppMeasurement.js.
keywords: Mise en œuvre d’Analytics
seo-description: Variables de configuration définies dans AppMeasurement.js pour Adobe Analytics
seo-title: Variables de configuration
solution: Analytics
subtopic: Variables
title: Variables de configuration
topic: Développeur et mise en œuvre
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# Présentation des variables de configuration

Les variables de configuration contrôlent le mode de collecte et de traitement des données dans les rapports. Variables de configuration les plus courantes généralement définies dans le fichier principal (global JavaScript AppMeasurement.js). Ces variables peuvent être définies dans le code de niveau page et les liens Analytics, le cas échéant.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Certaines de ces variables de configuration peuvent ne pas s’appliquer aux besoins de mise en œuvre de votre site.

Ces variables de configuration peuvent être utilisées aux fins suivantes :

* Suivi de plusieurs sites/domaines
* Utilisation de n’importe quelle devise pour les achats
* Collecte de données sans tenir compte de la langue
* Suivi des liens (nombre de fichiers téléchargés, liens vers des sites externes)
* Suivi des liens personnalisés à des fins uniques

>[!NOTE]
>
>[!DNL AppMeasurement] exige que toutes les variables de configuration soient définies avant l’appel initial à la fonction track `t()`. Si des variables de configuration sont définies après l’appel à `t()`, des résultats inattendus peuvent se produire. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

Pour obtenir de l’aide sur des variables de configuration spécifiques, consultez les liens suivants :

* [s_account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Spécifiez la suite de rapports dans laquelle les données sont stockées et signalées.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Sélectionnez dynamiquement la suite de rapports en fonction de l’URL de chaque page.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Spécifiez les règles utilisées pour déterminer la suite de rapports de destination.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Use the DOM object to retrieve the section of the URL to which all rules are applied.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Déployez le marquage pour les variables renseignées de manière dynamique.

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Convertissez les données entrantes au format UTF-8 pour le stockage et la création de rapports par Analytics.

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Déterminez le taux de conversion à appliquer aux recettes.

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Détermine le domaine dans lequel les `s_cc` cookies et `s_sq` les cookies sont définis.

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Déterminez le domaine pour `s_cc` et les `s_sq` cookies en spécifiant le nombre de points contenus dans le domaine de l’URL de la page.

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Spécifiez les cookies définis par JavaScript (`s_sq`, `s_cc`, plug-ins) qui sont intrinsèquement des cookies propriétaires, même avec des domaines tiers `2o7.net` ou `omtrdc.net` .

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Déterminer la durée de vie d’un cookie tel qu’il est traité par les serveurs de collecte de données et JavaScript.

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Référez-vous à la fonction et autorisez-la à être appelée à l’emplacement approprié dans le fichier JavaScript.

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Fonction permettant de prendre comme paramètres à la fois le rappel (une fonction) et les paramètres de cette fonction.

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Fonction permettant de prendre comme paramètres à la fois le rappel (une fonction) et les paramètres de cette fonction.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Effectuez le suivi des liens vers des fichiers téléchargeables de votre site.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Déterminez si un lien sur lequel l’utilisateur a cliqué est un lien de sortie.

* [strackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Déterminez si les données ClickMap sont collectées.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Incluez une liste d’extensions de fichiers séparées par des virgules.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Inclut une liste de filtres séparés par des virgules qui représentent les liens qui font partie du site.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determine whether or not the query string should be included in the Exit Links and File Download reports.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Incluez une liste de variables séparées par des virgules qui sont envoyées avec des liens personnalisés, de sortie et de téléchargement.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Permet de créer des rapports sur un sous-ensemble spécifique de liens de sortie.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Appelez la `s_doPlugins` fonction avant chaque demande d’image.

