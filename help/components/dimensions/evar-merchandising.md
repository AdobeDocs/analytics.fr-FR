---
title: eVar (marchandisage)
description: Variables personnalisées liées à la dimension products.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 25%

---


# eVar (marchandisage)

*Cette page d’aide décrit le fonctionnement des eVars de marchandisage en tant que dimension. For information on how to implement merchandising eVars, see[eVars](/help/implement/vars/page-vars/evar.md)in the Implement user guide.*

Lorsque vous mesurez le succès de termes de recherche ou de campagnes externes, vous voulez généralement qu’une seule valeur reçoive du crédit pour tout événement de succès qui se produit. Par exemple, si un client clique sur un lien d’une campagne par courriel pour visiter votre site Web, tous les achats effectués par ce biais doivent être crédités à cette campagne.

Qu&#39;en est-il des événements qui sont pilotés par la recherche interne ou par la recherche de catégories lorsqu&#39;un client recherche plusieurs articles ? For example, a customer searches your site for `"goggles"`, then adds a pair to their cart:

![Exemple de lunettes](assets/merch-example-goggles.png)

Before checkout, the customer searches for `"winter coat"`, then adds a down jacket to the to their cart:

![Exemple de manteau](assets/merch-example-coat.png)

Lorsque le visiteur termine cet achat, vous obtenez une recherche interne pour `"winter coat"` créditer l’achat d’une paire de lunettes de ski (en supposant que l’eVar utilise l’attribution par défaut de &quot;Le plus récent&quot;). Good for `"winter coat"`, but bad for marketing decisions:

| Terme de recherche interne | Recettes |
|---|---|
| manteau d’hiver | $157 |

## Comment les variables de marchandisage résolvent ce problème

Les eVars de marchandisage vous permettent d’attribuer la valeur actuelle d’une eVar à un produit au moment où un événement de réussite se produit. Cette valeur reste liée à ce produit, même si une ou plusieurs autres valeurs sont définies ultérieurement pour cette eVar.

If merchandising is enabled for the eVar in the previous example, the search term `"goggles"` is tied to the snow goggles, and the search term `"winter coat"` is tied to the down jacket. Les eVars de marchandisage allouent des recettes au niveau du produit, de sorte que chaque terme reçoive du crédit pour le montant des recettes du produit auquel le terme a été associé :

| Terme de recherche interne | Recettes |
|---|---|
| manteau d’hiver | $119 |
| lunettes de ski | $38 |

Voir eVars [de](/help/implement/vars/page-vars/evar-merchandising.md) marchandisage pour obtenir des instructions d’implémentation.

## Instances sur les variables de marchandisage

La mesure [Instances](../metrics/instances.md) n’est pas recommandée pour les variables de marchandisage.

* Pour les variables de marchandisage utilisant la syntaxe du produit, les instances ne sont pas du tout incrémentées.
* Pour les variables de marchandisage utilisant la syntaxe des variables de conversion, les instances sont comptabilisées chaque fois que l’eVar est définie. Cependant, il attribue à l’élément de dimension, sauf si tous les événements suivants se produisent sur le même accès : `"None"`
   * L’eVar de marchandisage est définie avec une valeur.
   * La `products` variable est définie avec une valeur.
   * Un événement de liaison est défini.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Comme la plupart des cas d’utilisation de la syntaxe de variable de conversion nécessitent la variable eVar et la variable products sur différents accès, l’utilisation de la mesure &quot;Instances&quot; n’est pas réaliste.
