---
description: Variables de configuration définies dans AppMeasurement.js.
keywords: Mise en œuvre d’Analytics
seo-description: Configuration variables set in AppMeasurement.js for Adobe Analytics
seo-title: Variables de configuration
solution: Analytics
subtopic: Variables
title: Variables de configuration
topic: Développeur et mise en œuvre
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 9212d70ab8fd7bc0ccfb7e781a92b1731f0a40bd

---


# Configuration variables overview

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
>[!DNL AppMeasurement] exige que toutes les variables de configuration soient définies avant l’appel initial à la fonction track `t()`. If configuration variables are set after the call to `t()`, unexpected results may occur. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

For help with specific configuration variables, click any of the following links:

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Spécifiez la suite de rapports dans laquelle les données sont stockées et signalées.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Sélectionnez dynamiquement la suite de rapports en fonction de l’URL de chaque page.

* [s.dynamicAccountList: Specify the rules used for determining the destination report suite.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Utilisez l’objet DOM pour récupérer la section de l’URL à laquelle s’appliquent toutes les règles.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Deploy flagging for dynamically-populated variables.

* [s.charSet: Convert incoming data to UTF-8 for storage and reporting by Analytics.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.currencyCode: Determine the conversion rate to apply to revenue.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Determines which domain the `s_cc` and `s_sq` cookies are set.

* [s.cookieDomainPeriods: Determine the domain for  and  cookies by specifying the number of periods in the domain of the page URL.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)`s_cc``s_sq`

* [s.fpCookieDomainPeriods: Specify cookies set by JavaScript (, , plug-ins) that are inherently first-party cookies, even with third-party  or  domains.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)`s_sq``s_cc``2o7.net``omtrdc.net`

* [s.cookieLifetime: Determine lifespan of a cookie as processed by both JavaScript and data collection servers.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.doPlugins: Refer and allow the function to be called at the appropriate location within the JavaScript file.](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html)

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Fonction permettant de prendre comme paramètres à la fois le rappel (une fonction) et les paramètres de cette fonction.

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Fonction permettant de prendre comme paramètres à la fois le rappel (une fonction) et les paramètres de cette fonction.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Effectuez le suivi des liens vers des fichiers téléchargeables de votre site.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Déterminez si un lien sur lequel l’utilisateur a cliqué est un lien de sortie.

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Déterminez si les données ClickMap sont collectées.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Incluez une liste d’extensions de fichiers séparées par des virgules.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Inclut une liste de filtres séparés par des virgules qui représentent les liens qui font partie du site.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Déterminez si la chaîne de requête doit être incluse dans les rapports Liens de sortie et Téléchargements de fichiers.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Incluez une liste de variables séparées par des virgules qui sont envoyées avec des liens personnalisés, de sortie et de téléchargement.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Permet de créer des rapports sur un sous-ensemble spécifique de liens de sortie.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Appelez la `s_doPlugins` fonction avant chaque demande d’image.

