---
description: Découvrez les directives et les recommandations concernant le consentement des utilisateurs à stocker ou lire des cookies non essentiels sur des périphériques ou des navigateurs.
title: Quelles sont les directives CNIL concernant le consentement de l'utilisateur et les cookies ?
translation-type: tm+mt
source-git-commit: c5ebc92622e012699d64c27701b24a88429e9f4f
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---


# Exonération du consentement CNIL

Le 1er octobre 2020, l’Autorité française de protection des données (la &quot;CNIL&quot;) a publié une version révisée de ses directives sur les cookies (les &quot;Lignes directrices&quot;) et de ses recommandations finales sur l’obtention du consentement des utilisateurs pour stocker ou lire des cookies non essentiels et des technologies similaires sur les appareils ou navigateurs des utilisateurs (la &quot;Recommendations&quot;).

Les Lignes directrices prévoient une exemption limitée à l&#39;exigence de consentement (&quot;Exonération de consentement&quot;). L’exemption de consentement s’applique aux cookies d’analyse dont le but est limité à mesurer l’audience du site ou de l’application uniquement pour le compte de l’éditeur Web. Les lignes directrices prévoient que pour que l&#39;exemption de consentement s&#39;applique, les conditions suivantes doivent être mises en oeuvre :

* 25 mois maximum de rétention des données.  Vous pouvez consulter vos paramètres actuels de rétention des données sous Analytics > Admin > Gouvernance des données.  [Rétention des données](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* Limite des cookies de 13 mois.  Vous pouvez remplacer l’expiration de vos cookies d’analyse à l’aide de la variable `cookieLifetime`.  [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html)
* Portée limitée. La portée du cookie doit être limitée à un seul site ou à une seule application. [Cookies de navigateur](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=en&quot;\l&quot;implémentations de cookies tiers)
* Anonymisation. Anonyme du dernier octet de l’adresse IP. [Paramètres du compte général](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* Masquer l’ID de visiteur du rapports.  Par défaut, les ID de visiteur ne sont pas visibles dans Adobe Workspace et dans Adobe Reports and Analytics.  Les ID de visiteur sont disponibles dans les flux de données et les Data Warehouse.  L’accès aux flux de données et aux Data Warehouse peut être limité par [les autorisations d’accès dans le Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en&quot;\l&quot;tâche_040673FE3E3E429B9531FBCB8B6A4391)
* Paramètres de géolocalisation. La géolocalisation ne peut pas être plus précise que le niveau de code postal. [Options ](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en&quot;\l&quot;zip-in-adobe-experience-platform-launch) de zip et paramètres  [généraux du compte](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=en&quot;\l&quot;admin-tools)
* Définissez les options d’inclusion.  Le service d’inclusion vous permet de définir des protocoles visiteurs pour déterminer si vous pouvez définir un cookie sur le périphérique ou le navigateur de l’utilisateur lors de sa visite sur votre site. [Service d’inscription](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* Empêcher le partage de données.  Pour empêcher le partage des données avec Adobe Audience Manager, utilisez la variable de contexte `opt.dmp` pour [Rapports de confidentialité](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=en&quot;\l&quot;variables) afin de bloquer le partage des accès.
* Possibilité d&#39;accéder et de supprimer. Utilisez le Privacy Service pour les demandes d’accès et de suppression. [Analytics et Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## Considérations supplémentaires relatives à la collecte de données

Les considérations supplémentaires suivantes s’appliquent :

* Aucune mesure en dehors du site ou de l’application sans le consentement préalable, par exemple aucune campagne hors site, campagne par courriel ou iFrames.
* La collecte de renseignements personnels dans des variables n&#39;est pas autorisée sans le consentement de l&#39;intéressé.
* Les données ne peuvent être utilisées que pour produire des statistiques anonymes, sans combinaison avec d&#39;autres données.
* Les données ne sont pas utilisées pour les actions de référence croisée.
* Les données de géolocalisation GPS ne sont pas collectées.

Pour plus d&#39;informations, consultez le [site Web CNIL Cookie Exemption](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).
