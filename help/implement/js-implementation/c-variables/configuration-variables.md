---
description: Variables de configuration définies dans le fichier AppMeasurement.js.
keywords: Mise en œuvre d’Analytics
seo-description: Variables de configuration définies dans le fichier AppMeasurement.js pour Adobe Analytics
seo-title: Variables de configuration
solution: Analytics
subtopic: Variables
title: Variables de configuration
topic: Développeur et mise en œuvre
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# Variables de configuration de la validation

Les variables de configuration contrôlent le mode de collecte et de traitement des données dans les rapports. Les variables de configuration les plus courantes sont généralement définies dans le fichier JavaScript global principal (AppMeasurement.js. Si nécessaire, ces variables peuvent être définies dans le code et les liens au niveau de la page d’Analytics.

Toutes ces variables n’apparaissent pas dans le code par défaut lorsque vous générez le code en sélectionnant **[!UICONTROL Outils d’administration]** &gt; **[!UICONTROL Gestionnaire de code]**. Certaines de ces variables de configuration peuvent ne pas s’appliquer aux besoins de mise en oeuvre de votre site.

Ces variables de configuration peuvent être utilisées aux fins suivantes :

* Suivi de plusieurs sites/domaines
* Utilisation de n’importe quelle devise pour les achats
* Collecte de données sans tenir compte de la langue
* Suivi des liens (nombre de fichiers téléchargés, liens vers des sites externes).
* Suivi des liens personnalisés à des fins uniques

> [!NOTE] [!DNL AppMeasurement] exige que toutes les variables de configuration soient définies avant l’appel initial vers la fonction de suivi, `t()`. Si des variables de configuration sont définies après l’appel à `t()`, des résultats inattendus peuvent se produire. Pour que la collecte des données se déroule correctement, toutes les variables de configuration doivent être définies au-dessus de la fonction `doPlugins`.

Pour obtenir de l’aide sur des variables de configuration spécifiques, cliquez sur l’un des liens suivants :

* [s.account](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html): Spécifiez la suite de rapports dans laquelle les données sont stockées et signalées.

* [s.dynamicAccountSelection](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccsel.html): Sélectionnez dynamiquement la suite de rapports en fonction de l’URL de chaque page.

* [s.dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynacclist.html): Spécifiez les règles utilisées pour déterminer la suite de rapports de destination.

* [s.dynamicAccountMatch](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynaccmatch.html): Utilisez l’objet DOM pour récupérer la section de l’URL à laquelle s’appliquent toutes les règles.

* [s.dynamicVariablePrefix](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-dynvarprefix.html): Déployez le marquage pour les variables renseignées de manière dynamique.

* [s.charSet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-charset.html): Convertissez les données entrantes au format UTF-8 pour le stockage et la création de rapports par Analytics.

* [s.currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-currcode.html): Déterminez le taux de conversion à appliquer aux recettes.

* [s.cookieDomain](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdom.html): Détermine le domaine dans lequel les `s_cc` cookies et `s_sq` les cookies sont définis.

* [s.cookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cookdomperiods.html): Déterminez le domaine pour `s_cc` et les `s_sq` cookies en spécifiant le nombre de points contenus dans le domaine de l’URL de la page.

* [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-fpcookdomperiods.html): Spécifiez les cookies définis par JavaScript (`s_sq`, `s_cc`, plug-ins) qui sont intrinsèquement des cookies propriétaires, même avec des domaines tiers `2o7.net` ou `omtrdc.net` .

* [s.cookieLifetime](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-cooklifetime.html): Déterminer la durée de vie d’un cookie tel qu’il est traité par les serveurs de collecte de données et JavaScript.

* [s.doPlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-doplugins.html): Référez-vous à la fonction et autorisez-la à être appelée à l’emplacement approprié dans le fichier JavaScript.

* [s.registerPreTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Fonction permettant de prendre comme paramètres à la fois le rappel (une fonction) et les paramètres de cette fonction.

* [s.registerPostTrackCallback](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-regpretrackcback.html): Fonction permettant de prendre comme paramètres à la fois le rappel (une fonction) et les paramètres de cette fonction.

* [s.trackDownLoadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackdnloadlinks.html): Effectuez le suivi des liens vers des fichiers téléchargeables de votre site.

* [s.trackExternalLinks](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackextlinks.html): Déterminez si un lien sur lequel l’utilisateur a cliqué est un lien de sortie.

* [s.trackInlineStats](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackinlinestats.html): Déterminez si les données ClickMap sont collectées.

* [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkdownldftype.html): Incluez une liste d’extensions de fichiers séparées par des virgules.

* [s.linkInternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-trackintfilters.html): Inclut une liste de filtres séparés par des virgules qui représentent les liens qui font partie du site.

* [s.linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linklvqrystring.html): Déterminez si la chaîne de requête doit être incluse dans les rapports Liens de sortie et Téléchargements de fichiers.

* [s.linkTrackVars](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html): Incluez une liste de variables séparées par des virgules qui sont envoyées avec des liens personnalisés, de sortie et de téléchargement.

* [s.linkExternalFilters](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linkextfilters.html): Permet de créer des rapports sur un sous-ensemble spécifique de liens de sortie.

* [s.usePlugins](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-useplugins.html): Appelez la `s_doPlugins` fonction avant chaque demande d’image.
