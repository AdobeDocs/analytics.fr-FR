---
description: Fournit une analyse exhaustive, précise et détaillée de l’activité des clients. Les mesures proposées (gestion des campagnes, cycle de ventes, abandons et conversions de clients, par exemple) vous permettent de mesurer les transactions de commerce électronique, les sources des ventes, l’efficacité de la publicité, la fidélité de la clientèle, etc.
title: Conversion
topic: Reports
uuid: 457d3033-6562-4fba-8c2e-0e7a9be44bfd
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conversion

Fournit une analyse exhaustive, précise et détaillée de l’activité des clients. Les mesures proposées (gestion des campagnes, cycle de ventes, abandons et conversions de clients, par exemple) vous permettent de mesurer les transactions de commerce électronique, les sources des ventes, l’efficacité de la publicité, la fidélité de la clientèle, etc.

Si vous souhaitez, par exemple, voir le type des campagnes internes de votre page d’accueil qui peuvent donner lieu à des achats, vous devez d’abord capturer les codes de suivi internes et définir la persistance sur une période équivalant à une visite pour la variable *`s.eVar`* qui capture les campagnes internes. Une fois un événement de succès terminé (un achat, par exemple), le crédit correspondant est attribué à toute variable de conversion qui persiste sur le visiteur, telle que l’ID de campagne interne. L’exécution du [!UICONTROL Rapport de campagne interne] vous permet d’identifier la campagne qui a généré le plus de conversions sur site.

Certains des rapports prêts à l’emploi contiennent des mesures de trafic et de conversion (tels que les rapports [!UICONTROL Moteur de recherche]). Toutefois, les rapports [!UICONTROL Trafic] et [!UICONTROL Conversion] sont exclusifs à votre entreprise et s’affichent dans les menus **[!UICONTROL Trafic]** et **[!UICONTROL Conversion]**.

**Propriétés des rapports**

* Les rapports [!UICONTROL Conversion personnalisée] sont basés sur des eVars (variables de conversion).
* Les variables de conversion peuvent persister au-delà de la consultation de page et être associées à des mesures dans l’intervalle spécifié.
* Par défaut, les mesures du rapport portent sur les recettes. Pour modifier les mesures par défaut, reportez-vous à la section [Sélection des mesures de rapport par défaut](https://marketing.adobe.com/resources/help/en_US/sc/user/t_metrics_set_default.html).
* Vous pouvez consulter ces rapports sous la forme de rapports de tendance et classés.
* Vous pouvez utiliser des classifications dans ces rapports afin de renommer et de consolider des éléments.
* Ces rapports peuvent être ventilés en fonction des éléments suivants si des sous-relations de base sont activées :

   * Campagnes et Produits, avec toutes les classifications connexes
   * Fidélité de la clientèle
   * Toutes les eVars complètement sous-liées

* D’autres rapports sont disponibles pour effectuer une ventilation lorsque les sous-relations complètes sont activées :

   * Durée de la visite
   * Pages et Sections du site, avec toutes les classifications connexes
   * Pages d’entrée
   * Presque tous les rapports Source de trafic
   * Nombre de visites
   * Un grand nombre de rapports Profil du visiteur et Technologie
   * Toutes les autres eVars
   * Canaux marketing Première touche et Dernière touche

* Les événements suivants peuvent être utilisés comme mesures :

   * Instances, nombre de fois où l’eVar a été définie
   * Toutes les variables de commerce électronique standard : Recettes, Commandes, Unités, Paniers, Consultations du panier, Passages en caisse, Ajouts au panier, Retraits du panier.
   * Tous les événements personnalisés : Événements 1-80, et Événements 81-100 si le code est H22 ou supérieur.
   * Visites et Visiteurs : la disponibilité dépend de la société et de la suite de rapports. Pour plus d’informations, contactez votre gestionnaire de compte.

* L’emplacement de chaque rapport [!UICONTROL Conversion personnalisée] varie en fonction de la valeur numérique affectée à l’eVar. En général, ils se trouvent dans le dossier [!UICONTROL Conversion personnalisée] (à condition que le menu ne soit pas personnalisé).

