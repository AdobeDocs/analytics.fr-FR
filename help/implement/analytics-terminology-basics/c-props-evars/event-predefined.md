---
description: Liste des événements prédéfinis.
keywords: Mise en œuvre d’Analytics;événement
seo-description: Liste des événements prédéfinis.
seo-title: Qu’est-ce qu’un événement prédéfini ?
solution: Analytics
title: Qu’est-ce qu’un événement prédéfini ?
topic: Développeur et mise en œuvre
uuid: 4d0799ba-0f97-42c3-a620-36c03f9995da
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Qu’est-ce qu’un événement prédéfini ?

Liste des événements prédéfinis.

| prodView | Evénement de succès qui se produit lorsqu’un visiteur consulte un produit. |
|---|---|
| scView | Evénement de succès qui se produit lorsqu’un panier est visualisé. |
| scOpen | Evénement de succès qui se produit la première fois qu’un visiteur ouvre un panier. |
| scAdd | Evénement de succès qui se produit lorsqu’un article est ajouté à un panier. |
| scRemove | Evénement de succès qui se produit lorsqu’un article est retiré d’un panier d’achats. |
| scCheckout | Evénement de succès qui se produit sur la première page d’un passage en caisse. |
| purchase | Evénement de succès qui se produit sur la dernière page d’un passage en caisse (inclut Recettes, Commandes et Unités). |

Lorsque l’un de ces événements prédéfinis se produit, une instance de l’événement en question est incrémentée. Les mesures relatives à l’événement peuvent être consultées dans différents rapports. Vous trouverez, ci-dessous, un exemple du code utilisé pour configurer des événements prédéfinis.

```js
s.events="scAdd"
```

```js
s.events="scOpen,scAdd"
```

* Dans le premier exemple ci-dessus, *`scAdd`* est la valeur de l’événement. Chaque fois qu’un article est ajouté au panier d’achats, l’événement est incrémenté.
* Dans le deuxième exemple, deux valeurs sont capturées simultanément. Lorsque plusieurs événements de succès se déclenchent sur la même page, chacun d’eux est incrémenté.

