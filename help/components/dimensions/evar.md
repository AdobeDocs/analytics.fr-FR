---
title: eVar
description: Dimension personnalisée que vous pouvez utiliser dans les rapports.
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 67%

---


# eVar

*Cette page d’aide décrit le fonctionnement des eVars en tant que dimension. Pour plus d’informations sur la mise en œuvre des eVars, voir[eVars](/help/implement/vars/page-vars/evar.md)dans le Guide d’utilisation de mise en œuvre.*

Les eVars sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Si vous disposez d’un [document de conception de solution](/help/implement/prepare/solution-design.md), la plupart des dimensions propres à votre entreprise se présentent sous la forme d’eVars. Par défaut, les eVars persistent au-delà de l’accès sur lequel elles sont définies. You can customize their expiration and allocation under [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in Report suite settings.

Le nombre d’eVars disponibles dépend de votre contrat avec l’Adobe. Jusqu’à 250 eVars sont disponibles si votre contrat avec Adobe le prend en charge.

Les eVars ne sont pas sensibles à la casse. Si vous envoyez la même valeur dans différents cas (par exemple, `"DOG"` et `"Dog"`), l’Analysis Workspace les regroupe dans le même élément de dimension. La casse de la première valeur affichée au début du mois de rapports est utilisée. Data warehouse affiche la première valeur rencontrée pendant la période de demande.

## Renseigner les eVars avec des données

Chaque eVar collecte des données de la chaîne [`v1` `v250` -](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. Par exemple, le paramètre de chaîne de `v1` requête collecte des données pour l’eVar1, tandis que le paramètre de chaîne de `v222` requête collecte des données pour l’eVar222.

AppMeasurement, qui compile des variables JavaScript dans une demande d’image pour la collecte de données, utilise les variables `eVar1` - `eVar250`. Voir [eVar](/help/implement/vars/page-vars/evar.md) dans le guide de l’utilisateur Mise en oeuvre pour obtenir des instructions sur la mise en oeuvre.

## Éléments de Dimension

Etant donné que les eVars contiennent des chaînes personnalisées dans votre implémentation, votre organisation détermine les éléments de dimension pour chaque eVar. Veillez à enregistrer l’objectif de chaque eVar et les éléments de dimension typiques dans un document [de conception de](/help/implement/prepare/solution-design.md)solution.

## Fonctionnement des eVars

Lorsque vous envoyez des données à Adobe Analytics, les serveurs de collecte de données convertissent l’accès en une seule ligne de données contenant des centaines de colonnes. Deux colonnes sont dédiées à chaque eVar ; l’une pour la collecte directe de données, l’autre pour les valeurs persistantes.

* Une colonne standard contient les données envoyées à Adobe à partir de la demande d’image.
* Une colonne « post » contient des données persistantes, qui dépendent de l’expiration et de l’attribution de l’eVar.

Dans la plupart des cas, la colonne `post_evar` est utilisée dans les rapports.

### Liaison des eVars aux mesures

Les événements de succès et les eVars sont fréquemment définis dans différentes demandes d’image. La colonne `post_evar` permet aux valeurs eVar de se lier aux événements, affichant les données dans les rapports. Prenez par exemple la visite suivante :

1. Un visiteur arrive sur votre site sur votre page d’accueil.
2. Il cherche le mot-clé « chats » en utilisant la recherche interne de votre site. Votre mise en oeuvre utilise l’eVar1 pour la recherche interne.
3. Il consulte un produit et passe par le processus de passage en caisse.

Une version simplifiée des données brutes se présenterait comme suit :

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* La colonne `visitor_id` lie les accès au même visiteur. Dans les données brutes réelles, les valeurs concaténées de `visid_high` et de `visid_low` déterminent l’ID de visiteur.
* La colonne `pagename` renseigne la dimension Pages.
* La colonne `evar` détermine les accès lorsque eVar1 a été explicitement définie.
* La valeur `post_evar1` porte la valeur précédente, en fonction de l’attribution et de l’expiration de la variable définies sous les paramètres de la suite de rapports.
* La colonne `event_list` contient toutes les données de mesure. Dans cet exemple, `event1` est « Recherches » et les autres événements sont des mesures standard du panier. Dans les données brutes réelles, `event_list` contient un ensemble de nombres délimités par des virgules, avec une table de recherche liant ces nombres à une mesure.

### Traduction de la collecte de données en rapports

Les outils d’Adobe Analytics, tels que Analysis Workspace, exploitent ces données collectées. Par exemple, si vous générez un rapport en utilisant eVar1 comme dimension et Commandes comme mesure, un rapport similaire à celui-ci s’affichera :

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace extrait ce rapport selon la logique suivante :

* Examinez toutes les valeurs `event_list` et sélectionnez tous les accès qui contiennent `purchase`.
* Sur ces accès, affichez la valeur `post_evar1`.

### L’importance de l’attribution et de l’expiration

Comme l’attribution et l’expiration déterminent quelles valeurs persistent, elles sont essentielles pour tirer le meilleur parti d’une implémentation d’Analytics. Adobe recommande vivement de discuter au sein de votre organisation de la manière dont plusieurs valeurs pour chaque eVar sont gérées (attribution) et du moment où les eVars cessent de conserver les données (expiration).

* Par défaut, une eVar utilise la dernière attribution. Les nouvelles valeurs remplacent les valeurs conservées.
* Par défaut, une eVar utilise une expiration de visite. Une fois la visite terminée, les valeurs ne sont plus copiées d’une ligne à l’autre dans la colonne `post_evar`.

You can change eVar allocation and expiration under [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in Report suite settings.

## Valeur des eVars par rapport aux props

Dans la plupart des cas, l’Adobe recommande d’utiliser des eVars, prises en charge par les moyens suivants :

* Les eVars sont limitées à 255 octets dans les rapports. Les props sont limitées à 100 octets.
* Par défaut, les props ne persistent pas au-delà de l’accès défini. Les eVars ont une expiration personnalisée, ce qui vous permet de déterminer quand une eVar n’obtient plus le crédit d’un événement ultérieur. Cependant, si vous utilisez le [traitement de l’heure des rapports](/help/components/vrs/vrs-report-time-processing.md), les props et les eVars peuvent utiliser un modèle d’attribution personnalisé.
* Adobe prend en charge jusqu’à 250 eVars et seulement 75 props.

Voir [prop](prop.md) pour plus d’informations sur les comparaisons entre props et eVars.
