---
description: Vue d’ensemble des données collectées par Adobe Analytics et autres considérations sur la confidentialité.
keywords: confidentialité
title: Confidentialité - Présentation
feature: Data Governance
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 98%

---

# Confidentialité - Présentation

Adobe souhaite permettre à votre organisation de se conformer aux lois et réglementations en vigueur. Consultez [Confidentialité de Adobe Experience Cloud](https://www.adobe.com/fr/privacy/experience-cloud.html){target=_blank} pour plus d’informations. Entre Adobe Analytics et votre organisation, Adobe agit en tant que « responsable du traitement des données ». Votre organisation a le rôle de « sous-traitant des données » (ou équivalent, en vertu des lois applicables en matière de confidentialité et de protection des données). Il appartient à votre organisation de révéler comment vous utilisez les produits et services d’Adobe, car elle contrôle exclusivement l’implémentation des solutions Adobe. Lors de l’utilisation d’Adobe Analytics, votre organisation est responsable du respect de votre propre politique de confidentialité, de votre contrat de service avec Adobe et de toutes les lois applicables.

Adobe recommande vivement de respecter les principes fondamentaux suivants :

* **Si vous collectez des données personnelles, veillez à respecter les lois et règlements en matière de protection de la vie privée.** Les variables personnalisées vous permettent de collecter pratiquement tout ce à quoi vous pouvez accéder. Toutefois, vous devez également tenir compte de la politique de confidentialité de votre organisation et des lois applicables.
* **Fournissez à votre clientèle des informations faciles à trouver et à comprendre sur la protection de la vie privée au sein de votre organisation.** Les informations utiles comprennent des liens d’opt-out, la manière dont les données de navigation sont utilisées et la manière dont vous utilisez ou prévoyez d’utiliser les services Adobe.
* **Tenez-vous au courant des lois locales et internationales qui s’appliquent à vous.** Si votre organisation opère à l’échelle mondiale, certaines lois internationales peuvent s’appliquer.

## Répartition de la collecte des données

Adobe propose plusieurs bibliothèques de collecte de données pour faciliter l’envoi de données à Adobe. Exemples notables :

* **AppMeasurement** : bibliothèque conçue pour envoyer des données directement à Adobe Analytics.
* **SDK Web** : bibliothèque conçue pour envoyer des données au réseau Edge d’Adobe Experience Platform, qui les transmet alors à Adobe Analytics.
* **Balises** : interface web qui vous permet de configurer votre implémentation sans avoir besoin d’accéder au code source d’un site web ou d’une application au-delà de l’implémentation initiale de la balise. Des extensions sont disponibles pour AppMeasurement et le SDK Web.

Adobe Analytics peut collecter les types de données suivants :

| Type de données | Détails | Exemples de variables contenant ces données |
| --- | --- | --- |
| Noms de page ou URL des pages web de votre site | Ces données sont nécessaires au fonctionnement d’Adobe Analytics. Une URL ou un nom de page est nécessaire pour chaque accès. | [Page](/help/components/dimensions/page.md), [URL de page](/help/components/dimensions/page-url.md) |
| Données temporelles | Ces données sont nécessaires au fonctionnement d’Adobe Analytics. Un horodatage est nécessaire pour la collecte des données. Les données temporelles sont dérivées de l’horodatage. | [Durée de consultation de la page](/help/components/dimensions/time-spent-on-page.md), [Heure du jour](/help/components/dimensions/hour-of-day.md), [AM/PM](/help/components/dimensions/am-pm.md), [Jour de la semaine/week-end](/help/components/dimensions/weekday-weekend.md), [Jour de la semaine](/help/components/dimensions/day-of-week.md), [Mois de l’année](/help/components/dimensions/month-of-year.md) |
| Données référentes | Les bibliothèques de collecte de données collectent par défaut l’URL référente lorsqu’une personne arrive sur votre site web. Vous pouvez personnaliser votre mise en œuvre pour collecter des données dans la chaîne de requête d’une personne référente. Cette pratique est courante pour les campagnes et le suivi de la performance publicitaire. | [Personne référente](/help/components/dimensions/referrer.md), [Domaine référent](/help/components/dimensions/referring-domain.md) |
| Identifiants anonymes des visiteurs et visiteuses | Les bibliothèques de collecte de données génèrent et référencent un identifiant de visiteur ou de visiteuse pour chaque navigateur accédant à votre site. Cet ID est stocké dans un cookie. Si une bibliothèque de collecte de données ne peut pas définir un identifiant de cookie, elle utilise une méthode de secours pour l’identification des visiteurs et visiteuses anonymes. Cette méthode consiste à relier des résultats connexes à la même visite en utilisant l’adresse IP de la personne et la chaîne de l’agent utilisateur. Si votre organisation a activé l’obscurcissement d’IP, ce paramètre est respecté. Voir [Adobe Analytics et les cookies de navigateur](../cookies/cookies.md) pour plus d’informations. | [Visiteurs et visiteuses uniques](/help/components/metrics/unique-visitors.md) |
| Identifiant visible des visiteurs et visiteuses | Adobe ne collecte pas automatiquement les identifiants personnalisés des visiteurs et visiteuses. Cependant, vous pouvez personnaliser votre implémentation pour collecter ces données. | [`visitorID`](/help/implement/vars/config-vars/visitorid.md) |
| Termes de recherche externe | Les données de recherche externe comprennent les mots-clés provenant des moteurs de recherche. Les bibliothèques de collecte de données recherchent ces données sur la base de l’URL référente. Cependant, de nombreux moteurs de recherche modernes n’incluent plus ces informations. | [Mot-clé de recherche](/help/components/dimensions/search-keyword.md) |
| Termes de recherche internes | Les données de recherche interne comprennent les mots-clés qui proviennent des capacités de recherche de votre site web ou de votre application. Adobe ne collecte pas automatiquement les données de recherche interne. Cependant, vous pouvez personnaliser votre implémentation pour collecter ces données. Cette pratique est courante dans les organisations qui utilisent Adobe Analytics. | [eVar](/help/components/dimensions/evar.md) |
| Spécifications de l’ordinateur et du navigateur | Les bibliothèques de collecte de données recueillent automatiquement des indices de navigation à faible entropie, tels que le type de navigateur, le type de système d’exploitation et le fait que l’appareil soit un ordinateur de bureau ou un appareil mobile. Une configuration personnalisée est nécessaire pour collecter des indices à forte entropie, tels que la version/le build spécifique du navigateur, le modèle de l’appareil ou la version du système d’exploitation. Pour plus d’informations, consultez la [vue d’ensemble des indications de la clientèle](../client-hints.md). | [Navigateur](/help/components/dimensions/browser.md), [Système d’exploitation](/help/components/dimensions/operating-systems.md), [Dimensions du mobile](/help/components/dimensions/mobile-dimensions.md), [Résolution du moniteur](/help/components/dimensions/monitor-resolution.md) |
| Informations sur la géolocalisation | Adobe offre la possibilité d’empêcher la géolocalisation détaillée en fixant le dernier octet d’une adresse IP à 0. Cela rend les informations géographiques moins précises et peut être réglé dans les [paramètres de la suite de rapports](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md). | [Villes](/help/components/dimensions/cities.md), [Régions](/help/components/dimensions/regions.md), [Pays](/help/components/dimensions/countries.md) |
| Adresse IP | Adobe offre la possibilité d’obscurcir (hacher) ou de supprimer totalement l’adresse IP du visiteur ou de la visiteuse lors du stockage de ces données. Pour la clientèle de la zone EMEA, le paramètre de l’adresse IP est généralement obscurci par défaut. Quel que soit le paramètre d’obscurcissement, l’adresse IP n’est pas disponible en tant que dimension dans l’espace de travail d’analyse. Elle n’est incluse que dans les [flux de données](/help/export/analytics-data-feed/data-feed-overview.md). Voir [Paramètres généraux du compte](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) dans le guide d’administration pour plus de détails sur les paramètres d’obscurcissement disponibles. | Aucun |
| Formulaire d’information fourni sur votre site | Tous les types d’implémentation nécessitent une configuration pour collecter ces données. Vous pouvez inclure ces données dans des variables personnalisées. | [eVar](/help/components/dimensions/evar.md) |
| Publicités ou liens de votre site sur lesquels des personnes ont cliqué | Collectés si [`trackExternalLinks`](/help/implement/vars/config-vars/trackexternallinks.md) ou [`trackDownloadLinks`](/help/implement/vars/config-vars/trackdownloadlinks.md) est activé. Des informations supplémentaires, telles que l’emplacement des clics, sont disponibles lorsque vous activez l’Activity Map. | [Activity Map](/help/analyze/activity-map/overview.md), [Lien de sortie](/help/components/dimensions/exit-link.md), [Lien de téléchargement](/help/components/dimensions/download-link.md) |
| Produits achetés sur votre site | Tous les types d’implémentation nécessitent une configuration pour collecter ces données. Adobe propose plusieurs variables par défaut pour collecter ces informations. | [Produit](/help/components/dimensions/product.md), [Commandes](/help/components/metrics/orders.md), [Revenu](/help/components/metrics/revenue.md) |

{style="table-layout:auto"}

Voir le menu de navigation sous [Vue d’ensemble des dimensions](/help/components/dimensions/overview.md) et [Vue d’ensemble des mesures](/help/components/metrics/overview.md) pour d’autres variables pour lesquelles Adobe peut potentiellement collecter des données.

## Emplacements de traitement des données

Adobe dispose de trois emplacements de traitement des données pour Adobe Analytics. Ces sites reçoivent des données brutes et les traitent dans une suite de rapports, qui est optimisée pour le stockage des données et la récupération des rapports. Ces emplacements de traitement des données se trouvent actuellement aux États-Unis (Oregon), au Royaume-Uni (Londres) et à Singapour. Voir [Présentation de la sécurité d’Adobe Analytics](https://www.adobe.com/content/dam/cc/fr/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf){target=_blank} pour plus d’informations.
