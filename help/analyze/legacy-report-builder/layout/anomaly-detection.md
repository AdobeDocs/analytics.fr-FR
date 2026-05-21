---
description: Découvrez la détection des anomalies et son calcul.
title: Utilisation de la détection des anomalies pour détecter automatiquement les tendances
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
feature: Report Builder
role: User, Admin
exl-id: 6e3881c8-3e1c-4df8-ba38-e8bc84cfc3d4
TQID: https://experienceleague.adobe.com/P2dvU8YgWcjCZ6h4oTxK-2-z1X3-wl-oMp70UIJGeXo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8id: c67272a6-888e-425e-9e97-a87304637eedid: e93b8c4c-c5f7-45f8-9abe-9b710f53f502id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 511
ht-degree: 91%

---

# Détection des anomalies{#anomaly-detection}

{{legacy-arb}}

La détection des anomalies utilise la modélisation statistique pour détecter automatiquement les tendances imprévues dans vos données. Le modèle analyse les mesures et détermine une limite inférieure, une limite supérieure et une plage de valeurs attendues. En cas de pic ou de creux inattendu, le système vous en avertit par le biais du rapport.

Voici quelques exemples d’anomalies dont vous pouvez rechercher l’origine :

* Forte chute de la valeur de commande moyenne
* Pic des commandes avec recettes faibles
* Pic ou diminution des inscriptions aux offres d’essai
* Forte diminution des affichages de pages de destination
* Pic des événements de mémoire tampon pour la vidéo
* Pic des faibles débits en bits pour la vidéo

>[!NOTE]
>
>La détection des anomalies n’est disponible que lorsque vous sélectionnez la granularité Jour.

<p class="head"> <b>Mesures de détection des anomalies</b> </p>

La détection des anomalies ajoute de nouvelles valeurs de mesures pour chaque mesure que vous sélectionnez, notamment :

<table id="table_BF75FC874634498DB6632C12CBD8D533"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Limite inférieure </td> 
   <td colname="col2"> <p>Niveau inférieur de l’intervalle de prédiction. Les valeurs inférieures à ce niveau sont considérées comme anormales. </p> <p>Représente une confiance à 95 % que les valeurs seront au-dessus de ce niveau. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valeur attendue </td> 
   <td colname="col2"> <p>La valeur attendue basée sur l’analyse des données. Cette valeur est également le point du milieu entre les limites supérieure et inférieure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite supérieure </td> 
   <td colname="col2"> <p>Niveau supérieur de l’intervalle de prédiction. Les valeurs supérieures à ce niveau sont considérées comme anormales. </p> <p>Représente une confiance à 95 % que les valeurs seront en dessous de ce niveau. </p> </td> 
  </tr> 
 </tbody> 
</table>

Le Créateur de rapports applique ces valeurs aux mesures sélectionnées. Par exemple, si vous sélectionnez une mesure Pages vues et appliquez la détection des anomalies, une mesure *`Page Views Lower Bound`* est utilisée.

**Comment la détection des anomalies est calculée**

La détection des anomalies utilise une période de formation pour calculer, apprendre et rapporter les données de l’intervalle de prédiction par jour. La période de formation est la période historique qui identifie ce qui est normal par rapport à ce qui est anormal, et applique ce qui est appris à la période de création de rapports. Dans les rapports marketing, des périodes de 30, 60 et 90 jours sont disponibles. Dans Report Builder, 30 jours sont disponibles.

La période de formation n’est pas nécessairement la même que la période de création de rapports sélectionnée. Un graphique de rapport affiche la période de la plage de données que vous indiquée dans le calendrier.

Pour calculer les données, le total journalier pour chaque mesure est comparé à la période de formation en utilisant chacun des algorithmes suivants :

* Holt Winters Multiplicative (Triple lissage exponentiel)
* Holt Winters Additive (Triple lissage exponentiel)
* Holts Trend Corrected (Double lissage exponentiel)

Chaque algorithme est appliqué afin de déterminer l’algorithme avec la plus petite somme des erreurs au carré. L’erreur en pourcentage absolue moyenne et l’erreur standard actuelle sont alors calculées afin de garantir que le modèle est statistiquement valide.

Ces algorithmes peuvent être étendus afin de fournir des prévisions des mesures pour les périodes futures.

La période de formation variant en fonction du début de la période de création de rapports, vous pourrez constater des différences dans les données rapportées pour la même date : elles pourront faire partie de deux périodes différentes.

Par exemple, si vous exécutez un rapport pour la période du 1er au 14 janvier, puis un autre pour la période du 7 au 21 janvier, vous pourrez voir différentes données de prédiction pour la même mesure entre le 7 et le 14 janvier dans les deux rapports différents. C’est le résultat de la différence entre les périodes de formation.

| Plage de création de rapports | Période de formation |
|--- |--- |
| 1er au 14 janvier | 27 novembre au 31 décembre |
| 7 au 21 janvier | 4 décembre au 6 janvier |
