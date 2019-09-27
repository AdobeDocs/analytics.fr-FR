---
description: Configuration variables set in AppMeasurement.js.
keywords: Mise en œuvre d’Analytics
seo-description: Variables de configuration définies dans AppMeasurement.js pour Adobe Analytics
seo-title: Variables de configuration
solution: Analytics
subtopic: Variables
title: Variables de configuration
topic: Développeur et mise en œuvre
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: a340bb50ec437db64dafaddc0b20aec740aee299

---


# Présentation des variables de configuration

Les variables de configuration contrôlent le mode de collecte et de traitement des données dans les rapports. The most-common configuration variables that are typically set in the main global JavaScript AppMeasurement.js). Ces variables peuvent être définies dans le code de niveau page et les liens Analytics, le cas échéant.

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

Pour obtenir de l’aide sur des variables de configuration spécifiques, cliquez sur l’un des liens suivants :

* [s.account: Specify the report suite where data is stored and reported.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html): Sélectionnez dynamiquement la suite de rapports en fonction de l’URL de chaque page.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html): Spécifiez les règles utilisées pour déterminer la suite de rapports de destination.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html): Utilisez l’objet DOM pour récupérer la section de l’URL à laquelle s’appliquent toutes les règles.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html): Déployez le marquage pour les variables renseignées de manière dynamique.

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html): Convertissez les données entrantes au format UTF-8 pour le stockage et la création de rapports par Analytics.

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html): Déterminez le taux de conversion à appliquer aux recettes.

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html): Détermine le domaine dans lequel les `s_cc` cookies et `s_sq` les cookies sont définis.

* [s.cookieDomainPeriods: Determine the domain for  and  cookies by specifying the number of periods in the domain of the page URL.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html)`s_cc``s_sq`

* [s.fpCookieDomainPeriods: Specify cookies set by JavaScript (, , plug-ins) that are inherently first-party cookies, even with third-party  or  domains.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html)`s_sq``s_cc``2o7.net``omtrdc.net`

* [s.cookieLifetime: Determine lifespan of a cookie as processed by both JavaScript and data collection servers.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html)

* [s.doPlugins: Refer and allow the function to be called at the appropriate location within the JavaScript file.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html)

* [s.registerPreTrackCallback: Function for taking as parameters both the callback (a function), and the parameters to that function.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html)

* [s.registerPostTrackCallback: Function for taking as parameters both the callback (a function), and the parameters to that function.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html)

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html): Effectuez le suivi des liens vers des fichiers téléchargeables de votre site.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html): Déterminez si un lien sur lequel l’utilisateur a cliqué est un lien de sortie.

* [s.trackInlineStats: Determine whether ClickMap data is gathered.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html)

* [s.linkDownloadFileTypes: Include a comma-separated list of file extensions.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html)

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkintfilters.html): Inclut une liste de filtres séparés par des virgules qui représentent les liens qui font partie du site.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html): Déterminez si la chaîne de requête doit être incluse dans les rapports Liens de sortie et Téléchargements de fichiers.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html): Incluez une liste de variables séparées par des virgules qui sont envoyées avec des liens personnalisés, de sortie et de téléchargement.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html): Permet de créer des rapports sur un sous-ensemble spécifique de liens de sortie.

* [s.usePlugins: Call the  function prior to each image request.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html)`s_doPlugins`

