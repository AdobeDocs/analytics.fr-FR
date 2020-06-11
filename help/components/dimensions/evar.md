---
title: eVar
description: Dimension personnalisée que vous pouvez utiliser dans le rapports.
translation-type: tm+mt
source-git-commit: 10e157e370367374b55ee9c87c0e5c7ca9e99c1a
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 5%

---


# eVar

*Cette page d’aide décrit le fonctionnement des eVars en tant que dimension. Pour plus d’informations sur la mise en oeuvre des eVars, voir[eVars](/help/implement/vars/page-vars/evar.md)dans le guide de l’utilisateur Mise en oeuvre.*

Les eVars sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Si vous disposez d’un document [de conception de](/help/implement/prepare/solution-design.md)solution, la plupart des dimensions propres à votre entreprise se présentent sous la forme d’eVars. Par défaut, les eVars persistent au-delà de l’accès sur lequel elles sont définies. Vous pouvez personnaliser leur expiration et leur attribution sous Variables [de](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversion dans les paramètres de la suite de rapports.

Le nombre d’eVars disponibles dépend de votre contrat avec Adobe. Jusqu’à 250 eVars sont disponibles si votre contrat avec Adobe le prend en charge.

## Renseigner les eVars avec des données

Chaque eVar collecte des données de la chaîne [`v1` `v250` -](/help/implement/validate/query-parameters.md) requête dans les demandes d’image. Par exemple, le paramètre de chaîne de `v1` requête collecte des données pour eVar1, tandis que le paramètre de chaîne de `v222` requête collecte des données pour eVar222.

AppMeasurement, qui compile des variables JavaScript dans une demande d’image pour la collecte de données, utilise les variables `eVar1` - `eVar250`. Voir [eVar](/help/implement/vars/page-vars/evar.md) dans le guide de l’utilisateur Mise en oeuvre pour obtenir des instructions d’implémentation.

## Valeurs de dimension

Etant donné que les eVars contiennent des chaînes personnalisées dans votre implémentation, votre organisation détermine les valeurs de dimension de chaque eVar. Veillez à enregistrer l’objectif de chaque eVar et les valeurs de dimension standard dans un document [de conception de](/help/implement/prepare/solution-design.md)solution.

## Fonctionnement des eVars

Lorsque vous envoyez des données à Adobe Analytics, les serveurs de collecte de données convertissent l’accès en une seule ligne de données contenant des centaines de colonnes. Deux colonnes sont dédiées à chaque eVar ; l’une pour la collecte directe de données, l’autre pour les valeurs persistantes.

* Une colonne standard contient les données envoyées à Adobe à partir de la demande d’image.
* Une colonne &quot;post&quot; contient des données persistantes, qui dépendent de l’expiration et de l’attribution de l’eVar.

Dans la plupart des cas, la `post_evar` colonne est utilisée dans les rapports.

### Liaison des eVars aux mesures

Les événements de réussite et les eVars sont fréquemment définis dans différentes demandes d’image. La `post_evar` colonne permet aux valeurs eVar de se lier aux événements, affichant les données dans le rapports. Prenez par exemple la visite suivante :

1. Un visiteur arrive sur votre site sur votre page d&#39;accueil.
2. Ils recherchent des &quot;chats&quot; en utilisant la recherche interne de votre site. Votre implémentation utilise eVar1 pour la recherche interne.
3. Ils ont vue un produit et passent par le processus de passage en caisse.

Une version simplifiée des données brutes se présenterait comme suit :

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* La `visitor_id` colonne lie les accès au même visiteur. Dans les données brutes réelles, les valeurs concaténées de `visid_high` et de `visid_low` déterminer l’ID de visiteur.
* La `pagename` colonne renseigne la dimension Pages.
* La `evar` colonne détermine les accès lorsque eVar1 a été explicitement définie.
* La valeur `post_evar1` porte la valeur précédente, en fonction de l’attribution et de l’expiration de la variable définies sous les paramètres de la suite de rapports.
* La `event_list` colonne contient toutes les données de mesure. Dans cet exemple, `event1` il s’agit de &quot;Recherches&quot; et les autres événements sont des mesures standard du panier. Dans les données brutes réelles, `event_list` contient un ensemble de nombres délimités par des virgules, avec une table de choix liant ces nombres à une mesure.

### Traduire la collecte de données en rapports

Les outils d’Adobe Analytics, tels que Analyse Workspace, exploitent ces données collectées. Par exemple, si vous générez un rapport en utilisant eVar1 comme dimension et Commandes comme mesure, un rapport similaire à celui-ci s’affichera :

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analyse Workspace extrait ce rapport selon la logique suivante :

* Examinez toutes les `event_list` valeurs et sélectionnez tous les accès qui `purchase` les contiennent.
* Sur ces accès, affichez la `post_evar1` valeur.

### L&#39;importance de l&#39;attribution et de l&#39;expiration

Puisque l’attribution et l’expiration déterminent les valeurs persistantes, elles sont essentielles pour tirer le meilleur parti d’une mise en oeuvre d’analyses. Adobe recommande vivement de discuter au sein de votre organisation de la manière dont plusieurs valeurs pour chaque eVar sont gérées (attribution) et lorsque les eVars cessent de conserver les données (expiration).

* Par défaut, une eVar utilise la dernière attribution. Les nouvelles valeurs remplacent les valeurs conservées.
* Par défaut, une eVar utilise une expiration de visite. Une fois la visite terminée, les valeurs ne sont plus copiées d’une ligne à l’autre dans la `post_evar` colonne.

Vous pouvez modifier l’attribution et l’expiration des eVars sous Variables [de](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversion dans les paramètres de la suite de rapports.

## Valeur des eVars par rapport aux props

Adobe recommande, dans la plupart des cas, d’utiliser des eVars, prises en charge par les moyens suivants :

* Les eVars sont limitées à 255 octets dans les rapports. Les props sont limitées à 100 octets.
* Par défaut, les props ne persistent pas au-delà de l’accès défini. Les eVars ont une expiration personnalisée, ce qui vous permet de déterminer quand une eVar n’obtient plus le crédit d’un événement ultérieur. Cependant, si vous utilisez le traitement [du temps de](/help/components/vrs/vrs-report-time-processing.md)rapport, les props et les eVars peuvent utiliser un modèle d’attribution personnalisé.
* Adobe prend en charge jusqu’à 250 eVars et seulement 75 props.

Voir [prop](prop.md) pour plus d’informations sur les comparaisons entre props et eVars.
