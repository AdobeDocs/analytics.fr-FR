---
title: eVar (dimension de marchandisage)
description: Variables personnalisées liées à la dimension des produits.
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 92%

---

# eVar (marchandisage)

*Cette page d’aide décrit le fonctionnement des eVars de marchandisage en tant que [dimension](overview.md). Pour plus d’informations sur l’implémentation des eVars de marchandisage, consultez [eVar (variable de marchandisage)](/help/implement/vars/page-vars/evar-merchandising.md) dans le guide d’utilisation de l’implémentation.*

Pour obtenir des informations détaillées sur le fonctionnement des eVars de marchandisage, consultez la page [eVars de marchandisage et méthodes de recherche de produit](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md).

Lorsque vous mesurez le succès de termes de recherche ou de campagnes externes, vous voulez généralement qu’une seule valeur reçoive du crédit pour tout événement de succès qui se produit. Par exemple, si un client clique sur un lien d’une campagne par e-mail pour visiter votre site Web, tous les achats effectués par ce biais doivent être crédités à cette campagne.

Qu’en est-il des événements consécutifs à une recherche interne ou une exploration de catégorie lorsqu’un client recherche plusieurs articles ? Supposons qu’un client recherche « `"goggles"` » (lunettes) sur votre site, puis en ajoute une paire dans le panier :

![Exemple de lunettes](assets/merch-example-goggles.png)

Avant le passage en caisse, le client effectue une recherche « `"winter coat"` » (manteau d’hiver), puis ajoute une doudoune dans le panier :

![Exemple de manteau](assets/merch-example-coat.png)

Lorsque le visiteur termine cet achat, vous obtenez une recherche interne pour `"winter coat"` créditée par l’achat d’une paire de lunettes (en supposant que l’eVar utilise l’attribution par défaut « Le plus récent »). Cela est certes bénéfique pour `"winter coat"`, mais beaucoup moins pour les décisions marketing :

| Terme de recherche interne | Recettes |
|---|---|
| manteau d’hiver | $157 |

## Comment les variables de marchandisage résolvent ce problème

Les variables de marchandisage vous permettent d’affecter la valeur en cours d’une eVar à un produit au moment où l’événement de succès se produit. Cette valeur reste liée à ce produit, même si une ou plusieurs autres valeurs sont définies ultérieurement pour cette eVar.

Si le marchandisage est activé pour l’eVar dans l’exemple précédent, le terme de recherche « `"goggles"` » est associé aux lunettes, et le terme « `"winter coat"` » à la doudoune. Les eVars de marchandisage attribuent les recettes au niveau du produit, de sorte que chaque terme reçoive du crédit pour les recettes relatives au produit auquel il est associé :

| Terme de recherche interne | Recettes |
|---|---|
| manteau d’hiver | $119 |
| lunettes de ski | $38 |

Consultez [eVars de marchandisage](/help/implement/vars/page-vars/evar-merchandising.md) pour obtenir des instructions de mise en œuvre.

## Instances sur les variables de marchandisage

La mesure [Instances](../metrics/instances.md) n’est pas recommandée pour les variables de marchandisage.

* Pour les variables de marchandisage utilisant la syntaxe du produit, les instances ne sont pas du tout incrémentées.
* Pour les variables de marchandisage utilisant la syntaxe des variables de conversion, les instances sont comptabilisées chaque fois que l’eVar est définie. Cependant, elle l’attribue à l’élément de dimension `"None"`, sauf si tous les événements suivants se produisent sur le même accès :
   * L’eVar de marchandisage est définie avec une valeur.
   * La variable `products` est définie avec une valeur.
   * Un événement de liaison est défini.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Comme la plupart des cas d’utilisation de la syntaxe des variables de conversion nécessitent l’eVar et la variable du produit sur différents accès, l’utilisation de la mesure « Instances » n’est pas réaliste.
