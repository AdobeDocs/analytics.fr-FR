---
title: Méthode de calcul de la durée de la visite dans Adobe Analytics
description: Une page agrégée des dimensions et mesures de durée de la visite.
feature: Metrics
exl-id: 71e9b856-8a0a-47be-a73f-4dc7d639a5de
source-git-commit: 03502f42473791bec930cc688c0b7905acf12de6
workflow-type: tm+mt
source-wordcount: '1655'
ht-degree: 65%

---

# Présentation de la durée de la visite

Diverses [!UICONTROL mesures] et dimensions [&#39;](overview.md) de temps passé sont proposées dans les produits Adobe Analytics. Cette page peut vous aider à distinguer la dimension ou la mesure souhaitée que vous recherchez.

## Mesures de « durée de la visite »

| Mesure | Définition | Disponible dans |
|---|---|---|
| [[!UICONTROL Durée totale en secondes]](total-seconds-spent.md) | Représente la durée totale pendant laquelle les visiteurs interagissent avec un élément de dimension spécifique. Inclut l’instance d’une valeur et la persistance sur tous les accès suivants. Dans le cas des props, la durée de la visite est également prise en compte dans les événements de lien ultérieurs. | Analysis Workspace, Report Builder (appelé « temps total passé »), Data Warehouse |
| [[!UICONTROL Durée par visite] (secondes)](time-spent-per-visit.md) | Approximativement *Nombre total de secondes passées / (rebonds de visites)*<br> Représente le temps moyen que les visiteurs et visiteuses passent à interagir avec un élément de dimension spécifique au cours de chaque visite. **Remarque** : cette mesure ne peut pas être calculée indépendamment, car le dénominateur de cette fonction est une mesure interne. | Analysis Workspace |
| [[!UICONTROL Temps passé par visiteur] (secondes)](time-spent-per-visitor.md) | Environ *Nombre total de secondes passées / visiteur unique*<br> représente le temps moyen que les visiteurs et visiteuses passent à interagir avec un élément de dimension spécifique au cours de la durée de vie du visiteur ou de la visiteuse (durée de leur cookie). **Remarque** : cette mesure ne peut pas être calculée indépendamment, car le dénominateur de cette fonction est une mesure interne. | Analysis Workspace |
| [!UICONTROL Temps Passé/Utilisateur (État)] | Environ *Nombre total de secondes passées sur l’application mobile / visiteurs uniques sur l’application mobile*<br> représente le temps moyen que les visiteurs et visiteuses d’applications mobiles passent à interagir avec un élément de dimension spécifique tout au long de la durée de vie du visiteur (durée de son cookie). **Remarque** : cette mesure ne peut pas être calculée indépendamment, car le dénominateur de cette fonction est une mesure interne. | Analysis Workspace |
| [[!UICONTROL Temps moyen passé sur le site] (secondes)](average-time-on-site.md) | Représente la durée totale pendant laquelle les visiteurs interagissent avec un élément de dimension spécifique, par séquence avec un élément de dimension. Il ne se limite pas aux moyennes « site » comme le nom l’indique. Pour plus d’informations sur les séquences, voir le « Mode de calcul de la durée de la visite ».<br>**Remarque :** Cette mesure diffère très probablement de la « durée de la visite » au niveau d’un élément de dimension en raison des différences de dénominateur dans le calcul. | Analysis Workspace, Report Builder (affiché en minutes) |
| [[!UICONTROL Temps moyen passé sur le site]](average-time-on-site.md) | Il s’agit de la même mesure que *Temps moyen passé sur le site (en secondes)*, mais au format de la mesure Heure (`hh:mm:ss`). | Analysis Workspace |
| [!UICONTROL Durée de consultation moyenne de la page] | Mesure obsolète.<br> la place, Adobe vous recommande d’utiliser [[!UICONTROL Temps moyen passé sur le site]](average-time-on-site.md) si le temps moyen d’un élément de dimension est nécessaire. | Report Builder (lorsqu’une dimension figure dans la demande) |

## Dimensions de « durée de la visite »

| Dimension | Définition | Disponible dans |
| --- | --- | --- |
| [[!UICONTROL Temps passé par visite - Valeur granulaire]](../dimensions/time-spent-per-visit.md) | Durée totale passée lors la visite arrondie à la seconde la plus proche et appliquée à chaque accès qui faisait partie de la visite. Il s’agit d’une dimension du niveau de la visite. | Analysis Workspace |
| [[!UICONTROL Durée par visite – Regroupement]](../dimensions/time-spent-per-visit.md) | Dimension granulaire regroupée en 9 plages différentes. Il s’agit d’une dimension du niveau de la visite. Les plages incluent :<ul><li>Moins de 1 minute</li><li>1-5 minutes</li><li>5-10 minutes</li><li>10-30 minutes</li><li>30-60 minutes</li><li>1-2 heures</li><li>2-5 heures</li><li>5-10 heures</li><li>10-15 heures</li></ul>**Remarque** : Il n’existe pas de regroupement plus élevé, car une visite expire après 12 heures d’activité. | Analysis Workspace, Report Builder |
| [[!UICONTROL Durée de consultation de la page - Granulaire]](../dimensions/time-spent-on-page.md) | Durée totale passée sur chaque accès, arrondie à la seconde la plus proche. Il s’agit d’une dimension du niveau de l’accès. Elle comprend à la fois des pages vues et des événements de lien. Malgré son nom, elle ne se limite pas à la dimension « page ». | Analysis Workspace |
| [[!UICONTROL Durée de consultation de la page – Regroupement]](../dimensions/time-spent-on-page.md) | La dimension granulaire a été regroupée en 10 plages. Cependant, la dimension regroupée ne décompte que les pages vues (et exclut les événements de lien). Il s’agit d’une dimension du niveau de l’accès. Les plages incluent :<ul><li>moins de 15 secondes</li><li>15 à 29 secondes</li><li>30 à 59 secondes</li><li>1 à 3 minutes</li><li>3 à 5 minutes</li><li>5 à 10 minutes</li><li>10 à 15 minutes</li><li>15 à 20 minutes</li><li>20 à 30 minutes</li><li>plus de 30 minutes</li></ul> | Analysis Workspace |

## Mode de calcul de la « durée de la visite »

Adobe Analytics utilise des valeurs explicites (y compris les événements de lien et les vues vidéo) pour calculer le temps passé.

>[!NOTE]
>
>Sans les événements de lien tels que [!UICONTROL Affichages de vidéos] ou [!UICONTROL Liens de sortie], la durée de la visite sur le dernier accès d’une visite ne peut pas être connue. Pour des raisons similaires, les [!UICONTROL Visites de rebond] (c’est-à-dire les visites avec un seul accès) n’ont pas de « Durée de la visite » associée.

Le **numérateur** dans tous les calculs de durée de la visite est la durée totale en secondes.

Le **dénominateur** n’est pas disponible comme mesure distincte dans Adobe Analytics. Pour les mesures de « durée de la visite » au niveau de l’accès, les séquences sont utilisées comme dénominateur. Une séquence est un jeu consécutif d’accès pour lequel une variable donnée contient la même valeur (qu’elle soit définie, propagée ou persistante). Le terme « propagé » fait référence à la persistance des props entre les pages vues (c’est-à-dire entre les événements de lien suivants), dans le but de calculer la durée de la visite.

* Par exemple, dans le cas du [!UICONTROL Nom de page] ou d’autres dimensions au niveau des accès, le dénominateur correspond essentiellement aux [!UICONTROL Instances] ou aux [!UICONTROL Pages vues], mais avec des actualisations et des valeurs non définies (par exemple, les événements de lien) comptabilisées comme une seule interaction (une séquence).

* Les accès Rebond et Sortie sont également supprimés du dénominateur car la « durée de la visite » ne peut pas être connue.

## Questions fréquentes

+++Toutes les mesures « Durée de la visite » peuvent-elles être appliquées à une dimension ?

Les mesures « Temps passé » qui peuvent être appliquées à n’importe quelle dimension sont les suivantes :

* [[!UICONTROL Durée totale en secondes]](total-seconds-spent.md)

* [[!UICONTROL Durée de la visite] (en secondes)](time-spent-per-visit.md)

* [[!UICONTROL Durée par visiteur] (en secondes)](time-spent-per-visitor.md)

* [[!UICONTROL Durée moyenne de la visite du site] (en secondes)](average-time-on-site.md)

+++

+++Quelle dimension de durée de la visite est la plus appropriée pour une utilisation dans les ventilations avec d’autres dimensions ?

La dimension [[!UICONTROL Temps passé sur la page - granulaire]](../dimensions/time-spent-on-page.md) est une dimension de niveau accès. La répartition de cette dimension en une autre dimension indique le nombre de secondes de la durée d’un accès lorsque la dimension de répartition était également présente.
Dans l’exemple ci-dessous, le terme de recherche « classifieds » est associé à des temps d’accès de 54 secondes, 59 secondes, etc., ce qui indique peut-être que les visiteurs passent du temps à lire le contenu renvoyé pour ce terme.

![Capture d’écran d’un rapport Temps passé sur la page](assets/time-spent1.png)

+++

+++Quelle mesure est appropriée par rapport à la dimension [!UICONTROL Temps passé sur la page - granulaire] ?

N’importe quelle mesure. La dimension indiquera la durée de la visite sur l’accès exact où l’événement s’est produit. Une durée plus longue de la visite signifie qu’un visiteur est resté plus longtemps sur une page (accès) où l’événement s’est produit.

Rapport Workspace ![présentant une mesure personnalisée utilisée avec une dimension Temps passé](assets/time-spent2.png)

+++

+++En quoi la [!UICONTROL Durée moyenne de la visite du site] diffère-t-elle de la [!UICONTROL Durée de la visite] ?

La différence est le dénominateur de la mesure :

* La [[!UICONTROL Durée moyenne de la visite du site]](average-time-on-site.md) utilise les séquences qui incluent un élément de dimension.

* La [[!UICONTROL Durée de la visite]](time-spent-per-visit.md) utilise le nombre de visites.

Par conséquent, ces mesures peuvent générer des résultats similaires au niveau d’une visite, mais sont différentes au niveau d’un accès.

+++

+++Pourquoi les totaux de répartition avec [!UICONTROL Temps moyen passé sur le site] ne correspondent-ils pas à l’élément de ligne parent ?

Parce que [!UICONTROL Temps moyen passé sur le site] dépend des séquences ininterrompues d’une dimension et que le rapport interne ne dépend pas du rapport externe lors du calcul de ces exécutions.

Prenons pour exemple la visite suivante.

| Accès n° | 1 | 2 | 3 |
|---|---|---|---|
| **Secondes écoulées** | 30 | 100 | 10 |
| **Nom de la page** | Accueil | Product | Accueil |
| **Date** | 1er jan | 1er jan | 1er jan |

Le calcul relatif à la durée de la visite sur la page d’accueil correspondrait à (30+10)/2=20, mais la ventilation par jour donnerait (30+10)/1=40, puisque la journée comporte une seule exécution ininterrompue pour le 1er janvier.

Par conséquent, ces mesures peuvent générer des résultats similaires au niveau d’une visite, mais sont différentes au niveau d’un accès.

+++

## Exemples de calculs de [!UICONTROL durée de la visite]

Supposons que le jeu d’appels au serveur suivant concerne un seul visiteur au cours d’une visite unique :

| Accès de la visite | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **Temps écoulé de la visite (en secondes)** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **Secondes écoulées** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **Type d’accès** | Page | Lien | Page | Page | Page | Page | Page |
| **Nom de la page** | Accueil | - | Product | Accueil | Accueil (rechargement) | Panier | Confirmation de commande |
|  |  |  |  |  |  |  |  |
| **prop1** | A (défini) | A (propagée) | non définie | B (définie) | B (définie) | A (définie) | C (défini) |
| **secondes écoulées prop1** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | Rouge (définie) | Rouge (persistante) | (expirée) | Bleu (définie) | Bleu (définie) | Bleu (persistante) | Rouge (définie) |
| **secondes écoulées eVar1** | 30 | 50 | - | 10 | 40 | 60 | - |

Sur la base du tableau ci-dessus, les mesures de durée de la visite sont calculées comme suit :

| prop1 | Durée totale en secondes | Durée de la visite | Durée par visiteur | Nombre de séquences | Durée moyenne de la visite du site |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| Durée non attribuée | 100 | - | - | - | - |

| eVar1 | Durée totale en secondes | Durée de la visite | Durée par visiteur | Nombre de séquences | Durée moyenne de la visite du site |
|---|---|---|---|---|---|
| Rouge | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Bleu | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Durée non attribuée | 100 | - | - | - | - |

Durée de la visite (granulaire) : 290
Durée par page (granulaire) : 10, 30, 40, 50, 60, 100

Quelques remarques supplémentaires à l’appui de l’exemple :

* Tous les calculs de durée de la visite sont basés sur le temps écoulé de la visite qui commence à zéro lors du premier accès de la visite.

* « Secondes passées » est la différence entre l’horodatage de l’accès actuel et celui de l’accès suivant. En conséquence, le dernier accès de la visite (et rebonds) ne comporte pas de durée de la visite.

* Une « séquence » est un ensemble consécutif d’accès où une variable donnée contient la même valeur (que ce soit en étant définie, étendue vers l’avant ou conservée). Par exemple, prop1 « A » a deux séquences : accès 1 et 2 et accès 6. Les valeurs du dernier accès de la visite ne démarrent pas une nouvelle séquence car le dernier accès ne comporte pas de durée de la visite. La durée moyenne de la visite du site utilise des séquences du dénominateur.

   * Pour des raisons de temps passé uniquement, les props sont « propagées » des accès à la page aux accès aux liens suivants, comme indiqué ci-dessus pour prop1 à l’accès 2. Cela permet à la valeur définie pour prop1 sur l’accès 1 (« A ») d’accumuler le temps passé sur l’accès 2.

   * Les eVars accumulent de la durée de visite sur n’importe quel accès pour lequel l’eVar est définie ou persistante. La persistance des eVars est définie par les paramètres d’eVar dans Analytics > Admin.
