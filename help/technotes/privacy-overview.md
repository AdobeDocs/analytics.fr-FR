---
description: Vue d’ensemble des données collectées par Adobe Analytics et autres considérations sur la confidentialité.
keywords: confidentialité
title: Confidentialité - Présentation
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: 04f8602ccfa7fd2d1d2f3c56f477aeee3739c563
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 3%

---

# Confidentialité - Présentation

Adobe souhaite permettre à votre organisation de se conformer aux lois et règlements en vigueur sur la protection des données. Voir [Confidentialité de Adobe Experience Cloud](https://www.adobe.com/fr/privacy/experience-cloud.html) pour plus d’informations. En ce qui concerne Adobe Analytics, Adobe agit comme un &quot;responsable du traitement des données&quot; et vous êtes le &quot;contrôleur des données&quot; (ou l’équivalent en vertu des lois applicables sur la protection de la vie privée et des données). C’est à votre organisation de révéler comment vous utilisez les produits et services d’Adobe, car votre organisation contrôle exclusivement la mise en oeuvre des solutions d’Adobe. Votre entreprise est responsable du respect de votre propre politique de confidentialité, de votre contrat de service avec l’Adobe et de toutes les lois applicables.

Adobe recommande vivement de respecter les concepts généraux suivants :

* **Si vous collectez des données personnelles, veillez à respecter les lois et réglementations relatives à la confidentialité.** Les variables personnalisées vous permettent de collecter pratiquement tout ce à quoi vous avez accès. Cependant, vous devez également tenir compte de la politique de confidentialité de votre entreprise et des lois applicables.
* **Fournissez à vos clients des informations de confidentialité faciles à trouver et à comprendre pour votre entreprise.** Ces informations utiles comprennent les liens d’exclusion, la manière dont leurs données de navigation sont utilisées et la manière dont vous utilisez ou envisagez d’utiliser les services d’Adobe.
* **Ayez conscience des lois locales et des lois internationales qui s&#39;appliquent à vous.** Si votre organisation opère à l’échelle mondiale, certaines lois internationales peuvent s’appliquer.

## Ventilation des collections de données

Adobe propose plusieurs bibliothèques de collecte de données pour faciliter l’envoi de données à Adobe. Voici quelques exemples notables :

* **AppMeasurement**: bibliothèque conçue pour envoyer des données directement à Adobe Analytics.
* **SDK Web**: bibliothèque conçue pour envoyer des données au réseau Adobe Experience Platform Edge, qui les transfère ensuite vers Adobe Analytics.
* **Balises**: interface utilisateur web qui vous permet de configurer votre mise en oeuvre sans avoir à accéder au code source d’un site web ou d’une application au-delà de la mise en oeuvre initiale des balises. Les extensions sont disponibles pour AppMeasurement et pour le SDK Web.

Adobe Analytics peut collecter les types de données suivants :

| Type de données | Détails | Exemples de variables contenant ces données |
| --- | --- | --- |
| Noms ou adresses URL des pages web de votre site | Toujours collectée pour qu’Adobe Analytics fonctionne. Une URL ou un nom de page est requis pour chaque accès. | [Page](../components/dimensions/page.md), [URL de la page](../components/dimensions/page-url.md) |
| Données temporelles | Toujours collectée pour qu’Adobe Analytics fonctionne. Un horodatage est requis pour la collecte des données et des données temporelles sont dérivées de l’horodatage. | [Durée de consultation de la page](../components/dimensions/time-spent-on-page.md), [Heure de la journée](../components/dimensions/hour-of-day.md), [Matin/après-midi](../components/dimensions/am-pm.md), [Jour ouvrable/week-end](../components/dimensions/weekday-weekend.md), [Jour de la semaine](../components/dimensions/day-of-week.md), [Mois de l’année](../components/dimensions/month-of-year.md) |
| Données des pages web d’autres sites | Adobe ne peut pas collecter de données sur des sites non affiliés où vous ne pouvez pas modifier le code source du site web ou de l’application. Les bibliothèques de collecte de données collectent l’URL de référence par défaut lorsqu’un visiteur arrive sur votre site web. Vous pouvez personnaliser votre mise en oeuvre afin de collecter des données dans des chaînes de requête une fois les visiteurs du site web ou de l’application arrivés. | [Référent](../components/dimensions/referrer.md), [Domaine référent](../components/dimensions/referring-domain.md) |
| Identifiants visiteur anonymes | Les bibliothèques de collecte de données génèrent et référencent un identifiant visiteur pour chaque navigateur qui visite votre site. Cet identifiant est stocké dans un cookie. Si une bibliothèque de collecte de données ne peut pas définir de cookies pour une raison quelconque, elle utilise une méthode de secours pour l’identification des visiteurs à l’aide de l’adresse IP et de la chaîne de l’agent utilisateur. Voir [Cookies Adobe Analytics et de navigateur](cookies/cookies.md) pour plus d’informations. | [Visiteurs uniques](../components/metrics/unique-visitors.md) |
| Identifiants visiteur identifiables | Adobe ne collecte pas automatiquement les identifiants visiteur personnalisés. Cependant, vous pouvez personnaliser votre implémentation pour collecter ces données. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| Termes de recherche externes | Les données de recherche externe incluent les mots-clés issus des moteurs de recherche. Les bibliothèques de collecte de données recherchent ces données en fonction de l’URL de référence. Cependant, de nombreux moteurs de recherche modernes n’incluent plus cette information. | [Mot-clé de recherche](../components/dimensions/search-keyword.md) |
| Termes de recherche internes | Les données de recherche interne incluent des mots-clés issus des fonctionnalités de recherche de votre site web ou de votre application. Adobe ne collecte pas automatiquement les données de recherche interne. Cependant, vous pouvez personnaliser votre implémentation pour collecter ces données. Cette pratique est courante pour les organisations qui utilisent Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Spécifications de l’ordinateur et du navigateur | AppMeasurement collecte automatiquement les indices de navigateur à faible entropie, tels que le type de navigateur, le type de système d’exploitation et si l’appareil est de bureau ou mobile. Une configuration personnalisée est requise pour collecter des indices à forte entropie, tels que la version/version spécifique du navigateur, le modèle de périphérique ou la version du système d’exploitation. Voir [Présentation des conseils client](client-hints.md) pour plus d’informations. | [Navigateur](../components/dimensions/browser.md), [Système d’exploitation](../components/dimensions/operating-systems.md), [Dimensions mobiles](../components/dimensions/mobile-dimensions.md), [Résolution de l’écran](../components/dimensions/monitor-resolution.md) |
| Informations de géolocalisation | Adobe offre la possibilité d’activer ou de désactiver la collecte de données de géolocalisation pour chaque site web ou application (au niveau d’une suite de rapports). La collecte de données de géolocalisation est activée par défaut. Les bibliothèques de collecte de données incluent la géolocalisation si elle est activée. | [Villes](../components/dimensions/cities.md), [Régions](../components/dimensions/regions.md), [Pays](../components/dimensions/countries.md) |
| Adresse IP | Adobe offre la possibilité d’obscurcir le dernier octet ou d’obscurcir complètement l’adresse IP du visiteur lors du stockage de ces données. Les clients EMEA ont généralement le paramètre d’adresse IP entièrement obscurci par défaut. Quel que soit le paramètre d’obscurcissement, l’adresse IP n’est pas disponible en tant que dimension dans Adobe Analytics ; elle est uniquement incluse dans [Flux de données](../export/analytics-data-feed/data-feed-overview.md). | Aucun |
| Informations sur le formulaire fournies sur votre site | Tous les types d’implémentation nécessitent une configuration pour collecter ces données. Vous pouvez inclure ces données dans des variables personnalisées. | [eVar](../components/dimensions/evar.md) |
| Publicités ou liens cliqués sur votre site | Collecté par défaut lors de l’utilisation d’une bibliothèque de collecte de données. Des informations supplémentaires, telles que l’emplacement des clics, sont disponibles lorsque vous activez Activity Map. | [Activity Map](../analyze/activity-map/activity-map.md), [Lien de sortie](../components/dimensions/exit-link.md), [Lien de téléchargement](../components/dimensions/download-link.md) |
| Produits achetés sur votre site | Tous les types d’implémentation nécessitent une configuration pour collecter ces données. Adobe propose plusieurs variables par défaut pour collecter ces informations. | [Produit](../components/dimensions/product.md), [Commandes](../components/metrics/orders.md), [Recettes](../components/metrics/revenue.md) |

{style="table-layout:auto"}

Voir le menu de navigation sous [Présentation des Dimensions](../components/dimensions/overview.md) et [Présentation des mesures](../components/metrics/overview.md) pour d’autres variables sous lesquelles Adobe peut potentiellement collecter des données.

## Emplacements de traitement des données

Adobe conserve trois emplacements de traitement des données pour Adobe Analytics. Ces sites reçoivent des données brutes et les traitent dans une suite de rapports optimisée pour le stockage des données et la récupération des rapports. Ces emplacements de traitement de données résident dans **Oregon**, **Londres**, et **Singapour**. Voir [Présentation de la sécurité d’Adobe Analytics](https://www.adobe.com/content/dam/cc/en/trust-center/ungated/whitepapers/experience-cloud/adb-analytics-security-wp.pdf) pour plus d’informations.
