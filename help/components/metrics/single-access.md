---
title: Accès unique
description: Nombre de fois où une valeur de dimension n’a pas changé au cours d’une visite.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Accès unique

La mesure &quot;Accès unique&quot; indique le nombre de visites pour lesquelles la valeur de dimension ne contenait qu’une seule valeur unique pour la visite entière. Cette mesure s’avère utile dans le contexte d’une dimension pour laquelle vous souhaitez identifier les valeurs de dimension qui stagnent au cours d’une visite.

## Méthode de calcul de cette mesure

Cette mesure comptabilise les visites pour lesquelles la valeur de dimension contenait une seule valeur unique. Vous pouvez définir la valeur de dimension plusieurs fois ou la faire persister tout en la comptabilisant comme un accès unique. Dès qu’une valeur de dimension devient une seconde valeur unique, la visite n’est plus considérée comme un accès unique.

## Différence entre &quot;Accès unique&quot; et &quot;Visite mono-page&quot;

Dans le contexte de la dimension [Page](../dimensions/page.md) , &#39;Accès unique&#39; et &#39;Visites mono-page&#39; sont exactement identiques. Leurs différences apparaissent lorsque vous utilisez d&#39;autres dimensions.

* **Accès** unique : Indique le nombre de visites au cours desquelles la valeur de dimension donnée n’a pas changé pour la totalité de la visite. Il est contextuel à la dimension que vous utilisez dans votre projet.
* **Visite** mono-page : Indique le nombre de visites au cours desquelles la dimension Page n’a pas été modifiée pour l’ensemble de la visite. Bien que vous utilisiez une autre dimension dans votre rapport, elle comptabilise toujours les visites qui contiennent une seule valeur de dimension &quot;Page&quot; unique.

Par exemple, prenons l’exemple suivant de deux visites d’accès. La dimension de votre rapport est la section [](../dimensions/site-section.md)Site.

* Un visiteur affiche deux pages, mais elles se trouvent toutes deux dans la même section du site. Comme la section du site est restée la même pendant la visite, elle compte comme un accès unique. Elle ne compte pas comme une visite sur une seule page, car la visite contient plusieurs valeurs de dimension Page uniques.
* Un visiteur affiche deux pages dans différentes sections du site, mais il se trouve que les deux pages portent le même nom. La visite ne compte pas comme un accès unique car il existe deux valeurs de section de site uniques. Il compte comme une visite d’une seule page car il n’y avait qu’une seule valeur de dimension Page unique.
