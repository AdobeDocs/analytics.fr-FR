---
title: Accès unique
description: Nombre de fois où un élément de dimension n’a pas changé au cours d’une visite.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---


# Accès unique

La mesure &quot;Accès unique&quot; indique le nombre de visites au cours desquelles l’élément de dimension ne contenait qu’une seule valeur unique pour la visite entière. Cette mesure s’avère utile dans le contexte d’une dimension pour laquelle vous souhaitez identifier les éléments de dimension qui stagnent au cours d’une visite.

## Méthode de calcul de cette mesure

Cette mesure comptabilise les visites pour lesquelles l’élément de dimension contenait une seule valeur unique. Vous pouvez définir l’élément de dimension plusieurs fois ou le faire persister et le comptabiliser comme un accès unique. Dès qu’un élément de dimension devient une seconde valeur unique, la visite n’est plus considérée comme un accès unique.

## Différence entre &quot;Accès unique&quot; et &quot;Visite mono-page&quot;

Dans le contexte de la dimension [Page](../dimensions/page.md) , &#39;Accès unique&#39; et &#39;Visites mono-page&#39; sont exactement identiques. Leurs différences apparaissent lorsque vous utilisez d&#39;autres dimensions.

* **Accès** unique : Indique le nombre de visites au cours desquelles l’élément de dimension donné n’a pas changé pour la visite complète. Il est contextuel à la dimension que vous utilisez dans votre projet.
* **Visite** mono-page : Indique le nombre de visites au cours desquelles la dimension Page n’a pas été modifiée pour l’ensemble de la visite. Bien que vous utilisiez une autre dimension dans votre rapport, il comptabilise toujours les visites qui contiennent un seul élément de dimension &quot;Page&quot; unique.

Par exemple, prenons l’exemple suivant de deux visites d’accès. La dimension de votre rapport est la section [](../dimensions/site-section.md)Site.

* Un visiteur affiche deux pages, mais elles se trouvent toutes deux dans la même section du site. Comme la section du site est restée la même pendant la visite, elle compte comme un accès unique. Elle ne compte pas comme une visite sur une seule page, car la visite contient plusieurs éléments de dimension Page uniques.
* Un visiteur affiche deux pages dans différentes sections du site, mais il se trouve que les deux pages portent le même nom. La visite ne compte pas comme un accès unique car il existe deux valeurs de section de site uniques. Il compte comme une visite d’une seule page car il n’y avait qu’un seul élément de dimension Page unique.
