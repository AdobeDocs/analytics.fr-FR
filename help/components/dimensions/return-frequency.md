---
title: Fréquence des retours
description: Durée cumulée entre la visite en cours et la visite précédente.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 4%

---


# Fréquence des retours

La dimension &quot;Fréquence des retours&quot; indique le temps qui s’écoule entre les visites des visiteurs de retour. Lorsqu’un visiteur revient sur votre site, Adobe examine depuis combien de temps se trouvait la visite précédente et regroupe l’accès dans l’élément de dimension approprié. Cette dimension est utile pour jauger l’attrait de votre site Web et sa pertinence pour les visiteurs au fil du temps. Il peut également vous aider à identifier l’impact du contenu et des promotions de votre site sur vos visiteurs.

>[!TIP]
>
>Cette dimension n’inclut pas les nouveaux visiteurs.

## Renseigner cette dimension avec des données

Cette dimension est prête à l’emploi pour toutes les implémentations. Si une suite de rapports contient des données, cette dimension fonctionne.

Les données de cette dimension sont définies sur le premier accès de la visite et persistent pour l’ensemble de la visite. La valeur ne peut pas changer en milieu de visite.

## Éléments de dimension

Les éléments de dimension comprennent des intervalles temporels, en fonction du temps écoulé depuis la visite précédente.

* Moins de 1 jour
* 1 à 3 jours
* 3 à 7 jours
* 7 à 14 jours
* 14 jours à 1 mois
* Plus de 1 mois

## Les éléments de dimension apparaissent sous des intervalles en dehors de la plage de dates du projet.

Lorsque vous définissez la plage de dates d’un projet, il est courant de voir l’attribut des éléments de dimension pour les visites en dehors de la plage de dates. Par exemple, un visiteur vient sur votre site en juillet, puis revient deux fois le même jour en septembre. La dimension Fréquence des retours pour le mois de septembre indique une visite sous &quot;Plus d&#39;un mois&quot; et une visite sous &quot;Moins d&#39;un jour&quot;.