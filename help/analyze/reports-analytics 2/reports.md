---
title: Rapports
description: Les dimensions et mesures utilisées par Reports & Analytics pour chaque rapport.
feature: Reports & Analytics Basics
role: User, Admin
exl-id: e3c23d17-fc4b-479e-9c48-6f27ef0de4e3
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 100%

---

# Rapports

{{ra-eol}}

Chaque rapport dans Reports &amp; Analytics utilise une dimension dédiée et une mesure par défaut. Vous pouvez modifier la mesure dans chaque rapport et ajouter des répartitions si nécessaire. Les listes suivantes indiquent la dimension utilisée dans chaque rapport.

>[!NOTE]
>
>L’aspect du menu des rapports peut varier en fonction des personnalisations effectuées par un administrateur de votre entreprise. Voir [Personnalisation des menus](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md) dans le guide d’utilisation Administrateur.

## Mesures du site

Contient des rapports qui sont généralement affichés à l’aide de périodes. Contient également des rapports uniques, tels que des rapports recommandés et des rapports en temps réel.

* Mes rapports recommandés : permet de créer un tableau de bord qui contient plusieurs petits rapports pour obtenir des informations immédiates.
* Mesures clés : un rapport qui vous permet d’afficher jusqu’à cinq mesures à la fois. Permet d’afficher les [Pages vues](/help/components/metrics/page-views.md), les [Visites](/help/components/metrics/visits.md) et les [Visiteurs uniques](/help/components/metrics/unique-visitors.md) par défaut.
* Pages vues : permet d’afficher la mesure [Pages vues](/help/components/metrics/page-views.md) au fil du temps.
* Visites : permet d’afficher la mesure [Visites](/help/components/metrics/visits.md) au fil du temps.
* Visiteurs : permet d’afficher les différentes mesures [Visiteurs uniques](/help/components/metrics/unique-visitors.md) au fil du temps.
   * Visiteurs uniques : permet de compter les visiteurs une seule fois pour la période sélectionnée.
   * Visiteurs uniques par heure : permet de compter les visiteurs plusieurs fois s’ils se rendent sur le site à différentes heures de la période sélectionnée.
   * Visiteurs uniques par jour : permet de compter les visiteurs plusieurs fois s’ils se rendent sur le site au cours des différents jours de la période sélectionnée.
   * Visiteurs uniques par semaine : permet de compter les visiteurs plusieurs fois s’ils se rendent sur le site au cours des différentes semaines de la période sélectionnée.
   * Visiteurs uniques par mois : permet de compter les visiteurs plusieurs fois s’ils se rendent sur le site au cours des différents mois de la période sélectionnée.
   * Visiteurs uniques par trimestre : permet de compter les visiteurs plusieurs fois s’ils se rendent sur le site au cours des différents trimestres de la période sélectionnée. Les trimestres sont répartis comme suit : janvier à mars, avril à juin, juillet à septembre et octobre à décembre.
   * Visiteurs uniques par an : permet de compter les visiteurs plusieurs fois s’ils se rendent sur le site au cours des différentes années civiles de la période sélectionnée.
* Durée de la visite : permet d’utiliser la dimension [Durée de la visite - regroupée](/help/components/dimensions/time-spent-per-visit.md).
* Durée avant l’événement : permet d’utiliser la dimension [Durée avant l’événement](/help/components/dimensions/time-prior-to-event.md).
* Achats : contient des rapports sur les mesures basées sur les achats.
   * Entonnoir de conversion d’achat : rapport sur les [Visites](/help/components/metrics/visits.md), les [Paniers](/help/components/metrics/carts.md), les [Commandes](/help/components/metrics/orders.md), le [Chiffre d’affaires](/help/components/metrics/revenue.md) et les [Unités](/help/components/metrics/units.md) dans un rapport entonnoir. Une visualisation similaire est réalisée dans Analysis Workspace à l’aide de la [visualisation Abandons](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Chiffre d’affaires : permet d’afficher la mesure [Chiffre d’affaires](/help/components/metrics/revenue.md) au fil du temps.
   * Commandes : permet d’afficher la mesure [Commandes](/help/components/metrics/orders.md) au fil du temps.
   * Unités : permet d’afficher la mesure [Unités](/help/components/metrics/units.md) au fil du temps.
* Panier : contient des rapports sur les mesures du panier.
   * Entonnoir de conversion de panier : rapport sur les [Instances](/help/components/metrics/instances.md), les [Paniers](/help/components/metrics/carts.md), les [Passages en caisse](/help/components/metrics/checkouts.md), les [Commandes](/help/components/metrics/orders.md) et le [Chiffre d’affaires](/help/components/metrics/revenue.md) dans un rapport entonnoir.
   * Paniers : permet d’afficher la mesure [Paniers](/help/components/metrics/carts.md) au fil du temps.
   * Consultations de panier : permet d’afficher la mesure [Consultations de panier](/help/components/metrics/cart-views.md) au fil du temps.
   * Ajouts au panier : permet d’afficher la mesure [Ajouts au panier](/help/components/metrics/cart-additions.md) au fil du temps.
   * Retraits du panier : permet d’afficher la mesure [Retraits du panier](/help/components/metrics/cart-removals.md) au fil du temps.
   * Passages en caisse : permet d’afficher la mesure [Passages en caisse](/help/components/metrics/checkouts.md) au fil du temps.
* Événements personnalisés : contient tous les rapports sur les [Événements](/help/components/metrics/custom-events.md) personnalisés spécifiques à votre implémentation.
* Robots : permet d’afficher les rapports liés aux robots.
   * Robots : permet d’afficher les robots qui consultent votre site le plus souvent. Voir [Règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) dans le guide d’utilisation Administrateur.
   * Pages de robots : permet d’afficher les pages les plus consultées par les robots.
* Temps réel : permet d’afficher certaines dimensions et mesures quelques secondes après la collecte de données. Pour plus d’informations, reportez-vous à la section [Rapports en temps réel](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).

## Contenu du site

Contient des rapports sur les dimensions qui affichent généralement le contenu du site. Vous pouvez appliquer des classifications à certains de ces rapports. Appliquer des classifications signifie qu’un rapport devient un menu qui contient le rapport source et les rapports de classification.

* Pages : permet d’utiliser la dimension [Page](/help/components/dimensions/page.md).
* Section du site : permet d’utiliser la dimension [Section du site](/help/components/dimensions/site-section.md).
* Serveurs : permet d’utiliser la dimension [Serveur](/help/components/dimensions/server.md).
* Liens : contient des rapports qui utilisent le suivi des liens.
   * Liens de sortie : permet d’utiliser la dimension [Lien de sortie](/help/components/dimensions/exit-link.md).
   * Téléchargements de fichiers : permet d’utiliser la dimension [Lien de téléchargement](/help/components/dimensions/download-link.md).
   * Liens personnalisés : permet d’utiliser la dimension [Lien personnalisé](/help/components/dimensions/custom-link.md).
   * Pages introuvables : permet d’utiliser la dimension [Pages introuvables](/help/components/dimensions/pages-not-found.md).

## Mobile

Contient des rapports sur les rapports mobiles hérités. Ces rapports basent leurs données sur la chaîne de l’agent utilisateur. Ils utilisent différentes [dimensions mobiles](/help/components/dimensions/mobile-dimensions.md) pour leurs rapports respectifs.

* Appareil : permet d’utiliser la dimension [Appareil mobile](/help/components/dimensions/mobile-dimensions.md).
* Type d’appareil : permet d’utiliser la dimension [Type d’appareil mobile](/help/components/dimensions/mobile-dimensions.md).
* Fabricant : permet d’utiliser la dimension [Fabricant mobile](/help/components/dimensions/mobile-dimensions.md).
* Taille d’écran : permet d’utiliser la dimension [Taille d’écran mobile](/help/components/dimensions/mobile-dimensions.md).
* Hauteur d’écran : permet d’utiliser la dimension [Hauteur d’écran mobile](/help/components/dimensions/mobile-dimensions.md).
* Largeur d’écran : permet d’utiliser la dimension [Largeur d’écran mobile](/help/components/dimensions/mobile-dimensions.md).
* Prise en charge des cookies : permet d’utiliser la dimension [Prise en charge des cookies mobile](/help/components/dimensions/mobile-dimensions.md).
* Prise en charge des images : permet d’utiliser la dimension [Prise en charge des images mobile](/help/components/dimensions/mobile-dimensions.md).
* Codage des couleurs : permet d’utiliser la dimension [Codage des couleurs mobile](/help/components/dimensions/mobile-dimensions.md).
* Prise en charge audio : permet d’utiliser la dimension [Prise en charge audio mobile](/help/components/dimensions/mobile-dimensions.md).
* Prise en charge de la vidéo : permet d’utiliser la dimension [Prise en charge de la vidéo mobile](/help/components/dimensions/mobile-dimensions.md).
* Système d’exploitation (obsolète) : permet d’utiliser la dimension [Système d’exploitation mobile (obsolète)](/help/components/dimensions/mobile-dimensions.md).

## Chemins

Contient des rapports qui vous permettent d’afficher les données de cheminement pour les visiteurs.

* Flux de page suivante : permet d’utiliser un rapport de flux sur l’élément de dimension de la première page. Les chemins parcourus sont similaires aux [Instances](/help/components/metrics/instances.md). Vous pouvez modifier l’élément de dimension signalé. Un rapport similaire dans Analysis Workspace est disponible à l’aide d’une [visualisation Flux](../analysis-workspace/visualizations/c-flow/flow.md).
* Page suivante : prend l’élément de dimension de la première page et vous montre les pages suivantes consultées par les visiteurs.
* Flux de page précédente : permet d’utiliser un rapport de flux sur l’élément de dimension de la première page. Un rapport similaire dans Analysis Workspace est disponible à l’aide d’une [visualisation Flux](../analysis-workspace/visualizations/c-flow/flow.md).
* Page précédente : prend l’élément de dimension de la première page et vous montre les pages précédentes consultées par les visiteurs.
* Abandon : permet de sélectionner les éléments de dimension de page par étapes et indique la proportion de personnes ayant suivi ou non ce chemin. Un rapport similaire dans Analysis Workspace est disponible à l’aide d’une [visualisation Abandons](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Chemins complets : permet d’afficher les chemins individuels sous forme d’éléments de dimension. Retiré dans Analysis Workspace, utilisez plutôt la [visualisation Flux](../analysis-workspace/visualizations/c-flow/flow.md).
* PathFinder : fournit plusieurs types de rapports qui vous permettent d’analyser les chemins (retiré dans Analysis Workspace).
* Longueur de chemin : permet d’utiliser la dimension [Profondeur de visite](/help/components/dimensions/visit-depth.md).
* Analyse de page
   * Résumé de la page : prend l’élément de dimension de la première page et affiche une vue de tendance. Affiche également les points d’entrée, les pages précédentes, les points de sortie et les pages suivantes pour l’élément de dimension de cette première page.
   * Actualisations : permet d’utiliser la dimension [Page](/help/components/dimensions/page.md) avec la mesure [Actualisations](/help/components/metrics/reloads.md).
   * Durée de consultation de la page : permet d’utiliser la dimension [Durée de consultation de la page - regroupée](/help/components/dimensions/time-spent-on-page.md).
   * Clics jusqu’à la page : prend l’élément de dimension de la première page et indique le nombre de clics nécessaires pour atteindre cette page au cours d’une visite donnée.
* Entrées et sorties
   * Pages d’accès : permet d’utiliser la dimension [Pages d’accès](/help/components/dimensions/entry-dimensions.md).
   * Pages d’accès d’origine : permet d’utiliser la dimension [Pages d’accès d’origine](/help/components/dimensions/entry-dimensions.md).
   * Visites sur une seule page : permet d’utiliser la dimension [Page](/help/components/dimensions/page.md) en appliquant le segment « Visites sur une seule page » fourni par Adobe.
   * Pages de sortie : permet d’utiliser la dimension [Pages de sortie](/help/components/dimensions/exit-dimensions.md).

>[!NOTE]
>
>D’autres rapports peuvent apparaître dans ce dossier. Il s’agit d’autres dimensions, telles que les props, dans lesquelles le [cheminement est activé](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) sous les paramètres de la suite de rapports.

## Sources de trafic

Contient un rapport qui indique d’où viennent les visiteurs avant d’arriver sur votre site. Ces rapports ne fonctionnent pas correctement, sauf si vous définissez correctement des [filtres URL internes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) sous les paramètres de la suite de rapports.

* Mots-clés de recherche - tous : permet d’utiliser la dimension [Mot-clé de recherche](/help/components/dimensions/search-keyword.md).
* Mots-clés de recherche - payants : permet d’utiliser la dimension [Mot-clé de recherche - payant](/help/components/dimensions/search-keyword.md).
* Mots-clés de recherche - naturels : permet d’utiliser la dimension [Mot-clé de recherche - naturel](/help/components/dimensions/search-keyword.md).
* Moteurs de recherche - tous : permet d’utiliser la dimension [Moteur de recherche](/help/components/dimensions/search-engine.md).
* Moteurs de recherche - payants : permet d’utiliser la dimension [Moteur de recherche - payant](/help/components/dimensions/search-engine.md).
* Moteurs de recherche - naturels : permet d’utiliser la dimension [Moteur de recherche - naturel](/help/components/dimensions/search-engine.md).
* Classement de toutes les pages de recherche : permet d’utiliser la dimension [Classement de toutes les pages de recherche](/help/components/dimensions/all-search-page-rank.md).
* Domaines référents : permet d’utiliser la dimension [Domaine référent](/help/components/dimensions/referring-domain.md).
* Domaines référents d’origine : permet d’utiliser la dimension [Domaine référent d’origine](/help/components/dimensions/original-referring-domain.md).
* Référents : permet d’utiliser la dimension [Référent](/help/components/dimensions/referrer.md).
* Types de référents : permet d’utiliser la dimension [Type de référent](/help/components/dimensions/referrer-type.md).

## Campagnes

Contient des rapports portant principalement sur la dimension [Code de suivi](/help/components/dimensions/tracking-code.md).

* Entonnoir de conversion de campagne : rapport sur les clics publicitaires, les [Passages en caisse](/help/components/metrics/checkouts.md), les [Commandes](/help/components/metrics/orders.md) et le [Chiffre d’affaires](/help/components/metrics/revenue.md) dans un rapport entonnoir. La mesure des clics publicitaires est similaire à la mesure [Instances](/help/components/metrics/instances.md) dans le contexte de la dimension [Code de suivi](/help/components/dimensions/tracking-code.md). Une visualisation similaire est réalisée dans Analysis Workspace à l’aide de la [visualisation Abandons](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Code de suivi : permet d’utiliser la dimension [Code de suivi](/help/components/dimensions/tracking-code.md).

## Produits

Contient des rapports portant principalement sur la dimension [Produit](/help/components/dimensions/product.md).

* Entonnoir de conversion de produits : rapport sur les [Consultations de produits](/help/components/metrics/product-views.md), les [Ajouts au panier](/help/components/metrics/cart-additions.md), les [Passages en caisse](/help/components/metrics/checkouts.md), les [Commandes](/help/components/metrics/orders.md), les [Unités](/help/components/metrics/units.md) et le [Chiffre d’affaires](/help/components/metrics/revenue.md) dans un rapport entonnoir. Une visualisation similaire est réalisée dans Analysis Workspace à l’aide de la [visualisation Abandons](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Produits : permet d’utiliser la dimension [Produits](/help/components/dimensions/product.md).
* Vente croisée : permet d’afficher les produits couramment vendus ensemble (retirés dans Analysis Workspace).
* Catégories : permet d’utiliser la dimension [Catégorie](/help/components/dimensions/category.md).

## Rétention des visiteurs

Contient des rapports sur les visiteurs qui reviennent sur votre site.

* Fréquence des retours : permet d’utiliser la dimension [Fréquence des retours](/help/components/dimensions/return-frequency.md).
* Visites retours : permet d’afficher la mesure [Visites](/help/components/metrics/visits.md) au fil du temps en appliquant le segment « Visites retours » fourni par Adobe.
* Nombre de visites : permet d’utiliser la dimension [Nombre de visites](/help/components/dimensions/visit-number.md).
* Cycle de vente : dossier pour les rapports liés aux achats.
   * Fidélisation des clients : permet d’utiliser la dimension [Fidélisation des clients](/help/components/dimensions/customer-loyalty.md).
   * Jours avant le premier achat : permet d’utiliser la dimension [Jours avant le premier achat](/help/components/dimensions/days-before-first-purchase.md).
   * Jours depuis le dernier achat : permet d’utiliser la dimension [Jours depuis le dernier achat](/help/components/dimensions/days-since-last-purchase.md).
   * Clients uniques par jour : permet d’afficher les [Visiteurs uniques par jour](/help/components/metrics/unique-visitors.md) au fil du temps en appliquant le segment « acheteurs » fourni par Adobe.
   * Clients uniques par semaine : permet d’afficher les [Visiteurs uniques par semaine](/help/components/metrics/unique-visitors.md) au fil du temps en appliquant le segment « acheteurs » fourni par Adobe.
   * Clients uniques par mois : permet d’afficher les [Visiteurs uniques par mois](/help/components/metrics/unique-visitors.md) au fil du temps en appliquant le segment « acheteurs » fourni par Adobe.
   * Clients uniques par trimestre : permet d’afficher les [Visiteurs uniques par trimestre](/help/components/metrics/unique-visitors.md) au fil du temps en appliquant le segment « acheteurs » fourni par Adobe. Les trimestres sont répartis comme suit : janvier à mars, avril à juin, juillet à septembre et octobre à décembre.
   * Clients uniques par an : permet d’afficher les [Visiteurs uniques par an](/help/components/metrics/unique-visitors.md) au fil du temps en appliquant le segment « acheteurs » fourni par Adobe.

## Profil du visiteur

Contient des rapports sur les visiteurs de votre site.

* Géosegmentation : rapports sur l’origine des visites sur votre site.
   * Pays : permet d’utiliser la dimension [Pays](/help/components/dimensions/countries.md).
   * Région : permet d’utiliser la dimension [Régions](/help/components/dimensions/regions.md).
   * Villes : permet d’utiliser la dimension [Villes](/help/components/dimensions/cities.md).
   * États américains : permet d’utiliser la dimension [États américains](/help/components/dimensions/us-states.md).
   * DMA des États-Unis : permet d’utiliser la dimension [DMA des États-Unis](/help/components/dimensions/us-dma.md).
* Langues : permet d’utiliser la dimension [Langue](/help/components/dimensions/language.md).
* Fuseaux horaires : permet d’utiliser la dimension de fuseau horaire (retirée dans Analysis Workspace). Les éléments de dimension sont le décalage horaire GMT de l’accès.
* Domaine : permet d’utiliser la dimension [Domaine](/help/components/dimensions/domain.md).
* Domaine de haut niveau : permet d’utiliser la dimension de domaine de haut niveau (retirée dans Analysis Workspace). Il regroupe la dimension [Domaines](/help/components/dimensions/domain.md) en catégories de niveau supérieur, généralement par pays du domaine.
* Technologie : dossier contenant des rapports sur les éléments utilisés par le visiteur pour accéder à votre site.
   * Navigateurs : permet d’utiliser la dimension [Navigateurs](/help/components/dimensions/browser.md).
   * Type de navigateur : permet d’utiliser la dimension [Type de navigateur](/help/components/dimensions/browser-type.md).
   * Largeur du navigateur : permet d’utiliser la dimension [Largeur du navigateur - regroupée](/help/components/dimensions/browser-width.md).
   * Hauteur du navigateur : permet d’utiliser la dimension [Hauteur du navigateur - regroupée](/help/components/dimensions/browser-height.md).
   * Système d’exploitation : permet d’utiliser la dimension [Systèmes d’exploitation](/help/components/dimensions/operating-systems.md).
   * Type de système d’exploitation : permet d’utiliser la dimension [Types de systèmes d’exploitation](/help/components/dimensions/operating-system-types.md).
   * Codage des couleurs de l’écran : permet d’utiliser la dimension [Codage des couleurs](/help/components/dimensions/color-depth.md).
   * Résolution de l’écran : permet d’utiliser la dimension [Résolution de l’écran](/help/components/dimensions/monitor-resolution.md).
   * Java : permet d’utiliser la dimension [Java activé](/help/components/dimensions/java-enabled.md).
   * JavaScript : permet d’utiliser la dimension JavaScript activé (retirée dans Analysis Workspace). Les éléments de dimension sont « Activé », « Désactivé » ou « Inconnu », selon que JavaScript est activé ou non sur le navigateur.
   * Version de JavaScript : permet d’utiliser la dimension de version de JavaScript (retirée dans Analysis Workspace). Les éléments de dimension indiquent la version de JavaScript utilisée par le navigateur.
   * Cookies : permet d’utiliser la dimension [Prise en charge des cookies](/help/components/dimensions/cookie-support.md).
   * Types de connexions : permet d’utiliser la dimension [Type de connexion](/help/components/dimensions/connection-type.md).
   * Opérateur de téléphonie mobile : permet d’utiliser la dimension [Opérateur de téléphonie mobile](/help/components/dimensions/mobile-dimensions.md).
* État du visiteur : permet d’utiliser la dimension État (retirée dans Analysis Workspace). Les éléments de dimension proviennent de la variable [`state`](../../implement/vars/page-vars/state.md).
* Code postal du visiteur : permet d’utiliser la dimension [Code postal](/help/components/dimensions/zip-code.md).

## Conversion personnalisée

Contient des rapports spécifiques à votre implémentation. Les rapports de conversion personnalisés utilisent des [eVars](/help/components/dimensions/evar.md) comme dimension.

## Trafic personnalisé

Contient des rapports spécifiques à votre implémentation. Les rapports sur le trafic personnalisé utilisent les [props](/help/components/dimensions/prop.md) comme dimension.

## Canaux marketing

Contient des rapports impliquant des [canaux marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Rapport Aperçu d’un canal : un rapport personnalisé spécifique à Reports &amp; Analytics. Utilise les canaux marketing comme éléments de dimension. Les mesures utilisent l’attribution Première touche ou Dernière touche.
* Canal Première touche : permet d’utiliser la dimension [Canal Première touche](/help/components/dimensions/first-touch-channel.md).
* Détails du canal Première touche : permet d’utiliser la dimension [Détails du canal Première touche](/help/components/dimensions/first-touch-detail.md).
* Canal Dernière touche : permet d’utiliser la dimension [Canal Dernière touche](/help/components/dimensions/last-touch-channel.md).
* Détails du canal Dernière touche : permet d’utiliser la dimension [Détails du canal Dernière touche](/help/components/dimensions/last-touch-detail.md).

## Signets

Contient les rapports que vous avez marqués d’un signet. Voir [Signets](bookmarks.md) pour plus d’informations.

## Tableaux de bord

Contient les tableaux de bord que vous avez créés. Voir [Tableaux de bord](dashboard.md) pour plus d’informations.

## Cibles

Contient les cibles que vous avez créées. Voir [Cibles](targets.md) pour plus d’informations.

>[!NOTE]
>
>Si vous ne trouvez pas votre rapport sur cette page d’aide, il est possible que votre administrateur ait renommé ou modifié des dossiers. Voir [Personnalisation des menus](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md) dans le guide d’utilisation Administrateur.
