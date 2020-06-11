---
title: Rapports
description: Dimensions et mesures utilisées par les rapports et analyses pour chaque rapport.
translation-type: tm+mt
source-git-commit: 1968162d856b6a74bc61f22f2e5a6b1599d04c79
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 1%

---


# Rapports

Chaque rapport des rapports et analyses utilise une dimension dédiée et une mesure par défaut. Vous pouvez modifier la mesure dans chaque rapport et ajouter des ventilations si nécessaire. Les listes suivantes indiquent la dimension utilisée dans chaque rapport.

> [!NOTE] Le menu des rapports peut avoir un aspect différent en fonction des personnalisations effectuées par un administrateur de votre organisation. See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.

## Mesures du site

Contient des rapports qui affichent généralement des tendances à l’aide d’une plage de dates. Contient également des rapports uniques, tels que des rapports recommandés et des rapports en temps réel.

* Mes rapports recommandés : Crée un tableau de bord qui contient plusieurs petits rapports pour obtenir des informations immédiates.
* Mesures clés : Rapport qui vous permet d’afficher jusqu’à cinq mesures à la fois. Tendances des vues [de](/help/components/metrics/page-views.md)page, des [visites](/help/components/metrics/visits.md)et des visiteurs [](/help/components/metrics/unique-visitors.md) uniques par défaut.
* vues de page : Tendances au fil du temps la mesure vues [de](/help/components/metrics/page-views.md) page.
* Visites : Tendances de la mesure [Visites](/help/components/metrics/visits.md) au fil du temps.
* Visiteur : Tendances différentes mesures de visiteurs [](/help/components/metrics/unique-visitors.md) uniques au fil du temps.
   * visiteurs uniques : comptabilise les visiteurs une seule fois pour la période sélectionnée.
   * visiteurs uniques par heure : Compte les visiteurs plusieurs fois s’ils se rendent pendant différentes heures de la période sélectionnée.
   * visiteurs uniques quotidiens : Compte les visiteurs plusieurs fois s’ils se rendent au cours de différents jours de la période sélectionnée.
   * visiteurs uniques par semaine : Compte les visiteurs plusieurs fois s’ils se rendent au cours de différentes semaines de la période sélectionnée.
   * visiteurs uniques mensuels : Compte les visiteurs plusieurs fois s’ils se rendent au cours de différents mois de la période sélectionnée.
   * visiteurs uniques trimestriels : Compte les visiteurs plusieurs fois s’ils se rendent au cours de différents trimestres de la période sélectionnée. Les trimestres sont janvier-mars, avril-juin, juillet-septembre et octobre-décembre.
   * visiteurs uniques par an : Compte les visiteurs plusieurs fois s’ils effectuent une visite au cours de différentes années civiles de la période sélectionnée.
* Durée de la visite : Utilise la dimension [Durée de la visite - regroupée](/help/components/dimensions/time-spent-per-visit.md) .
* Heure avant le événement : Utilise la dimension [Heure avant événement](/help/components/dimensions/time-prior-to-event.md) .
* Achats : Contient des rapports sur les mesures basées sur les achats.
   * Entonnoir de conversion d&#39;achat : Rapport sur les [visites](/help/components/metrics/visits.md), les [paniers](/help/components/metrics/carts.md), les [commandes](/help/components/metrics/orders.md), les [recettes et les unités dans un rapport Entonnoir. ](/help/components/metrics/revenue.md)[](/help/components/metrics/units.md) Une visualisation similaire est réalisée dans Analyse Workspace à l’aide de la visualisation [](../analysis-workspace/visualizations/fallout/fallout-flow.md)Abandons.
   * Recettes : Tendances des [recettes](/help/components/metrics/revenue.md) de la mesure au fil du temps.
   * Commandes : Tendances de la mesure [Commandes](/help/components/metrics/orders.md) au fil du temps.
   * Unités : Tendances des [unités](/help/components/metrics/units.md) de mesure au fil du temps.
* Panier : Contient des rapports sur les mesures du panier.
   * Entonnoir de conversion de panier : Rapports [Instances](/help/components/metrics/instances.md), [Paniers](/help/components/metrics/carts.md), [Passages en caisse](/help/components/metrics/checkouts.md), [Commandes et Recettes dans un rapport Entonnoir.](/help/components/metrics/orders.md)[](/help/components/metrics/revenue.md)
   * Paniers : Tendances des [paniers](/help/components/metrics/carts.md) de mesures au fil du temps.
   * vues du panier : Tendances des vues [de](/help/components/metrics/cart-views.md) panier de mesures au fil du temps.
   * Ajouts au panier : Tendances des ajouts [de](/help/components/metrics/cart-additions.md) panier au fil du temps.
   * Retraits du panier : Tend à la hausse la mesure des suppressions [de](/help/components/metrics/cart-removals.md) panier au fil du temps.
   * Passages en caisse : Tend à la hausse la mesure [Passages en caisse](/help/components/metrics/checkouts.md) au fil du temps.
* événements personnalisés : Contient tous les rapports autour de [Événements](/help/components/metrics/custom-events.md) personnalisés spécifiques à votre implémentation.
* Robots : Affiche les rapports liés aux robots.
   * Robots : Affiche les robots qui fréquentent le plus votre site. See [Bot rules](../../admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
   * Pages de robots : Affiche les pages qui ont le plus touché les robots.
* Temps réel : Affiche certaines dimensions et mesures quelques secondes après la collecte des données. See [Real-time reports](/help/components/c-real-time-reporting/realtime.md) for more information.

## Contenu du site

Contient des rapports portant sur les dimensions qui affichent généralement le contenu du site. Vous pouvez appliquer des classifications à certains de ces rapports. L&#39;application de classifications signifie qu&#39;un rapport devient un menu contenant le rapport source et les rapports de classification.

* Pages : Utilise la dimension [Page](/help/components/dimensions/page.md) .
* Section du site : Utilise la dimension de section [](/help/components/dimensions/site-section.md) Site.
* Serveurs : Utilise la dimension [Serveur](/help/components/dimensions/server.md) .
* Liens : Contient des rapports qui utilisent le suivi des liens.
   * Liens de sortie : Utilise la dimension de lien [de](/help/components/dimensions/exit-link.md) sortie.
   * Téléchargements de fichiers : Utilise la dimension de lien [](/help/components/dimensions/download-link.md) Télécharger.
   * Liens personnalisés : Utilise la dimension de lien [](/help/components/dimensions/custom-link.md) personnalisé.
   * Pages introuvables : Utilise la dimension [Pages introuvables](/help/components/dimensions/pages-not-found.md) .

## Mobile

Contient des rapports sur les rapports mobiles hérités. Ces rapports fondent leurs données sur la chaîne de l’agent utilisateur. Ils utilisent différentes dimensions [](/help/components/dimensions/mobile-dimensions.md) mobiles pour leurs rapports respectifs.

* Périphériques : Utilise la dimension Périphérique [](/help/components/dimensions/mobile-dimensions.md) mobile.
* Type de périphérique : Utilise la dimension de type [de périphérique](/help/components/dimensions/mobile-dimensions.md) mobile.
* Fabricant : Utilise la dimension fabricant [de](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Taille d’écran : Utilise la dimension de taille [d’écran](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Hauteur d’écran : Utilise la dimension de hauteur [d’écran](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Largeur d’écran : Utilise la dimension de largeur [d’écran](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Prise en charge des cookies : Utilise la dimension de prise en charge [des cookies](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Prise en charge des images : Utilise la dimension de prise en charge [des images](/help/components/dimensions/mobile-dimensions.md) mobiles.
* Intensité des couleurs : Utilise la dimension de profondeur [de couleur](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Prise en charge audio : Utilise la dimension Prise en charge [audio](/help/components/dimensions/mobile-dimensions.md) mobile.
* Prise en charge de la vidéo : Utilise la dimension de prise en charge [vidéo](/help/components/dimensions/mobile-dimensions.md) mobile.
* Système d’exploitation (obsolète) : Utilise la dimension Système d’exploitation [mobile (obsolète)](/help/components/dimensions/mobile-dimensions.md) .

## Chemins

Contient des rapports qui vous permettent d’afficher les données de cheminement pour les visiteurs.

* Flux de page suivante : Utilise un rapport de flux sur la valeur de dimension de la page supérieure. Les vues de chemin sont similaires aux [instances](/help/components/metrics/instances.md). Vous pouvez modifier la valeur de dimension signalée. Un rapport similaire dans Analyse Workspace est disponible à l’aide d’une visualisation [de](../analysis-workspace/visualizations/c-flow/flow.md)flux.
* Page suivante : Prend la valeur de dimension de la première page et vous montre les pages suivantes auxquelles les visiteurs sont allés.
* Flux de page précédente : Utilise un rapport de flux sur la valeur de dimension de la page supérieure Un rapport similaire dans l’espace de travail d’Analyse est disponible à l’aide d’une visualisation [de](../analysis-workspace/visualizations/c-flow/flow.md)flux.
* Page précédente : Prend la valeur de dimension de la page supérieure et vous montre les pages précédentes d’où viennent les visiteurs.
* Abandon : Permet de sélectionner les valeurs de dimension de page en étapes et indique la proportion de personnes qui ont suivi et non suivi ce chemin. Un rapport similaire dans l’espace de travail d’Analyse est disponible à l’aide d’une visualisation [](../analysis-workspace/visualizations/fallout/fallout-flow.md)Abandons.
* Chemins complets : Affiche les chemins individuels sous forme de valeurs de dimension. Retraité dans Analyse Workspace ; utilisez plutôt la visualisation [](../analysis-workspace/visualizations/c-flow/flow.md) Flux.
* PathFinder : Fournit plusieurs types de rapports qui vous permettent d’analyser les chemins d’accès (retraités dans Analyse Workspace).
* Longueur de chemin : Utilise la dimension de profondeur [de](/help/components/dimensions/visit-depth.md) visite.
* Analyse de page
   * Résumé de la page : Prend la valeur de dimension de la page supérieure et affiche une vue de tendance. Affiche également les points d’entrée, les pages précédentes, les points de sortie et les pages suivantes pour cette valeur de dimension de page supérieure.
   * Rechargements : Utilise la dimension [Page](/help/components/dimensions/page.md) avec la mesure [Rechargements](/help/components/metrics/reloads.md) .
   * Durée de consultation de la page : Utilise la dimension [Durée de consultation de la page - regroupée](/help/components/dimensions/time-spent-on-page.md) .
   * Clics jusqu’à la page : Prend la valeur de dimension de la page supérieure et indique le nombre de clics nécessaires pour atteindre cette page au cours d’une visite donnée.
* Entrées et sorties
   * Pages d’entrée : Utilise la dimension Pages [](/help/components/dimensions/entry-dimensions.md) d’entrée.
   * Pages d&#39;entrée d&#39;origine : Utilise la dimension d’origine [de la page](/help/components/dimensions/entry-dimensions.md) d’entrée.
   * Visites mono-page : Utilise la dimension [Page](/help/components/dimensions/page.md) avec le segment &quot;Visites mono-page&quot; fourni par Adobe appliqué.
   * Pages de sortie : Utilise la dimension Pages [de](/help/components/dimensions/exit-dimensions.md) sortie.

> [!NOTE] D’autres rapports peuvent apparaître dans ce dossier. Il s’agit d’autres dimensions, telles que les props, dans lesquelles le [cheminement est activé](../../admin/admin/c-traffic-variables/traffic-var.md) sous les paramètres de la suite de rapports.

## Sources de trafic

Contient un rapport qui indique d’où viennent les visiteurs avant d’arriver sur votre site. Ces rapports ne fonctionnent pas correctement, sauf si vous définissez correctement des filtres [URL](../../admin/admin/internal-url-filter-admin.md) internes sous Paramètres de la suite de rapports.

* Mots-clés de recherche - tous : Utilise la dimension Mot-clé [](/help/components/dimensions/search-keyword.md) de recherche.
* Mots-clés de recherche - payée : Utilise la dimension payée [du mot-clé](/help/components/dimensions/search-keyword.md) de recherche.
* Mots-clés de recherche - naturelle : Utilise le mot-clé [Rechercher - dimension naturelle](/help/components/dimensions/search-keyword.md) .
* Moteurs de recherche - tous : Utilise la dimension du moteur [de](/help/components/dimensions/search-engine.md) recherche.
* Moteurs de recherche - payants : Utilise la dimension payée [du moteur de](/help/components/dimensions/search-engine.md) recherche.
* Moteurs de recherche - naturels : Utilise la dimension naturelle [du moteur de](/help/components/dimensions/search-engine.md) recherche.
* Classement de toutes les pages de recherche : Utilise la dimension de classement [de la page de recherche](/help/components/dimensions/all-search-page-rank.md) Tous.
* Domaines référents : Utilise la dimension de domaine [](/help/components/dimensions/referring-domain.md) référent
* Domaines référents initiaux : Utilise la dimension de domaine [référent](/help/components/dimensions/original-referring-domain.md) original
* Parrains : Utilise la dimension [Parrain](/help/components/dimensions/referrer.md) .
* Types de Parrain : Utilise la dimension de type [de](/help/components/dimensions/referrer-type.md) Parrain.

## Campagnes

Contient des rapports principalement autour de la dimension Code [de](/help/components/dimensions/tracking-code.md) suivi.

* Entonnoir de conversion Campaign : Signale les clics publicitaires, les [passages en caisse](/help/components/metrics/checkouts.md), les [commandes](/help/components/metrics/orders.md)et les [recettes](/help/components/metrics/revenue.md) dans un rapport Entonnoir. La mesure Clics publicitaires est similaire à la mesure [Instances](/help/components/metrics/instances.md) dans le contexte de la dimension Code [de](/help/components/dimensions/tracking-code.md) suivi. Une visualisation similaire est réalisée dans Analyse Workspace à l’aide de la visualisation [](../analysis-workspace/visualizations/fallout/fallout-flow.md)Abandons.
* Code de suivi : Utilise la dimension de code [de](/help/components/dimensions/tracking-code.md) suivi.

## Produits

Contient des rapports principalement autour de la dimension [Produit](/help/components/dimensions/product.md) .

* Entonnoir de conversion de produits : Signale les vues [](/help/components/metrics/product-views.md)de produits, les ajouts [au](/help/components/metrics/cart-additions.md)panier, les [passages en caisse](/help/components/metrics/checkouts.md), les [commandes, Units et les recettes dans un rapport Entonnoir. ](/help/components/metrics/orders.md)[](/help/components/metrics/units.md)[](/help/components/metrics/revenue.md) Une visualisation similaire est réalisée dans Analyse Workspace à l’aide de la visualisation [](../analysis-workspace/visualizations/fallout/fallout-flow.md)Abandons.
* Produits : Utilise la dimension [Produits](/help/components/dimensions/product.md) .
* Vente croisée : Affiche les produits couramment vendus ensemble (retraités dans Analyse Workspace).
* Catégories : Utilise la dimension [Catégorie](/help/components/dimensions/category.md) .

## Rétention des visiteurs

Contient des rapports autour des visiteurs qui reviennent sur votre site.

* Fréquence des retours : Utilise la dimension de fréquence [des](/help/components/dimensions/return-frequency.md) retours.
* Visites de retour : Tend la mesure [Visites](/help/components/metrics/visits.md) au fil du temps en appliquant le segment Visites de retour fourni par Adobe.
* Nombre de visites : Utilise la dimension Nombre [de](/help/components/dimensions/visit-number.md) visites.
* Cycle de vente : Dossier pour les rapports liés aux achats.
   * Fidélité de la clientèle : Utilise la dimension Fidélité [](/help/components/dimensions/customer-loyalty.md) du client.
   * Jours avant le premier achat : Utilise la dimension [Jours avant le premier achat](/help/components/dimensions/days-before-first-purchase.md) .
   * Jours depuis le dernier achat : Utilise la dimension [Jours depuis le dernier achat](/help/components/dimensions/days-since-last-purchase.md) .
   * Clients quotidiens uniques : Tendances visiteurs [uniques](/help/components/metrics/unique-visitors.md) quotidiens au fil du temps avec le segment &quot;acheteurs&quot; fourni par Adobe appliqué.
   * Clients hebdomadaires uniques : Tendances visiteurs [uniques](/help/components/metrics/unique-visitors.md) hebdomadaires au fil du temps avec le segment &quot;acheteurs&quot; fourni par Adobe appliqué.
   * Clients uniques mensuels : Tendances visiteurs [uniques](/help/components/metrics/unique-visitors.md) mensuels au fil du temps avec le segment &quot;acheteurs&quot; fourni par Adobe appliqué.
   * Clients trimestriels uniques : Tendances visiteurs [uniques](/help/components/metrics/unique-visitors.md) trimestriels au fil du temps avec le segment &quot;acheteurs&quot; fourni par Adobe appliqué. Les trimestres sont janvier-mars, avril-juin, juillet-septembre et octobre-décembre.
   * Clients uniques annuels : Tendances visiteurs [uniques](/help/components/metrics/unique-visitors.md) annuels au fil du temps avec le segment &quot;acheteurs&quot; fourni par Adobe appliqué.

## Profil du visiteur

Contient des rapports sur les visiteurs de votre site.

* Géosegmentation : Rapports sur la provenance des accès sur le globe à votre site.
   * Pays : Utilise la dimension [Pays](/help/components/dimensions/countries.md) .
   * Région : Utilise la dimension [Régions](/help/components/dimensions/regions.md) .
   * Villes : Utilise la dimension [Villes](/help/components/dimensions/cities.md) .
   * Les États-Unis déclarent : Utilise la dimension Etats [](/help/components/dimensions/us-states.md) américains.
   * DMA US : Utilise la dimension DMA [](/help/components/dimensions/us-dma.md) US.
* Langues : Utilise la dimension [Langage](/help/components/dimensions/language.md) .
* Fuseaux horaires : Utilise la dimension de fuseau horaire (retiré dans l’espace de travail des Analyses). Les valeurs de dimension sont le décalage GMT de l’accès.
* Domaine : Utilise la dimension [Domaine](/help/components/dimensions/domain.md) .
* Domaine de niveau supérieur : Utilise la dimension de domaine de niveau supérieur (retirée dans l’espace de travail des Analyses). Il regroupe les [domaines](/help/components/dimensions/domain.md) en catégories de niveau supérieur, généralement par pays du domaine.
* Technologie : Dossier contenant des rapports sur les éléments utilisés par le visiteur pour accéder à votre site.
   * Navigateurs : Utilise la dimension [Navigateurs](/help/components/dimensions/browser.md) .
   * Type de navigateur : Utilise la dimension de type [](/help/components/dimensions/browser-type.md) Navigateur.
   * Largeur du navigateur : Utilise la largeur du [navigateur - dimension regroupée](/help/components/dimensions/browser-width.md) .
   * Hauteur du navigateur : Utilise la hauteur du [navigateur - dimension avec empilement](/help/components/dimensions/browser-height.md) .
   * Système d&#39;exploitation : Utilise la dimension Systèmes [d’](/help/components/dimensions/operating-systems.md) exploitation.
   * Type de système d’exploitation : Utilise la dimension Types [de système](/help/components/dimensions/operating-system-types.md) d’exploitation.
   * Intensité des couleurs de l&#39;écran : Utilise la dimension de profondeur [de](/help/components/dimensions/color-depth.md) couleur.
   * Résolution de l&#39;écran : Utilise la dimension de résolution [de l’](/help/components/dimensions/monitor-resolution.md) écran.
   * Java : Utilise la dimension [Java activée](/help/components/dimensions/java-enabled.md) .
   * JavaScript : Utilise la dimension JavaScript activée (désactivée dans Analyse Workspace). Les valeurs de dimension sont &quot;Activé&quot;, &quot;Désactivé&quot; ou &quot;Inconnu&quot;, selon si JavaScript est activé dans le navigateur.
   * Version de JavaScript : utilise la dimension de version JavaScript (retraitée dans Analyse Workspace). Les valeurs de dimension indiquent la version de JavaScript utilisée par le navigateur.
   * Cookies : Utilise la dimension de prise en charge [des](/help/components/dimensions/cookie-support.md) cookies.
   * Types de connexion : Utilise la dimension de type [](/help/components/dimensions/connection-type.md) Connexion.
   * Opérateur de téléphonie mobile : Utilise la dimension Opérateur [de](/help/components/dimensions/mobile-dimensions.md) téléphonie mobile.
* Etat du Visiteur : Utilise la dimension Etat (retiré dans l’espace de travail d’Analyse). Les valeurs de dimension proviennent de la [`state`](../../implement/vars/page-vars/state.md) variable.
* Code postal du Visiteur : Utilise la dimension de code [](/help/components/dimensions/zip-code.md) postal.

## Conversion personnalisée

Contient des rapports spécifiques à votre mise en oeuvre. Les rapports de conversion personnalisés utilisent [des eVars](/help/components/dimensions/evar.md) comme dimension.

## Trafic personnalisé

Contient des rapports spécifiques à votre mise en oeuvre. Les rapports de trafic personnalisés utilisent [les props](/help/components/dimensions/prop.md) comme dimension.

## Canaux marketing

Contient des rapports impliquant des canaux [](/help/components/c-marketing-channels/c-getting-started-mchannel.md)marketing.

* Rapport d&#39;aperçu du Canal : Rapport personnalisé spécifique aux rapports et analyses. Utilise les canaux marketing comme valeurs de dimension, les mesures utilisant l’attribution Première touche ou Dernière touche.
* canal Première touche : Utilise la dimension canal [](/help/components/dimensions/first-touch-channel.md) Première touche.
* Détails du canal Première touche : Utilise la dimension détaillée [du canal](/help/components/dimensions/first-touch-detail.md) Première touche.
* canal Dernière touche : Utilise la dimension canal [](/help/components/dimensions/last-touch-channel.md) Dernière touche.
* Détails du canal Dernière touche : Utilise la dimension détaillée [du canal](/help/components/dimensions/last-touch-detail.md) Dernière touche.

## Signets

Contient les rapports que vous avez mis en signet. Voir [Signets](bookmarks.md) pour plus d’informations.

## Tableaux de bord

Contient les tableaux de bord que vous avez créés. Voir [Tableaux de bord](dashboard.md) pour plus d’informations.

## Cibles 

Contient les cibles que vous avez créées. Voir [Cibles](targets.md) pour plus d’informations.

> [!NOTE] Si vous ne trouvez pas votre rapport sur cette page d&#39;aide, il est possible que votre administrateur ait renommé ou modifié des dossiers. See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.
