---
title: eVar
description: Dimension personnalisée que vous pouvez utiliser dans les  de.
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# eVar

*Cette page d’aide décrit le fonctionnement des eVars en tant que dimension. Pour plus d’informations sur la mise en oeuvre des eVars, voir[eVars](/help/implement/vars/page-vars/evar.md)dans le guide de l’utilisateur Mise en oeuvre.*

Les eVars sont des variables personnalisées que vous pouvez utiliser comme bon vous semble. Si vous disposez d’un [de conception de](/help/implement/prepare/solution-design.md)solution, la plupart des dimensions propres à votre entreprise se présentent comme des eVars. Par défaut, les eVars persistent au-delà de l’accès sur lequel elles sont définies. Vous pouvez personnaliser leur expiration et leur attribution sous Variables [de](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversion dans les paramètres de la suite de rapports.

## Fonctionnement des eVars

Lorsque vous envoyez des données à Adobe Analytics, les serveurs de collecte de données transforment l’accès en une seule ligne de données contenant des centaines de colonnes. Deux colonnes sont dédiées à chaque eVar ; l’une pour la collecte directe des données, l’autre pour les valeurs persistantes.

* Une colonne standard contient les données envoyées à Adobe à partir de la demande d’image.
* Une colonne &quot;post&quot; contient des données persistantes, qui dépendent de l’expiration et de l’attribution de l’eVar.

Dans presque toutes les circonstances, la `post_evar` colonne est utilisée dans les rapports.

### Comment les eVars sont liées aux mesures

Les  de réussite et les eVars sont fréquemment définis dans différentes demandes d’image. La `post_evar` colonne permet aux valeurs eVar de se lier à des , affichant les données dans les . Prenez l’exemple suivant :

1. Un arrive sur votre site sur votre .
2. Ils recherchent des &quot;chats&quot; en utilisant la recherche interne de votre site. Votre implémentation définit eVar1 sur la recherche interne.
3. Ils  un produit et passent par le processus de passage en caisse.

Une version simplifiée des données brutes se présenterait comme suit :

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* La `visitor_id` colonne lie les accès au même. Dans les données brutes réelles, les valeurs concaténées de `visid_high` et `visid_low` déterminent l’ID de.
* La `pagename` colonne renseigne la dimension Pages.
* La `evar` colonne détermine les accès lorsque eVar1 a été explicitement définie.
* La valeur `post_evar1` porte la valeur précédente, selon l’allocation et l’expiration de la variable définies sous les paramètres de la suite de rapports.
* La `event_list` colonne contient toutes les données de mesure. Dans cet exemple, `event1` il s’agit de &quot;Recherches&quot; et les autres  sont des mesures standard du panier. Dans les données brutes réelles, `event_list` contient un ensemble de nombres délimités par des virgules, avec une table de recherche liant ces nombres à une mesure.

### Traduction de la collecte de données en 

Les outils d’Adobe Analytics, tels que  l’espace de travail , fonctionnent à partir de ces données collectées. Par exemple, si vous lancez un rapport à l’aide de l’eVar1 comme dimension et des Commandes comme mesure, un rapport similaire à celui-ci s’affiche :

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

 Workspace  extrait ce rapport en utilisant la logique suivante :

* Examinez toutes les `event_list` valeurs et sélectionnez tous les accès avec `purchase` elles.
* Sur ces accès, affichez la `post_evar1` valeur.

### L&#39;importance de l&#39;attribution et de l&#39;expiration

Puisque l’attribution et l’expiration déterminent les valeurs persistantes, elles sont essentielles pour tirer le meilleur parti d’une implémentation d’analyse. Adobe recommande vivement de discuter au sein de votre entreprise de la manière dont plusieurs valeurs pour chaque eVar sont gérées (attribution) et lorsque les eVars cessent de conserver les données (expiration).

* Par défaut, une eVar utilise la dernière allocation. Les nouvelles valeurs remplacent les valeurs persistantes.
* Par défaut, une eVar utilise une expiration de visite. Une fois la visite terminée, les valeurs cessent de se copier d’une ligne à l’autre dans la `post_evar` colonne.

Vous pouvez modifier l’attribution et l’expiration des eVars sous Variables [de](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversion dans les paramètres de la suite de rapports.
