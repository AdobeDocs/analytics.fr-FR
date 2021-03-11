---
description: Découvrez les directives et les recommandations concernant le consentement des utilisateurs quant au stockage ou à la lecture de cookies non essentiels sur des appareils ou des navigateurs.
title: Quelles sont les directives de la CNIL concernant le consentement des utilisateurs et les cookies ?
translation-type: tm+mt
source-git-commit: 36259e3a36cad221d7264e5caa0a09a757dc4fe8
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 83%

---


# Exemption de consentement de la CNIL

Le 1er octobre 2020, l’autorité française de protection des données (la « CNIL ») a publié une version révisée de ses directives en matière de cookies (les « Directives »), ainsi que ses recommandations finales sur l’obtention du consentement des utilisateurs quant au stockage ou à la lecture de cookies non essentiels et de technologies similaires sur leurs appareils ou navigateurs (la « Recommandation »).

Les Directives fournissent une exemption limitée à l’exigence de consentement (« Exemption de consentement »). L’Exemption de consentement s’applique aux cookies d’analyse dont le but est limité à mesurer l’audience du site ou de l’application uniquement pour le compte de l’éditeur web. Les Directives prévoient que les conditions suivantes doivent être mises en œuvre pour que l’exemption de consentement s’applique :

* Période de rétention des données maximale de 25 mois. Vous pouvez consulter vos paramètres actuels de rétention des données sous Analytics > Admin > Gouvernance des données. [Rétention des données](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=fr)
* Désactivez les cookies tiers dans ECID. [disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=en#id-service-api),  [disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=en#id-service-api) et  [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=en#id-service-api)
* La limite des cookies de 13 mois est définie sur une date statique et non variable.  Vous pouvez remplacer l’expiration de vos cookies d’analyse à l’aide de la variable `cookieLifetime`. [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=fr)
* Portée limitée. La portée du cookie doit être limitée à un seul site ou une seule application. [Cookies de navigateur](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=fr&quot;\l&quot;third-party-cookie-implementations)
* Anonymisation. Anonymisation du dernier octet de l’adresse IP. [Paramètres généraux du compte](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=fr)
* Masquez l’ID du visiteur du rapport. Par défaut, les ID de visiteurs ne sont pas visibles dans Adobe Workspace ni dans Adobe Reports and Analytics. Les ID de visiteur sont disponibles dans les flux de données et dans Data Warehouse. L’accès aux flux de données et à Data Warehouse peut être limité par les [autorisations d’accès dans l’Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr&quot;\l&quot;task_040673FE3E3E429B9531FBCB8B6A4391)
* Paramètres de géolocalisation. La niveau de géolocalisation ne peut pas être plus précis que le code postal. [Option ZIP](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=fr&quot;\l&quot;zip-in-adobe-experience-platform-launch) et [paramètres généraux du compte](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=fr&quot;\l&quot;admin-tools)
* Définissez les options Opt-in. Le service Opt-in vous permet de configurer des protocoles afin de déterminer si vous pouvez définir un cookie sur l’appareil ou le navigateur de l’utilisateur lorsqu’il visite votre site. [Service Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=fr)
* Empêchez le partage de données. Pour empêcher le partage des données avec Adobe Audience Manager, utilisez la variable de contexte `opt.dmp` pour que les [Rapports de confidentialité](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=fr&quot;\l&quot;variables) bloquent le partage des accès.
* Capacité d’accès et de suppression. Utilisez Privacy Service pour les demandes d’accès et de suppression. [Analytics et Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=fr)

## Considérations supplémentaires relatives à la collecte de données

Il convient également de tenir compte des considérations suivantes :

* Envisagez de collecter l’état d’inclusion dans une variable Analytics afin de séparer les données d’inclusion des données d’exclusion pour la segmentation, les suites de rapports virtuelles ou d’acheminer vers des points de terminaison distincts.
* Aucune mesure en dehors du site ou de l’application sans consentement préalable ; par exemple aucune campagne hors site, campagne par e-mail ni iFrame.
* La collecte d’informations personnelles dans des variables n’est pas autorisée sans le consentement de l’intéressé.
* Les données ne peuvent être utilisées que pour la production de statistiques anonymes, sans être combinées avec d’autres données.
* Les données ne sont pas utilisées pour les actions de référence croisée.
* Les données de géolocalisation par GPS ne sont pas collectées.
* Lorsque l&#39;utilisateur final a donné son consentement, les paramètres ci-dessus peuvent être modifiés et les restrictions assouplies.

Pour plus d’informations, consultez le site web sur l’[exemption de cookies de la CNIL](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).
