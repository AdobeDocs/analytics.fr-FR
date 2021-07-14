---
title: eVars de marchandisage et méthodes de recherche de produits
description: Exploration approfondie des concepts sous-jacents aux eVars de marchandisage et de la manière dont elles traitent et allouent les données.
source-git-commit: 746c2cfd3236df7ec7498749015ddf75c1e558f5
workflow-type: tm+mt
source-wordcount: '246'
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

