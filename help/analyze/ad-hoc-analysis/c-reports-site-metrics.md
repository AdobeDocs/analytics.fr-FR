---
description: Affiche des informations quantitatives concernant votre site Web, comme le nombre de visiteurs qui ont consulté certaines pages, le nombre global des achats effectués à partir de pages particulières et des informations quantitatives similaires. Chacun de ces rapports est une mesure que vous pouvez placer dans d’autres rapports portant sur les éléments.
title: Rapports sur les mesures du site
topic: Ad hoc analysis
uuid: 0730747a-216f-4a58-b62b-a9812968cde5
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Rapports sur les mesures du site

Affiche des informations quantitatives concernant votre site Web, comme le nombre de visiteurs qui ont consulté certaines pages, le nombre global des achats effectués à partir de pages particulières et des informations quantitatives similaires. Chacun de ces rapports est une mesure que vous pouvez placer dans d’autres rapports portant sur les éléments.

## Rapports sur les mesures du site {#concept_0639CA16551749A693F49ADED4842CCE}

Affiche des informations quantitatives concernant votre site Web, comme le nombre de visiteurs qui ont consulté certaines pages, le nombre global des achats effectués à partir de pages particulières et des informations quantitatives similaires. Chacun de ces rapports est une mesure que vous pouvez placer dans d’autres rapports portant sur les éléments.

Les rapports de mesures indiquent les tendances au fil du temps. Vous pouvez détailler ces rapports par heure et par jour. Vous pouvez également analyser la durée de visite sur votre site, les achats et les recettes et d’autres mesures similaires.

The following Site Metrics reports are available in the [!UICONTROL Site Metrics] menu.

## Rapport des pages vues {#concept_5331AFB6948547F7B8DF367B49360E6B}

<!-- 

c_reports_pageviews.xml

 -->

Rapport de tendance qui affiche le nombre de fois où les pages de votre site web ont été consultées pour une période donnée (heure, jour, semaine, mois, trimestre ou année). A [!UICONTROL Page View] is a request for a full page document, rather than an element of a page, such as an image or video. Par exemple, si un visiteur unique consulte 15 pages durant une visite, 15 pages vues sont comptabilisées. Si un visiteur affiche la même page trois fois durant une visite, trois pages vues sont comptabilisées. Ce rapport vous permet de suivre chaque page vue pour chaque page de votre site, ainsi qu’un groupe de pages vues pour la totalité du site.

## Rapport Visites {#concept_50CA55CF2A41430CBC754AEEEE6023A9}

Affiche le nombre de visites effectuées sur l’ensemble de votre site web au cours d’une période spécifiée. Une *visite* correspond à une séquence de pages vues. Elle débute lorsque le visiteur charge une page et se termine après 30 minutes d’inactivité. Une visite peut durer plusieurs heures, pour autant que le visiteur charge au moins une page avant l’expiration du délai. Une visite ne coïncide pas nécessairement avec une session de navigateur. Par exemple, si un visiteur ferme le navigateur, l’ouvre de nouveau et se rend sur votre site dans les cinq minutes qui suivent, cette visite est considérée comme étant la suite de celle entamée quelques minutes plus tôt. Cela signifie également que si un visiteur consulte une page pendant 35 minutes, la visite est fermée et traitée, et une nouvelle visite commence s’il clique sur un lien vers une autre page. Le suivi des visites est réalisé par des cookies. Il est mis fin à une visite après 12 heures d’activité continue.

<!-- 

c_reports_visits.xml

 -->

In marketing reports and analytics, you can run a [!UICONTROL Visits Report] on a selected page. Dans les Ad Hoc Analysis, vous pouvez segmenter les données afin d’afficher des pages spécifiques.

## Rapport Visiteurs uniques {#concept_39097C54E46C496CBAD537329DB3C84A}

Rapport de tendance qui indique le nombre de visiteurs uniques ayant accédé à votre site. Chaque visiteur est comptabilisé une seule fois, indépendamment du nombre de visites qu’il effectue sur votre site Web. Adobe utilise une technologie dont le brevet est en cours d’homologation, dite « cookie-handshake » (reconnaissance par cookie), pour distinguer un visiteur unique d’un visiteur récurrent. Le cookie-handshake dépasse les limitations de la technologie des cookies des navigateurs Internet.

<!-- 

c_reports_unique_visitors.xml

 -->

Vous pouvez utiliser ce rapport pour :

* identifier le nombre de personnes différentes ayant consulté votre site Web au cours d’une période donnée ;
* déterminer les schémas de trafic récents et comment les promotions amènent des visiteurs uniques sur votre site ;
* comparer le nombre de vos visiteurs uniques au nombre de pages vues.

## Rapport Visiteurs {#concept_7371DAB5DA474D03A2D1448F151E011B}

Affiche le nombre de visiteurs uniques de votre site pour une heure, un jour, une semaine, un mois, un trimestre ou une année sélectionné(e). Un visiteur unique est comptabilisé une seule fois pendant la période sélectionnée. Les visiteurs qui reviennent sur votre site ne sont pas recomptabilisés en tant que visiteurs uniques jusqu’à l’expiration de la période.

<!-- 

c_reports_visitors.xml

 -->

La valeur totale affichée en bas du tableau est la somme de toutes les visites pour une période spécifiée et ne reflète pas toujours le nombre de visiteurs uniques. For example, if you run a [!UICONTROL Daily Unique Visitors Report] with a time frame of several days, the total can include repeat visitors, because the same visitor might return on the next day and be counted again. However, if you run a [!UICONTROL Monthly Unique Visitors Report], the value in the Totals column accurately reflects how many unique visitors came during the month.

## Rapport Durée de visite {#concept_5CDB759F9C9B4002A786A71F2BDBB292}

Indique le temps que les visiteurs ont passé à consulter votre site lors de chaque visite. Il comporte aussi une statistique Durée moyenne de la visite du site, qui indique la durée moyenne d’affichage de votre site par les visiteurs.

<!-- 

c_reports_time_spent_per_visit.xml

 -->

Utilisez ce rapport pour :

* déterminer la durée de la visite des visiteurs sur votre site ;
* découvrir le contenu du site et les promotions qui suscitent l’intérêt des visiteurs ;
* comprendre pourquoi le trafic est élevé alors que les visiteurs repartent immédiatement.

## Rapport Achats {#concept_E3B9AF43CCD24F25A85D05DFB51C4740}

Affiche des données récapitulatives pour les mesures Recettes, Commandes et Unités. Vous pouvez également afficher le rapport [!DNL Purchase Conversion Funnel].

<!-- 

c_reports_purchases.xml

 -->

* **Recettes** : vous permet d’afficher les recettes brutes pour les périodes sélectionnées. Vous pouvez consulter, par exemple, les recettes générées au mois de mars, les commandes passées la semaine dernière ou encore les recettes d’aujourd’hui.
* **Commandes** : indique le nombre de commandes passées sur votre site web lors d’une période spécifiée. Plusieurs produits peuvent faire l’objet d’une commande unique.
* **Unités** : indique le nombre total d’unités commandées lors d’une période spécifiée.
* **Entonnoir de conversion d’achat** : idéal pour présenter les événements de conversion sur votre site, s’ils se produisent dans un ordre spécifique, par exemple dans le cas d’une vente au détail. Un rapport Entonnoir présente la mesure de conversion pour chaque étape du processus de conversion, ainsi que les commandes, les recettes et les unités.

## Rapport Panier {#concept_6AEC5A6C707B46B790C1A79E72F9A339}

Indique le nombre de paniers ouverts lors d’une période spécifiée. Vous pouvez exécuter des rapports afin d’analyser les paniers affichés, les ajouts, les suppressions et les passages en caisse. Un panier est généralement ouvert lorsqu’un client sélectionne un élément à acheter, mais il peut également être ouvert sans aucun élément.

<!-- 

c_reports_shopping_cart.xml

 -->

Vous pouvez utiliser la variable [!UICONTROL Carts Report] pour :

* Déterminer les modèles, les hauts ou les bas au niveau du nombre de paniers ouverts sur le site.
* Analyser des périodes spécifiques afin d’en savoir plus sur les mesures qui ont contribué à l’ouverture du panier.

## Rapport Événements personnalisés {#concept_9337B2FB8A3F417BA8689FE7FD64629F}

Actions de conversion que vos visiteurs sont censés réaliser sur votre site. Il peut s’agir d’un enregistrement, d’un abonnement, d’un formulaire complété, d’un début de conversation, d’un achat, d’une réservation ou d’une enquête terminée.

<!-- 

c_reports_custom_events.xml

 -->

Chaque suite de rapports d’analyse étant unique, cet ensemble de rapports est utilisé différemment par chaque client. A [!UICONTROL Custom Event] report can be used as a counter that shows the number of times an event occurs. For example, if **[!UICONTROL event1]** is set to count the number of times a document is downloaded, then the [!UICONTROL Custom Event] report for Event 1 shows the total number of times the event (or download) occurs. Vous pouvez créer plusieurs rapports d’événement personnalisé.

## Rapports de conversion {#concept_BDD3DD8A46F043BB916C7E346E7C314F}

Indiquent les recettes provenant de différents aspects du site Web. Ce sont, notamment, des rapports indiquant les recettes provenant des campagnes publicitaires, les recettes qui proviennent des clients fidèles par rapport aux nouveaux clients et la ventilation des recettes par produit et de nombreux autres rapports sur les recettes. Les rapports de conversion peuvent également indiquer d’autres événements de succès, tels que les clics sur une publicité, les téléchargements ou d’autres événements.

<!-- 

c_reports_conversion.xml

 -->

Les rapports de conversion comprennent des statistiques en temps réel sur toutes les activités importantes des clients, notamment :

* les schémas d’achat des clients ;
* les mesures relatives au panier d’achat, y compris les abandons ;
* les taux de conversion des clients ;
* l’efficacité de la publicité et des partenaires intermédiaires ;
* les performances de la campagne marketing en ligne et hors ligne ;
* les mesures de la fidélité de la clientèle ;
* des informations sur les cycles de ventes.

## Rapports Canal marketing {#concept_81FFA8C15A9B4914BFED37488ADD17FD}

Les rapports Canal marketing montrent l’attribution du canal Première touche et Dernière touche avec les mesures standard essentielles telles que les recettes, les commandes et les coûts, ce qui vous permet de connaître les recettes générées par chaque canal. Configurez les règles de définition de canal dans [!DNL Admin Console] ; des API spécifiques aux rapports de canal sont disponibles.

<!-- 

c_reports_marketing_channel.xml

 -->

**[!UICONTROL First or Last Touch Channel Report]**: Affiche les mesures montrant les données d’un canal Première touche ou Dernière touche spécifique. Dans ces rapports, vous pouvez séparer un canal et en afficher les détails. Si AdLens est activé, les classifications apparaîtront dans les rapports de canal des Reports and Analytics marketing.

**[!UICONTROL First or Last Touch Channel Detail Reports]**: Affiche des détails tels que les noms de page et les  de, qui proviennent des valeurs  que vous avez configurées dans l’ [!UICONTROL Set the channel's value to] option lors de la configuration des règles. Les rapports Canal détaillés vous permettent de mieux examiner les valeurs détaillées de canal du rapport Présentation.

Pour des informations plus détaillées concernant la configuration du canal marketing dans les rapports et analyses marketing, voir le système d’aide [Canal marketing](/help/components/c-marketing-channels/analyze-mc.md).
