---
description: Mesure l’incidence de divers codes de suivi publicitaire sur différents événements de conversion sur votre site. Vous pouvez utiliser ce rapport pour mesurer les performances de campagnes spécifiques pour différents événements de succès ou pour savoir comment vos campagnes favorisent ou entravent les initiatives de votre site, comme par exemple les campagnes qui génèrent les plus grosses recettes.
solution: Analytics
title: Codes de suivi
topic: Reports
uuid: c893d592-10fd-4b40-84b3-8c8949a67b25
translation-type: tm+mt
source-git-commit: 5f087807ddff07f2439f82061e471624381febf8

---


# Codes de suivi

Mesure l’incidence de divers codes de suivi publicitaire sur différents événements de conversion sur votre site. Vous pouvez utiliser ce rapport pour mesurer les performances de campagnes spécifiques pour différents événements de succès ou pour savoir comment vos campagnes favorisent ou entravent les initiatives de votre site, comme par exemple les campagnes qui génèrent les plus grosses recettes.

**Propriétés générales**

* Ce rapport fait directement référence à des données de la variable [s.campaign](/help/implement/js-implementation/page-variables/page-variables.md) implémentée sur votre site web.
* Ce rapport est basé sur une [variable de conversion](/help/admin/admin/conversion-var-admin/conversion-var-admin.md). Cela signifie qu’il peut persister au-delà de la consultation de page et être associé à des mesures dans l’intervalle spécifié.
* La mesure par défaut du rapport est Recettes. Vous pouvez modifier cette valeur par défaut dans le [!UICONTROL Gestionnaire de Report Suites] des [!UICONTROL Outils d’administration]. ( **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Individual Report Settings]** &gt; **[!UICONTROL Default Metrics]**.)

* Ce rapport peut être visualisé sous la forme d’un rapport de tendance ou avec classement.
* Ce rapport peut utiliser un filtre de recherche afin de localiser des éléments spécifiques.
* Les rapports [!UICONTROL Campagnes] et [!UICONTROL Éléments créatifs] sont des classifications basées sur ce rapport. Ils sont automatiquement créés avec chaque suite de rapports.

* Vous pouvez utiliser des classifications SAINT dans ce rapport afin de renommer et de consolider des éléments.
* Vous pouvez ventiler ces rapports selon les éléments suivants (en fonction des paramètres de la suite de rapports et de l’entreprise) :

   * Durée de la visite
   * Rapports Pages et Sections du site, avec toutes les classifications connexes
   * Profondeur de page, Pages d’entrée et Pages d’entrée originales
   * La plupart des rapports de source de trafic
   * Nombre de visites et Fidélité de la clientèle
   * Un grand nombre de rapports Profil du visiteur et Technologie, sauf les rapports de géosegmentation
   * Toutes les variables de conversion

* Les mesures ci-dessous peuvent être utilisées dans ce rapport (en fonction des paramètres de la suite de rapports et de l’entreprise) :

   * Clics publicitaires : nombre de fois où la variable *`s.campaign`* a été définie
   * Toutes les variables de commerce électronique standard : Recettes, Commandes, Unités, Paniers, Consultations du panier, Passages en caisse, Ajouts au panier, Retraits du panier.
   * Tous les événements personnalisés : Événements 1-80, et Événements 81-100 si le code est H22 ou supérieur.
   * Visites et Visiteurs : la disponibilité dépend de la société et de la suite de rapports. Pour plus d’informations, contactez votre gestionnaire de compte.

**Propriétés des Reports &amp; Analytics**

* Click **[!UICONTROL Conversion]** &gt; **[!UICONTROL Campaigns]** &gt; **[!UICONTROL Tracking Code]** to locate this report, unless the menu is customized.

* Ce rapport peut également être ventilé selon toutes les [Variables de liste](https://marketing.adobe.com/resources/help/en_US/sc/implement/list_var.html).
* Pages vues, Visites et Visiteurs uniques sont disponibles en tant que mesures.
* Ce rapport peut faire usage de segments.

**Propriétés d’Ad Hoc Analysis**

* Outre la plupart des variables de conversion prêtes à l’emploi, vous pouvez ventiler le rapport Code de suivi selon tous les autres rapports de l’interface de création de rapports.
* Outre les événements de commerce électronique et personnalisés, vous pouvez utiliser l’ensemble des mesures de conversion et de trafic, ainsi qu’une affectation différente pour toutes les mesures de conversion.
* Ce rapport peut faire usage de segments avancés.

