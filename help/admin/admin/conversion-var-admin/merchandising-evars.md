---
title: eVars de marchandisage et méthodes de recherche de produits
description: Exploration approfondie des concepts sous-jacents aux eVars de marchandisage et de la manière dont elles traitent et allouent les données.
source-git-commit: e7bfb56b63a9134728360c91f3c835da1952fa5a
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 0%

---

# eVars de marchandisage et méthodes de recherche de produits

Ce document explique les concepts sous-jacents aux eVars de marchandisage, qui traitent et allouent les données différemment des eVars standard. Il explique également comment les eVars de marchandisage se rapportent aux méthodes de recherche de produits.

Bien que la plupart des sites web de vente au détail disposent de plusieurs moyens de rechercher des produits, Adobe considère que les méthodes suivantes sont les méthodes de recherche de produits fondamentales dont chaque client de vente au détail doit effectuer le suivi dans Adobe Analytics :

* Mots-clés de recherche interne
* Codes de suivi de campagne internes
* Catégories de marchandisage/navigation
* Liens de vente croisée

Pour les besoins de ce document, associons quelques eVars aux solutions comme suit :

* eVar2 : Mots-clés de recherche interne
* eVar3 : Codes de suivi de campagne internes
* eVar4 : Catégories de marchandisage/navigation
* eVar5 : Liens de vente croisée

Nous pouvons utiliser un eVar supplémentaire pour mesurer les performances de toutes les méthodes de recherche de produits les unes par rapport aux autres. Outre les méthodes de recherche décrites ci-dessus, l’eVar inclura d’autres méthodes de recherche, telles que des liens vers des pages de détails de produit de sites web externes, dans sa comparaison.

* eVar1 : Méthodes de recherche de produits

Vous ne devez pas configurer ces variables comme des eVars standard, mais plutôt les configurer comme des eVars de marchandisage.  L’utilisation d’eVars de marchandisage vous permet d’allouer toute activité réussie aux valeurs capturées par les eVars à un niveau *par produit* au lieu d’un niveau *par visite/par commande*. Je vais clarifier la différence entre l’attribution par produit et l’attribution par commande dans le reste de ce document.

Pour démontrer comment ces variables doivent être définies, je vais commencer par un exemple dans lequel un visiteur décide d’utiliser la recherche de mots-clés internes &quot;sandales&quot; pour trouver un produit sur le site.  Sur la page des résultats de recherche par mot-clé, vous devez capturer des données dans au moins deux eVars :

* `eVar2` est égal au mot-clé utilisé dans la recherche (&quot;sandales&quot;)
* `eVar1` est égal à la méthode de recherche de produit utilisée (&quot;recherche interne de mots-clés&quot;).

Lorsque vous définissez ces deux variables sur ces valeurs spécifiques, vous savez que le visiteur utilise le terme de recherche de mots-clés internes &quot;sandales&quot; pour trouver un produit.
En même temps, vous savez que le visiteur n’utilise pas d’autres méthodes de recherche de produits pour rechercher des produits (par exemple, il ne navigue pas dans les catégories de produits exactement au même moment qu’il effectue une recherche de mots-clés). Pour garantir que l’attribution appropriée par produit a lieu, ces méthodes inutilisées ne doivent pas créditer la recherche d’un produit trouvé via une recherche interne par mot-clé.  Par conséquent, vous devez insérer une logique dans le code (par exemple, AppMeasurement, SDK Web AEP, etc.) qui définit automatiquement les eVars associées à ces autres méthodes de recherche sur une valeur &quot;méthode de non-recherche&quot;.

Par exemple, lorsqu’un utilisateur recherche des produits à l’aide du mot-clé &quot;sandales&quot;, la logique du code Analytics doit définir les variables suivantes sur la page de résultats de recherche de mots-clés internes :

* eVar2=&quot;sandals&quot;: le mot-clé &quot;sandals&quot; a été utilisé dans la recherche interne par mot-clé.
* eVar1=&quot;recherche interne de mots-clés&quot; : La méthode de recherche &quot;recherche interne par mot-clé&quot; a été utilisée.
* eVar3=&quot;campagne non interne&quot; : une campagne interne n’a pas été utilisée pour accéder à la page des résultats de recherche.
* eVar4=&quot;non-browse&quot; : une catégorie de navigation n’était pas accessible sur la page des résultats de recherche.
* eVar5=&quot;non-vente croisée&quot;: aucun clic n’a été effectué sur un lien de vente croisée sur la page des résultats de recherche.

