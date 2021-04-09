---
description: Découvrez les directives et les recommandations concernant le consentement des utilisateurs quant au stockage ou à la lecture de cookies non essentiels sur des appareils ou des navigateurs.
title: Quelles sont les directives de la CNIL concernant le consentement des utilisateurs et les cookies ?
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
translation-type: tm+mt
source-git-commit: 0e09f6ee34560ca7f036e8f3fb743c822d5fcfc4
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 90%

---

# Exemption de consentement de la CNIL

Le 1er octobre 2020, l’autorité française de protection des données (la « CNIL ») a publié une version révisée de ses directives en matière de cookies (les « Directives »), ainsi que ses recommandations finales sur l’obtention du consentement des utilisateurs quant au stockage ou à la lecture de cookies non essentiels et de technologies similaires sur leurs appareils ou navigateurs (la « Recommandation »).

Les Directives fournissent une exemption limitée à l’exigence de consentement (« Exemption de consentement »). L’Exemption de consentement s’applique aux cookies d’analyse dont le but est limité à mesurer l’audience du site ou de l’application uniquement pour le compte de l’éditeur web. Les Directives prévoient que les conditions suivantes doivent être mises en œuvre pour que l’exemption de consentement s’applique :

* Période de rétention des données maximale de 25 mois.  Vous pouvez consulter vos paramètres actuels de rétention des données sous Analytics > Admin > Gouvernance des données.  [Rétention des données](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=fr)
* Désactivez les cookies tiers suivants dans ECID. [disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=fr#id-service-api), [disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=fr#id-service-api) et [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=fr#id-service-api).
* Limite des cookies de 13 mois. Vous pouvez remplacer l’expiration de vos cookies d’analyse à l’aide de la variable `cookieLifetime`.  Les cookies Experience Cloud, y compris Analytics et ECID, étendent la date d’expiration des cookies à chaque visite.  Pour définir une expiration de cookie statique non variable, vous pouvez effectuer l’une des opérations suivantes : (1) écrire du code personnalisé pour définir la date à laquelle supprimer le cookie, ou (2) utiliser votre CMP pour contrôler la date de réinitialisation du cookie.   [Cookies ](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=fr) cookieLifetimeet  [Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=en#ec-cookies)
* Portée limitée. La portée du cookie doit être limitée à un seul site ou une seule application. [Cookies de navigateur](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=fr&quot;\l&quot;third-party-cookie-implementations)
* Anonymisation. Anonymisation du dernier octet de l’adresse IP. [Paramètres généraux du compte](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=fr)
* Masquez l’ID du visiteur du rapport.  Par défaut, les ID de visiteurs ne sont pas visibles dans Adobe Workspace ni dans Adobe Reports and Analytics.  Les ID de visiteur sont disponibles dans les flux de données et dans Data Warehouse.  L’accès aux flux de données et à Data Warehouse peut être limité par les [autorisations d’accès dans l’Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr&quot;\l&quot;task_040673FE3E3E429B9531FBCB8B6A4391) et la [Référence des colonnes de flux de données](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=fr#columns%2C-descriptions%2C-and-data-types).
* Paramètres de géolocalisation. La niveau de géolocalisation ne peut pas être plus précis que le code postal. [Option ZIP](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=fr&quot;\l&quot;zip-in-adobe-experience-platform-launch) et [paramètres généraux du compte](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=fr&quot;\l&quot;admin-tools)
* Définissez les options Opt-in.  Le service Opt-in vous permet de configurer des protocoles afin de déterminer si vous pouvez définir un cookie sur l’appareil ou le navigateur de l’utilisateur lorsqu’il visite votre site. [Service Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=fr)
* Empêchez le partage de données.  Pour empêcher le partage des données avec Adobe Audience Manager, utilisez la variable de contexte `opt.dmp` pour que les [Rapports de confidentialité](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=fr&quot;\l&quot;variables) bloquent le partage des accès.
* Capacité d’accès et de suppression. Utilisez Privacy Service pour les demandes d’accès et de suppression. [Analytics et Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=fr)

## Considérations supplémentaires relatives à la collecte de données

Il convient également de tenir compte des considérations suivantes :

* Envisagez de collecter le statut de consentement dans une variable Analytics afin de séparer les données que lʼutilisateur accepte/refuse de partager pour la segmentation, les suites de rapports virtuelles ou pour les acheminer vers des points de terminaison distincts.
* Aucune mesure en dehors du site ou de l’application sans consentement préalable ; par exemple aucune campagne hors site, campagne par e-mail ni iFrame.
* La collecte d’informations personnelles dans des variables n’est pas autorisée sans le consentement de l’intéressé. [Contrôler les activités Experience Cloud en fonction du consentement de l’utilisateur](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html?lang=fr&quot;\l&quot;implementation#implementation)
* Les données ne peuvent être utilisées que pour la production de statistiques anonymes, sans être combinées avec d’autres données.
* Les données ne sont pas utilisées pour les actions de référence croisée.
* Les données de géolocalisation par GPS ne sont pas collectées.
* Lorsque lʼutilisateur final a donné son consentement, les paramètres ci-dessus peuvent être modifiés et les restrictions assouplies.

Pour plus d’informations, consultez le site web sur l’[exemption de cookies de la CNIL](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).
