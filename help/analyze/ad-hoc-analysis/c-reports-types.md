---
description: Descriptions des types de rapport utilisés dans Experience Cloud.
title: Types de rapports
topic: Ad hoc analysis
uuid: 357102eb-a172-40ec-a302-01c87abaacb5
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Types de rapports

Descriptions des types de rapport utilisés dans Experience Cloud.

## Rapports de classement {#concept_E1710FFFBB334F3D9DB63A1626DBCB01}

Affiche un tableau contenant des articles classés, à l’aide de valeurs numériques et de pourcentages dans les mesures. Par exemple, un [!UICONTROL rapport Pages] classe les pages de votre site en fonction du trafic, tandis que le tableau détaillé affiche les pourcentages et valeurs numériques pour des mesures telles que Pages vues et Recettes. Le type de graphique par défaut est un graphique à barres horizontal. Les graphiques affichent une couleur pour chaque mesure. Ces rapports peuvent afficher plusieurs mesures.

<!-- 

c_reports_ranked.xml

 -->

Les graphiques classés portent, par défaut, sur cinq éléments ; vous pouvez toutefois représenter graphiquement jusqu’à trente éléments dans les options de graphique.

## Rapports de tendances {#concept_65FEA92704024232BB21A5952939711F}

Ces rapports vous permettent d’examiner la tendance des conversions et des événements selon une granularité temporelle sélectionnée (Heure, Jour, Semaine, Mois, Trimestre ou Année) au cours d’une période de rapport.

<!-- 

c_reports_trended.xml

 -->

L’axe vertical du graphique affiche les éléments qui font l’objet d’un suivi. L’axe horizontal affiche la granularité temporelle. Dans le tableau, vous pouvez afficher des tendances à partir d’une cellule spécifique et lancer un rapport complet à partir de la cellule. La date ou l’heure utilisée dépend de la valeur de la cellule.

Vous pouvez également sélectionner plusieurs cellules et lancer un rapport de tendances sur la base d’une granularité donnée. Lorsque vous établissez des tendances à partir de plusieurs cellules, les colonnes du rapport présentent des données pour l’ensemble de la période de rapport.

Un [!UICONTROL rapport de produits] est un exemple de rapport de tendance. Vous pouvez afficher les recettes générées par un produit au cours de la période sélectionnée. Dans le cas d’une période de rapport hebdomadaire, vous pouvez afficher le montant des recettes générées par ce produit chaque jour de cette période, afficher un graphique de tendance pour un produit spécifique au cours de cette journée ou ouvrir un rapport de tendance distinct pour la sélection.

## Tendance à partir de cellules {#task_AD9275BED5CE4D61AC25778D144406A4}

Cette procédure décrit le lancement d’un rapport de tendance à partir d’une ou de plusieurs cellules d’un tableau.

<!-- 

t_trend_row.xml

 -->

**Pour afficher des tendances à partir de cellules**

1. Ouvrez un rapport de classement.
1. Recherchez la cellule dans le tableau, puis cliquez sur **[!UICONTROL Tendance]**.

   ![](assets/TrendInspector_Buttcon.png)

1. Pour afficher un rapport complet à partir de la cellule, cliquez sur **[!UICONTROL Lancer le rapport de tendance]**.

   Une autre solution consiste à cliquer sur la cellule avec le bouton droit de la souris, puis à sélectionner **[!UICONTROL Cellule tendance]**. Vous pouvez également effectuer cette tâche après avoir sélectionné plusieurs cellules.

## Rapport Totaux {#concept_48E23FB3BCCD43DFB486A048960800A8}

<!-- 

c_reports_totals.xml

 -->

Rapport destiné aux décideurs qui affiche des chiffres essentiels. Il contient les données relatives aux recettes totales, aux pages vues et aux commandes. Vous pouvez segmenter ce rapport et y ajouter d’autres mesures pour afficher des données supplémentaires.

## Rapports de flux {#concept_3E417D018F1B4566973F694B01E6439F}

Les rapports de flux indiquent les chemins empruntés le plus souvent par les utilisateurs pour parcourir les pages, sections de site et serveurs.

<!-- 

c_reports_flow.xml

 -->

**Flux suivant**

Le groupe de rapports [!UICONTROL Flux suivant] comprend trois rapports : [!UICONTROL Flux de page suivante], [!UICONTROL Flux de section suivante] et [!UICONTROL Flux de serveur suivant]. Les rapports de ce groupe indiquent les pages, sections du site et serveurs les plus fréquemment consultés par un visiteur après avoir accédé à une page, une section du site ou un serveur spécifique. Ces rapports montrent les chemins les plus fréquemment suivis par les visiteurs sur votre site Web.

**Flux précédent**

Les rapports Flux précédent sont semblables aux rapports Flux suivant, si ce n’est qu’au lieu de voir où se rendent les visiteurs après une page sélectionnée, vous pouvez voir l’emplacement d’où ils proviennent avant d’accéder à une page spécifique. Les commandes permettant d’utiliser ce rapport sont identiques à celles des rapports de flux suivant.

## Flux de page suivante {#concept_F7565234927942BEAF75D5D94A7AB47D}

Affiche les vues chemin, ou le pourcentage et le nombre de fois où une page a été consultée dans les limites des chemins. Il se peut, par exemple, qu’une politique de confidentialité génère 10 000 pages vues au total, mais que seulement 500 d’entre elles soient immédiatement affichées avant une page d’accueil. Dans ce cas, vous verrez 500 vues chemin. Vous pouvez visualiser le rapport au niveau de la visite ou du visiteur. Le pourcentage de chaque page est affiché en regard de son nom. La largeur d’une ligne connectée à une page représente le pourcentage relatif des visites.

<!-- 

c_reports_next_page_flow.xml

 -->

Par défaut, ce rapport affiche les 10 pages principales consultées par les visiteurs après la page que vous avez sélectionnée. Vous pouvez cliquer sur une page soulignée pour développer un peu plus le graphique. Le nombre de pages pouvant figurer sur le graphique n’est pas limité. De plus, vous pouvez placer le pointeur de la souris sur une page pour afficher des données concernant les visites et les recettes de cette page.

Utilisez ce rapport pour :

* Déterminer les étapes effectuées le plus souvent après la consultation d’une page sélectionnée.
* Optimiser la conception de vos chemins de site pour acheminer le trafic vers la page cible souhaitée.
* Identifier les pages que les visiteurs consultent au lieu de consulter vos pages cibles.

## Flux de serveur suivant {#concept_DB8C20E18AEA4051903C47A16C0E9C4E}

Affiche les données de navigation entre des serveurs sur votre site. Lorsque vous sélectionnez le nom d’un serveur du site, le rapport indique le nombre de visiteurs qui ont navigué du serveur vers chacun des autres serveurs de votre site dans le cadre d’une visite unique ou entre plusieurs visites.

<!-- 

c_reports_next_server_flow.xml

 -->

Si, par exemple, des données spécifiques se trouvent sur des serveurs différents ou en miroir sur des serveurs distincts, le rapport indique le chemin suivi entre les serveurs atteints par les utilisateurs. C’est également vrai pour les domaines de votre site web. Vous pouvez, par exemple, voir le nombre d’utilisateurs qui sont passés de `https://www.mysite.com` à `https://info.mysite.com`ou `https://sales.mysite.com`.

## Flux de section suivante {#concept_7C9C8567E7DF477DA186E47DD3FD47A4}

Le rapport [!UICONTROL Flux de section suivante] est semblable au rapport [!UICONTROL Flux page suivante]. Il affiche des données pour des sections du site (groupes de pages Web connexes). Si une page est contenue dans plusieurs sections du site, le rapport affiche les données pour toutes les sections.

<!-- 

c_reports_next_section_flow.xml

 -->

Par exemple, un détaillant en ligne peut avoir des sections pour ses produits et d’autres sections pour des marques de produits. Dans ce cas, la page Web d’un produit peut appartenir à plusieurs sections. Bien que la page du produit n’ait été visitée qu’une seule fois, le rapport [!UICONTROL Flux de section suivante] indique une page vue pour chaque section associée à la page.

## Flux Page précédente {#concept_ADEAEBAE3F37401B977A27E03B5A523B}

Semblable au rapport [!UICONTROL Flux page suivante]. Le rapport [!UICONTROL Flux page précédente] représente plusieurs niveaux des pages les plus populaires que vos visiteurs consultent avant de passer à la page sélectionnée. Le rapport met également en évidence les pages à partir desquelles les visiteurs arrivent sur votre site.

<!-- 

c_reports_previous_page_flow.xml

 -->

Utilisez ce rapport pour :

* Déterminer les étapes effectuées le plus souvent avant la consultation d’une page sélectionnée.
* Optimiser la conception de vos chemins de site pour acheminer le trafic vers la page cible souhaitée.

## Flux de section précédente {#concept_30688D97B48449E1958866BAF376FA8C}

Le rapport [!UICONTROL Flux de section précédente] est semblable au rapport [!UICONTROL Flux page précédente]. Il affiche des données pour des sections du site (groupes de pages Web connexes). Si une page est contenue dans plusieurs sections du site, le rapport affiche les données pour toutes les sections.

<!-- 

c_reports_previous_section_flow.xml

 -->

Par exemple, un détaillant en ligne peut avoir des sections pour ses produits et d’autres sections pour des marques de produits. Dans ce cas, la page Web d’un produit peut appartenir à plusieurs sections. Bien que la page du produit n’ait été visitée qu’une seule fois, le rapport [!UICONTROL Flux de section précédente] indique une page vue pour chaque section associée à la page.

## Flux de serveur précédent {#concept_8E43208CAF2C4C358F19D4669B73822F}

Ce rapport montre les données de navigation entre les serveurs de votre site. Lorsque vous sélectionnez le nom d’un serveur du site, le rapport indique le nombre de visiteurs qui ont navigué vers ce serveur à partir de chacun des autres serveurs de votre site dans le cadre d’une visite unique ou entre plusieurs visites.

<!-- 

c_reports_previous_server_flow.xml

 -->

Si, par exemple, des données spécifiques se trouvent sur des serveurs différents ou en miroir sur des serveurs distincts, le rapport indique le chemin suivi entre les serveurs atteints par les utilisateurs. C’est également vrai pour les domaines de votre site web. Vous pouvez, par exemple, voir le nombre d’utilisateurs qui sont passés de `www.mysite.com` à `info.mysite.com`ou `sales.mysite.com`.

## Rapports Entonnoir de conversion {#concept_35A2EB61E84441CBB670C2E02CA26F81}

Les rapports Entonnoir de conversion affichent des pourcentages de conversion entre des événements de mesure spécifiques. Vous pouvez utiliser ces rapports pour connaître le nombre de clics publicitaires qui génèrent des ventes et le nombre d’unités vendues. Par exemple, un rapport [!UICONTROL Conversion de produits] indique le pourcentage d’événements Paniers associés à des événements Visites, puis affiche les totaux pour Commandes, Recettes et Unités sur la base de ces événements.

<!-- 

c_reports_conversion_funnel.xml

 -->

Les rapports d’entonnoir suivants sont disponibles :

* [!UICONTROL Entonnoir de conversion d’achat] : affiche Visites (Propre au rapport), Paniers, Commandes, Unités et Recettes.
* [!UICONTROL Entonnoir de conversion de panier d’achats] : affiche Visites (Propre au rapport), Paniers, Passages en caisse, Commandes et Recettes.
* [!UICONTROL Entonnoir d’événements personnalisés] : affiche des événements personnalisés sur votre site. Ce rapport affiche, par défaut, les événements personnalisés de 1 à 5.
* [!UICONTROL Entonnoir de conversion de campagne] : affiche Clics publicitaires, Passages en caisse, Commandes et Recettes.

Le tableau de rapport affiche des statistiques sur les ventes moyennes par clic publicitaire et sur le nombre moyen d’unités vendues par clic publicitaire. Vous pouvez ajouter des mesures et des événements personnalisés d’autres groupes de rapports à ces rapports. Ces entonnoirs présentent de nombreuses similitudes, mais ils sont basés sur des variables et des événements différents. Vous pouvez utiliser ces rapports pour afficher les tendances générales et les pourcentages d’utilisateurs qui déclenchent les événements spécifiques que vous indiquez. Vous pouvez également identifier les endroits où les utilisateurs ne poursuivent pas jusqu’aux événements, ce qui vous éclaire sur ce point précis dans le processus de conversion.

## Rapport Analyse de site {#concept_65694C6BDE424714B7975764F95497A4}

Le rapport [!UICONTROL Analyse de site] indique le cheminement des visiteurs dans des pages et événements spécifiés. Vous pouvez, par exemple, afficher le flux de trafic entre des pages, l’affinité entre les produits et les canaux marketing, ainsi que la manière dont les campagnes et canaux débouchent sur des commandes de produits. Vous pouvez faire glisser des pages, des éléments de dimension (et des listes), ainsi que des événements de mesure. Chaque cylindre représente un ou plusieurs éléments de dimension (pages) ou un événement. Les flèches représentent le flux entre les valeurs de cylindre. Les mesures sont affectées à des positions de cylindre (X et Y), une largeur de cylindre, une hauteur de cylindre et une couleur. La position, la taille et la couleur varient en fonction des valeurs de la mesure.

<!-- 

c_reports_site_analysis.xml

 -->

Faites glisser des éléments depuis les volets d’outils pour les ajouter au graphique ou au champ des dimensions.

Cliquez avec le bouton droit sur des cylindres pour les modifier ou les supprimer.

<!-- Meike, UICONTROL and DNL stripped from tables. Re-add. -->

| Option | Description |
|--- |--- |
| Afficher l’analyse de site à (Visite ou Visiteur) | Permet de basculer entre Visite et Visiteur afin d’analyser le cheminement du visiteur. Ces paramètres vous aident à mieux comprendre l’engagement du visiteur au niveau de la visite, entre les différentes visites. Le cheminement du visiteur est pris en charge dans les rapports Analyse de site, Flux et Abandon. Si vous modifiez ce paramètre, le rapport est exécuté à nouveau, limitant ainsi les données à la sélection. |
| Ajouter un point de contrôle | Affiche l’Éditeur de point de contrôle qui vous permet de sélectionner des dimensions ou des événements à afficher à l’écran. |
| Remplacer le graphique | Remplace le graphique Analyse de site par les points de contrôle ajoutés à l’éditeur. |
| Ajuster à l’écran | Rétablit l’affichage initial du graphique. |
| Vue aérienne | Fournit une vue descendante du graphique. |
| Basculer la grille | Affiche ou masque la grille. |
| Dimension | Il s’agit de l’élément qui fait actuellement l’objet du rapport. Faites-le glisser à partir de Dimensions. |

| Option | Description |
|--- |--- |
| Modifier | Permet d’ajouter des pages à un cylindre ou d’en supprimer. |
| Supprimer | Permet de supprimer un cylindre. |
| Rapports | Permet de lancer un autre rapport à partir du cylindre. |
| Enregistrer le diagramme sous | Permet d’enregistrer le diagramme au format .png ou .jpg. Si vous modifiez les propriétés du diagramme (angle, taille, etc.) avant l’enregistrement, les modifications sont conservées dans la sortie. |
| Copier un diagramme vers le Presse-papiers | Copie le diagramme en vue de le coller dans une autre application. Si vous modifiez les propriétés du diagramme (angle, taille, etc.) avant l’enregistrement, les modifications sont conservées dans la sortie. |
