---
description: Utilisation des mesures dans les rapports Canal marketing.
seo-description: Utilisation des mesures dans les rapports Canal marketing.
seo-title: Mesures utilisées dans les rapports Canal marketing
solution: Analytics
subtopic: Canaux marketing
title: Mesures utilisées dans les rapports Canal marketing
topic: Reports and Analytics
uuid: be 5 bcb 94-927 e -4 b 5 f-b 201-3 d 54 eb 51 e 740
translation-type: tm+mt
source-git-commit: 15b3f0172f470086ca9a9a596a891de572fcb83e

---


# Mesures utilisées dans les rapports Canal marketing

Utilisation des mesures dans les rapports Canal marketing.

## Metrics used in Marketing Channel reports {#topic_F83F5D4C3E144967AD90D956F0E8A999}

Utilisation des mesures dans les rapports Canal marketing.

![](assets/metric_edit_icon.png)

Ajouter (ou modifier) des mesures.

![](assets/add_column_icon.png)

Ajouter une colonne au rapport.

## First and last-touch metrics {#concept_68D9A50204304BA58C1F8013451E7853}

Première touche et Dernière touche sont des attributs de canal qui vous permettent de déterminer le nombre d'engagements (ou de données de mesure tels que les consultations de produits, les recettes et les commandes) consécutifs à l'activité d'un visiteur dans le canal.

When a success event occurs, Analytics looks at the entire visitor's activity and history (back to the [visitor's engagement expiration](../../components/c-marketing-channels/visitor-engagement.md#topic_32ADFDB12D3A4F35843A4545AC97C49F)). Il note le premier canal emprunté par l’utilisateur, ainsi que le canal le plus récent. Il crédite ensuite l’événement de succès à chaque canal adéquat.

<!-- 

<note>
  A first-touch value has a rolling expiration based on the frequency of a visitor returning to the site. This first-touch expiration resets whenever a visitor returns to the site. This effects reporting by causing first-touch values to persist longer than you might expect. For example, this can occur if an instance of an first-touch channel was created a year ago. Remove the values on the eVar in the admin console to reset. 
</note>

 -->

**Exemple**

Supposons que vous configuriez deux canaux marketing : Recherche payante et Campagne par courriel.

![](assets/paid_search.png)

Recherche payante est une annonce pour un produit. Elle capture l’intérêt du visiteur et génère une consultation de produit, mais ne parvient pas à générer un événement de conversion.

![](assets/email_campaign.png)

Un mois plus tard, vous lancez une campagne par courriel pour le même produit. Cette campagne déclenche un achat de 100 euros (ou tout autre événement de conversion souhaité).

Dans le rapport Canal marketing, le résultat peut être affiché comme suit :

![](assets/report-graphic.png)

Le canal Recherche payante est crédité de 100 euros comme canal Première touche pour les recettes, avec 1 commande Première touche. Le canal Campagne par courriel est crédité de 100 euros en tant que canal de recettes Dernière touche (le canal atteint en dernier par l’utilisateur avant l’événement de conversion), avec une commande Dernière touche. En d’autres termes, l’un des principaux objectifs du rapport est de savoir en quoi la ventilation des recettes sur les canaux Première touche est différente de celle sur les canaux Dernière touche.

Chaque instance d’événement de succès comporte exactement un canal Première touche et un canal Dernière touche. Cela signifie que si vous additionnez une colonne de mesure donnée pour n’importe quel événement de succès, le total sera toujours égal à celui d’une même période. Ce total sera également égal au nombre total d’événements dans le rapport [!UICONTROL Mesures du site] &gt; [!UICONTROL Evénements personnalisés] adéquat. Les mesures d’événement autre que de succès, telles que les visites et les visiteurs, ne correspondront pas 1 à 1 dans la mesure où plusieurs canaux peuvent se déclencher dans une même visite. 

>[!NOTE]
>
>Ce rapport utilise la version Première touche ou Dernière touche de chaque mesure. Il est donc possible que les données affichées dans un rapport [!UICONTROL Canal marketing] ne correspondent pas à celles présentées dans d’autres rapports.

## Metric definitions {#section_364D003D34D748B79503DFA4DD208EDB}

| Mesure | Définition |
|--- |--- |
| Canal Première touche | Premier canal marketing à engager un visiteur. Techniquement, le canal Première touche est une evar avec l'allocation initiale. |
| Visiteur Première touche | Dans le cadre de la création de rapports de canal, un visiteur Première touche est un visiteur unique quotidien en provenance d’un canal. L’engagement du visiteur est stocké pendant la période d’engagement auprès du site, laquelle peut s’étendre sur plusieurs visites. |
| Canal Dernière touche | Canal de conversion, à savoir le dernier canal marketing à engager le visiteur et à déboucher sur une conversion. Un seul canal est défini comme canal Première touche. Le canal Dernière touche peut changer avec chaque visite de retour sur le site. Chaque visite comporte un canal Première touche et Dernière touche. Cependant, la valeur du canal Première touche n’est pas affectée par les visites suivantes. |

## Clic publicitaire {#reference_55E2254F02EF4E7EB0AD2838C948347A}

Un clic publicitaire est une instance sur le canal Dernière touche. Il s’agit de la variable eVar présentant l’allocation la plus récente.

Supposons, par exemple, qu’un visiteur vienne sur votre site Web une fois par jour et que chaque visite provienne d’un canal marketing différent :

* Jour 1 : Recherche payante
* Jour 2 : Afficher
* Jour 3 : Recherche naturelle
* Jour 4 : Afficher
* Jour 5 : Recherche payante
* Jour 6 : Afficher
* Jour 7 : Recherche naturelle

Le rapport Canal Première touche montre 1 nouvel engagement pour Recherche payante. Les autres canaux afficheront 0 nouvel engagement. Le rapport Canal Dernière touche affichera 2 clics publicitaires pour Recherche payante, 3 pour Afficher et 2 pour Recherche naturelle.

## Ajout de mesures à un rapport Canal marketing {#task_D381139E00504666AB2402D553CFEA5B}

Ajoutez des mesures à un rapport Canal marketing. Vous pouvez ajouter jusqu’à quatre mesures à chaque colonne du rapport, et autant de colonnes que vous le souhaitez.

1. Ouvrez le [!UICONTROL rapport Canal marketing].
1. Cliquez sur Ajouter des mesures.

   ![](assets/metric_edit_icon.png)

1. Sous [!UICONTROL Mesures disponibles], faites glisser les mesures depuis la section [!UICONTROL Mesures disponibles] vers la section [!UICONTROL Mesures sélectionnées.]

   ![Résultat de l’étape](assets/metric_create.png)

1. Pour créer des mesures calculées, faites défiler le menu jusqu’à [!UICONTROL Mesures calculées]**, puis cliquez sur[!UICONTROL Créer]**.
1. Cliquez sur **[!UICONTROL Enregistrer.]**
