---
description: Vue d’ensemble des données collectées par Adobe Analytics et autres considérations sur la confidentialité.
keywords: confidentialité
title: Confidentialité - Présentation
feature: Privacy
exl-id: 71c83106-a047-47d7-9a70-4a24595e3d0a
source-git-commit: ee0bf5beeac3c9780eb0c8420845114f7e840aec
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 12%

---

# Confidentialité - Présentation

Les visiteurs peuvent en savoir plus sur la manière dont Adobe utilise généralement les informations collectées dans le [Centre de traitement des données personnelles d’Adobe](https://www.adobe.com/fr/privacy.html). Il appartient à votre entreprise de révéler comment vous utilisez les produits et services d’Adobe, car votre entreprise contrôle exclusivement la mise en œuvre des services d’Adobe. Votre entreprise est responsable du respect de votre propre politique de confidentialité, de votre contrat de service avec l’Adobe et de toutes les lois applicables.

Adobe recommande vivement de respecter les concepts généraux suivants :

* **Évitez de collecter des informations d’identification personnelle dans Adobe Analytics.** Les variables personnalisées vous permettent de collecter pratiquement tout ce à quoi vous avez accès. Cependant, vous devez également tenir compte de la politique de confidentialité de votre entreprise et des lois applicables.
* **Fournissez aux visiteurs des informations faciles à trouver et à comprendre concernant les informations d’exclusion.** Permettez-leur d&#39;exclure tout ce qui n&#39;est pas strictement nécessaire. La plupart des pays de l’Union européenne ne considèrent pas les cookies d’analyse comme strictement nécessaires.

## Ventilation des collections de données

Adobe Analytics collecte automatiquement ou peut potentiellement collecter les types de données suivants :

| Type de données | Détails | Exemples de variables contenant ces données |
| --- | --- | --- |
| Noms ou adresses URL des pages web de votre site | Toujours collectée. Une URL ou un nom de page est requis pour chaque accès. | [Page](../components/dimensions/page.md), [URL de la page](../components/dimensions/page-url.md) |
| Données temporelles | Toujours collectée. L’horodatage est requis pour la collecte des données et les données temporelles sont dérivées de l’horodatage. | [Durée de consultation de la page](../components/dimensions/time-spent-on-page.md), [Heure de la journée](../components/dimensions/hour-of-day.md), [Matin/après-midi](../components/dimensions/am-pm.md), [Jour ouvrable/week-end](../components/dimensions/weekday-weekend.md), [Jour de la semaine](../components/dimensions/day-of-week.md), [Mois de l’année](../components/dimensions/month-of-year.md) |
| Données des pages web d’autres sites | Adobe ne peut pas collecter de données sur des sites non affiliés où vous ne pouvez pas modifier le code source du site web. AppMeasurement collecte automatiquement l’URL de référence lorsqu’un visiteur arrive sur votre site web. Vous pouvez personnaliser votre mise en oeuvre pour collecter des données dans les chaînes de requête une fois qu’elles sont arrivées sur votre site. | [Référent](../components/dimensions/referrer.md), [Domaine référent](../components/dimensions/referring-domain.md) |
| Identifiants visiteur anonymes | AppMeasurement génère et référence automatiquement un identifiant visiteur pour chaque navigateur qui visite votre site. Cet identifiant est stocké dans un cookie. Si les cookies ne sont pas disponibles pour une mise en oeuvre donnée, Adobe Analytics utilise une méthode de secours pour l’identification des visiteurs à l’aide de l’adresse IP et de la chaîne de l’agent utilisateur. Voir [Cookies Adobe Analytics et de navigateur](cookies/cookies.md) pour plus d’informations. | [Visiteurs uniques](../components/metrics/unique-visitors.md) |
| Identifiants visiteur identifiables | Adobe ne collecte pas automatiquement les identifiants visiteur personnalisés. Cependant, vous pouvez personnaliser votre implémentation pour collecter ces données. | [`visitorID`](../implement/vars/config-vars/visitorid.md) |
| Termes de recherche externes | AppMeasurement tente de collecter automatiquement ces données en fonction de l’URL de référence. Cependant, de nombreux moteurs de recherche modernes n’incluent plus cette information. | [Mot-clé de recherche](../components/dimensions/search-keyword.md) |
| Termes de recherche internes | Adobe ne collecte pas automatiquement les données de recherche interne. Cependant, vous pouvez personnaliser votre mise en oeuvre pour collecter ces données. C’est une pratique courante pour les organisations qui utilisent Adobe Analytics. | [eVar](../components/dimensions/evar.md) |
| Spécifications de l’ordinateur et du navigateur | AppMeasurement collecte automatiquement les indices de navigateur à faible entropie, tels que le type de navigateur, le type de système d’exploitation et si l’appareil est de bureau ou mobile. La configuration est requise pour collecter des indices à forte entropie, tels que la version/version spécifique du navigateur, le modèle de périphérique ou la version du système d’exploitation. Voir [Présentation des conseils client](client-hints.md) pour plus d’informations. | [Navigateur](../components/dimensions/browser.md), [Système d’exploitation](../components/dimensions/operating-systems.md), [Dimensions mobiles](../components/dimensions/mobile-dimensions.md), [Résolution de l’écran](../components/dimensions/monitor-resolution.md) |
| Informations de géolocalisation | Adobe offre la possibilité d’activer ou de désactiver la collecte de données de géolocalisation pour chaque site web ou application (au niveau d’une suite de rapports). De nombreux types d’implémentation, y compris AppMeasurement, collectent automatiquement ces données. | [Villes](../components/dimensions/cities.md), [Régions](../components/dimensions/regions.md), [Pays](../components/dimensions/countries.md) |
| Adresse IP | Adobe permet d’obscurcir le dernier octet ou d’obscurcir complètement l’adresse IP du visiteur lors du stockage de ces données. Les clients EMEA ont généralement une adresse IP complètement masquée par défaut. L’adresse IP n’est pas disponible en tant que dimension dans Adobe Analytics ; elle est uniquement incluse dans les données brutes ([Flux de données](../export/analytics-data-feed/data-feed-overview.md)). | Aucun |
| Informations sur le formulaire fournies sur votre site | Tous les types d’implémentation nécessitent une configuration pour collecter ces données. Vous pouvez inclure ces données dans des variables personnalisées. | [eVar](../components/dimensions/evar.md) |
| Clics sur des publicités ou des liens sur votre site | Collecté automatiquement en cas d’utilisation de AppMeasurement. Des informations supplémentaires, telles que l’emplacement des clics, sont disponibles avec Activity Map activé. | [Activity Map](../analyze/activity-map/activity-map.md), [Lien de sortie](../components/dimensions/exit-link.md), [Lien de téléchargement](../components/dimensions/download-link.md) |
| Produits achetés sur votre site | Tous les types d’implémentation nécessitent une configuration pour collecter ces données. Adobe propose plusieurs variables par défaut pour stocker ces informations. | [Produit](../components/dimensions/product.md), [Commandes](../components/metrics/orders.md), [Recettes](../components/metrics/revenue.md) |

{style="table-layout:auto"}

Voir le menu de navigation sous [Présentation des Dimensions](../components/dimensions/overview.md) et [Présentation des mesures](../components/metrics/overview.md) pour d’autres variables sous lesquelles Adobe peut potentiellement collecter des données.
