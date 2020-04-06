---
description: La détection des anomalies utilise la modélisation statistique pour détecter automatiquement les tendances imprévues dans vos données. Le modèle analyse les mesures et détermine une limite inférieure, une limite supérieure et une plage de valeurs attendues. En cas de pic ou de creux inattendu, le système vous avertit dans le rapport.
title: Détection des anomalies
topic: Report builder
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Détection des anomalies {#anomaly-detection}

La détection des anomalies utilise la modélisation statistique pour détecter automatiquement les tendances imprévues dans vos données. Le modèle analyse les mesures et détermine une limite inférieure, une limite supérieure et une plage de valeurs attendues. En cas de pic ou de creux inattendu, le système vous avertit dans le rapport.

Voici quelques exemples d’anomalies que vous pouvez étudier :

* Baisse drastique de la valeur de commande moyenne
* Pic dans les commandes à faible chiffre d&#39;affaires
* Pic ou diminution des inscriptions aux versions d’évaluation
* Pertes dans  
* Épices dans le de mémoire tampon vidéo 
* Pic dans les faibles débits vidéo

>[!NOTE] La détection des anomalies n’est disponible que lorsque vous sélectionnez la granularité Jour.

<p class="head"> <b>Mesures de détection des anomalies</b> </p>

La détection des anomalies ajoute de nouvelles valeurs de mesure pour chaque mesure sélectionnée, notamment :

<table id="table_BF75FC874634498DB6632C12CBD8D533"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Limite inférieure </td> 
   <td colname="col2"> <p>Niveau inférieur de l’intervalle de prédiction. Les valeurs inférieures à ce niveau sont considérées comme anormales. </p> <p>Représente un degré de confiance de 95 % selon lequel les valeurs seront supérieures à ce niveau. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Prévu </td> 
   <td colname="col2"> <p>Valeur prédite basée sur les données  le . Cette valeur est également le point central entre les limites supérieure et inférieure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite supérieure </td> 
   <td colname="col2"> <p>Niveau supérieur de l’intervalle de prédiction. Les valeurs supérieures à ce niveau sont considérées comme anormales. </p> <p>Représente un degré de confiance de 95 % selon lequel les valeurs seront inférieures à ce niveau. </p> </td> 
  </tr> 
 </tbody> 
</table>

Le créateur de rapports applique ces valeurs aux mesures sélectionnées. Par exemple, si vous sélectionnez une mesure Pages vues et appliquez une détection des anomalies, une mesure *`Page Views Lower Bound`* est utilisée.

**Méthode de calcul de la détection des anomalies**

La détection des anomalies utilise une période de formation pour calculer, apprendre et rapporter les données d’intervalle de prédiction par jour. La période de formation est la période historique qui identifie ce qui est normal par rapport à ce qui est anormal, et applique ce qui est appris à la période de création de rapports. Dans les rapports marketing, des périodes de formation de 30, 60 et 90 sont disponibles. Dans le créateur de rapports, 30 jours sont disponibles.

La période de formation n’est pas nécessairement la même que la période de création de rapports sélectionnée. Un graphique de rapport affiche la période de la période que vous spécifiez dans le calendrier.

Pour calculer les données, le total quotidien de chaque mesure est comparé à la période de formation à l’aide de chacun des algorithmes suivants :

* Holt Winters Multiplicative (triple lissage exponentiel)
* Holt Winters Additive (Triple Lissage exponentiel)
* Holts Trend Corrected ( lissage exponentiel)

Chaque algorithme est appliqué pour déterminer l’algorithme avec la plus petite somme des erreurs au carré (SSE). L’erreur en pourcentage absolu moyen (MAPE) et l’erreur standard actuelle sont alors calculées pour s’assurer que le modèle est statistiquement valide.

Ces algorithmes peuvent être étendus pour fournir des prévisions de mesures dans les périodes futures.

La période de formation varie en fonction de la  de la période  de l’, vous pouvez constater des différences dans les données reportées pour la même date dans le cadre de deux périodes différentes.

Par exemple, si vous exécutez un rapport pour la période du 1er au 14 janvier, puis un autre pour la période du 7 au 21 janvier, vous pourrez voir différentes données de prédiction pour la même mesure entre le 7 et le 14 janvier dans les deux rapports différents. C&#39;est le résultat de la différence entre les périodes de formation.

| Période  | Période de formation |
|--- |--- |
| 1er-14 janvier | 27 novembre au 31 décembre |
| 7-21 janvier | 4 décembre au 6 janvier |
