---
description: Découvrez comment configurer et spécifier les points de contact pour créer une séquence d’abandons multidimensionnelle.
title: Configurer Une Visualisation Des Abandons
feature: Visualizations
role: User, Admin
exl-id: 9d2a0163-a5cb-4a1c-97e9-e78a8f99aaee
TQID: https://experienceleague.adobe.com/878FKpZVmm9-cCzRv0liWtppRRnHV3NqU1fMneDz4EU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: c67272a6-888e-425e-9e97-a87304637eedid: dcae653e-62c6-4cc8-84e6-ee110b848296id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 898
ht-degree: 33%

---

# Configuration d’une visualisation Abandons

Vous pouvez spécifier des **points de contact** pour créer une séquence d’abandons multidimensionnelle. Dans de nombreux cas, un point de contact est une page de votre site. Ils ne se limitent toutefois pas à cela. Vous pouvez par exemple ajouter des événements, tels que des unités, ainsi que des personnes uniques et des visites récurrentes. Vous pouvez aussi ajouter des dimensions, telles qu’une catégorie, un type de navigateur ou un terme de recherche interne.

Il est possible en outre d’ajouter des segments dans un point de contact, Par exemple, vous pouvez comparer des segments, tels que les utilisateurs d’iOS et d’Android. Faites glisser les segments à comparer en haut de l’abandon pour ajouter des informations sur ces segments au rapport sur les abandons. Pour afficher seulement ces segments, supprimez la ligne de base Toutes les visites.

Les visualisations des abandons ne comportent aucune limitation quant au nombre de points de contact que vous pouvez ajouter ou au nombre de composants que vous pouvez utiliser.

Vous pouvez effectuer un cheminement sur des dimensions, des mesures et des segments. Supposons, par exemple, que quelqu’un `shoes, shirt` regarde sur une page et que, sur la page suivante, il regarde `shirt, socks`. Le prochain rapport de flux de produits généré à partir des chaussures portera sur chemise et chaussettes, SAUF chemise.

## Utilisation

1. Ajoutez une visualisation ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Abandon]**. Voir [Ajouter une visualisation à un panneau](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Faites glisser un composant vers le menu déroulant **[!UICONTROL Ajouter un point de contact]**.

   >[!TIP]
   >
   >Vous pouvez ajouter une seule page au rapport sur les abandons, plutôt que la dimension entière. Cliquez sur la flèche droite ![ChevronRight](/help/assets/icons/ChevronRight.svg) sur la dimension de page pour sélectionner une page spécifique, telle que **[!UICONTROL accueil]**, à ajouter au rapport sur les abandons.


   ![Page d’accueil de la dimension Page d’accueil déplacée vers le champ Ajouter un point de contact.](assets/fallout-drag.png)

1. Continuez à ajouter des points de contact jusqu’à ce que votre séquence soit complète.

   Les nombres encadrés dans la partie grise de la barre correspondent aux abandons entre les points de contact (et non à l’ensemble des abandons à ce point). Les nombres entourés dans la partie verte de la barre indiquent la réussite de l’abaissement du point de contact précédent au point de contact actuel.

   ![Visualisation des abandons](assets/fallout-visualization.png)

   Lors de l’ajout de points de contact, vous pouvez effectuer l’une des opérations suivantes :

   * Combinez plusieurs composants en faisant glisser un ou plusieurs composants supplémentaires sur un seul point de contact.

     >[!NOTE]
     >
     >Plusieurs segments sont reliés par l’opérateur ET, mais plusieurs éléments, tels que des éléments de dimension et les mesures, sont reliés par l’opérateur OU.

   * Réorganisez les points de contact en les faisant glisser vers un autre niveau dans la hiérarchie des abandons.

   * Combinez deux points de contact en faisant glisser un point de contact sur un autre. Déposez le point de contact lorsque vous voyez le mot **[!UICONTROL Combiner]**.

   * Contraindre des points de contact individuels à l’accès suivant (par opposition à *éventuellement*) dans le chemin. Sous chaque point de contact se trouve un sélecteur avec les options **[!UICONTROL Chemin éventuel]** et **[!UICONTROL Accès suivant]**, comme illustré ici :

     | Option | Description |
     |---|---|
     | **[!UICONTROL Chemin définitif]** (par défaut) | Les visiteurs qui *éventuellement* arriveront sur la page suivante du chemin, mais pas nécessairement lors de la prochaine visite, sont comptés. |
     | **[!UICONTROL Accès suivant]** | Les visiteurs qui arriveront sur la page suivante du chemin lors du prochain accès sont comptabilisés. |

   * Pointez sur un point de contact pour afficher l’abandon et d’autres informations sur ce niveau. Les informations incluent le nom du point de contact, le nombre de personnes et le taux de réussite. Vous pouvez également comparer le taux de succès à d’autres points de contact.

## Paramètres

Les paramètres de visualisation disponibles sont les suivants :

| Conteneur d’abandons | Description |
|--- |--- |
| **[!UICONTROL Visites]** ou **[!UICONTROL Visiteurs]** | Basculez entre [!UICONTROL visites] et [!UICONTROL visiteurs] pour analyser le cheminement de la personne. La valeur par défaut est [!UICONTROL  Visiteurs ]. Ces paramètres permettent de comprendre l’engagement des visiteurs au niveau des visiteurs (à l’échelle de toutes visites) ou de contraindre l’analyse à une seule visite. |


## Menu contextuel

Dans le cadre de la visualisation, des options de menu contextuel spécifiques sont disponibles.

### Accès au menu contextuel

Vous pouvez accéder au menu contextuel de l’une des manières suivantes :

* Pointez sur un point de contact dans la visualisation, puis sélectionnez **[!UICONTROL Cliquer pour analyser]**.

  ![Accédez au menu contextuel en passant la souris](assets/fallout-tooltip-analyze.png)

* Cliquez avec le bouton droit sur un point de contact dans la visualisation.

  ![Options d’abandon](assets/fallout-options.png)

### Options du menu contextuel

Les options de menu contextuel suivantes sont disponibles :

| Option | Description |
|--- |--- |
| **[!UICONTROL Tendance du point de contact]** | Consultez dans un graphique linéaire les données sur les tendances d’un point de contact, avec quelques données de détection des anomalies prédéfinies. |
| **[!UICONTROL Tendance du point de contact (%)]** | Calcule la tendance du pourcentage total d’abandons. |
| **[!UICONTROL Tendance de tous les points de contact (%)]** | Affiche en tendance tous les pourcentages de point de contact dans l’abandon (à l’exception de **[!UICONTROL Tous les visiteurs]**, s’il est inclus), sur le même graphique. |
| **[!UICONTROL Répartir les baisses à ce point de contact]** | Vérifiez ce que les visiteurs ont fait entre deux points de contact (ce point de contact et le point de contact suivant) s’ils ont continué jusqu’au point de contact suivant. Cette option crée un tableau à structure libre présentant vos dimensions. Vous pouvez remplacer des dimensions et d’autres éléments du tableau. Par exemple, un tableau intitulé **[!UICONTROL Abandon : tous les visiteurs > Page est égal à l’un des domaines d’accueil]** et contient **[!UICONTROL Page]** comme dimension et **[!UICONTROL Visiteurs uniques]** segmenté par la mesure [segment rapide de projet uniquement](/help/components/segmentation/segmentation-workflow/seg-quick.md) **[!UICONTROL Abandon : tous les visiteurs > Page est égal à l’un des domaines d’accueil]**. Inspectez le segment pour comprendre comment le segment de secours est déterminé. |
| **[!UICONTROL Répartir les abandons à ce point de contact]** | Affichez ce que les visiteurs et visiteuses qui n’ont pas réussi à faire via le funnel ont fait immédiatement après l’étape sélectionnée. Cette option crée un tableau à structure libre présentant vos dimensions. Vous pouvez remplacer des dimensions et d’autres éléments du tableau. Par exemple, un tableau intitulé **[!UICONTROL Abandon : tous les visiteurs > Page est égal à l’un des domaines d’accueil]** et contient **[!UICONTROL Page]** comme dimension et **[!UICONTROL Visiteurs uniques]** segmenté par la mesure [segment rapide de projet uniquement](/help/components/segmentation/segmentation-workflow/seg-quick.md) **[!UICONTROL Abandon : tous les visiteurs > Page est égal à l’un des domaines d’accueil]** segment comme mesure. Examinez le segment pour comprendre comment le segment d’abandon est déterminé. |
| **[!UICONTROL Créer un segment à partir du point de contact]** | Créez un segment à partir du point de contact sélectionné. |

>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Paramètres de visualisation](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu contextuel de visualisation](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

