---
title: Profondeur moyenne de page
description: Nombre moyen de pages dans lesquelles la dimension existe.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---


# Profondeur moyenne de page

La mesure &quot;Profondeur moyenne de page&quot; indique à quel point la valeur de dimension se trouve au cours d’une visite donnée. Par exemple, votre page d&#39;accueil affiche généralement une profondeur de page moyenne inférieure à celle de votre page de confirmation d’achat, qui se trouve généralement plus loin au cours d’une visite. Cette mesure s’avère utile lorsque vous souhaitez comprendre le nombre de pages d’une valeur de dimension donnée qui se trouvent en moyenne. Vous pouvez utiliser ces informations pour optimiser certaines pages en fonction des visiteurs récents si la page présente une faible profondeur en moyenne.

>[CONSEIL] Utilisez cette mesure en même temps qu’une autre mesure ( [Visites](visits.md), par exemple) pour obtenir de meilleures informations. Si vous utilisez cette mesure seule, vous obtenez des valeurs de dimension contenant des profondeurs de page d’anomalie, ce qui n’a généralement pas de valeur.

## Méthode de calcul de cette mesure

La première page d’une visite a une profondeur de `0`page de. La page suivante a une profondeur de page de 1 et augmente chaque vue de page jusqu’à la fin de la visite. Cette mesure augmente uniquement avec les appels de vue de page ([`t()`](/help/implement/vars/functions/t-method.md)) et non avec les appels de suivi de lien ([`tl()`](/help/implement/vars/functions/tl-method.md)).

Pour une valeur de dimension donnée, ajoutez toutes les profondeurs de page pour cette valeur de dimension et divisez-la par des visites. Le nombre obtenu correspond à la profondeur moyenne de la page, arrondie à l’entier le plus proche. Les valeurs de dimension avec une profondeur de page moyenne `0` signifie qu’elles se trouvaient fréquemment sur la première page de la visite.

Prenons l’exemple de visite suivant :

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Si nous voulions une profondeur de page moyenne pour la valeur de dimension `Page2`, elle serait calculée comme suit :

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP] Si vous souhaitez afficher la profondeur moyenne de page avec une décimale, créez une mesure calculée en utilisant cette mesure comme seul élément de la formule. Augmentez le nombre de décimales de la mesure calculée pour atteindre le nombre de décimales souhaité.

## Pourcentages supérieurs à 100 %

Cette mesure contient fréquemment des pourcentages supérieurs à 100 %. Le dénominateur correspond à la profondeur moyenne de page de la dimension entière et le numérateur à la profondeur moyenne de page de la valeur de dimension. Si la profondeur de page moyenne de la dimension entière est inférieure à la profondeur de page moyenne d’une valeur de dimension donnée, vous verrez des pourcentages supérieurs à 100 %. Le tri des rapports avec classement selon cette mesure montre les valeurs de profondeur de page moyennes des anomalies, ce qui n’a généralement pas de valeur. Adobe recommande le tri selon une autre mesure, telle que [Visites](visits.md), dans les rapports avec classement.