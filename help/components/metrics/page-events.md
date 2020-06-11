---
title: événements de page
description: Nombre d’actions de suivi de liens déclenchées.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# événements de page

La mesure &quot;événements de page&quot; indique le nombre de fois où un appel de suivi de liens a été effectué. Cette mesure s’avère utile lorsque vous souhaitez identifier les pages qui présentent le contenu le plus engageant. La mesure de cette mesure s’avère particulièrement utile lorsqu’un visiteur peut effectuer une action sur la page sans accéder à une nouvelle page.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les appels de suivi de liens ([`tl()`](/help/implement/vars/functions/tl-method.md)) dans une suite de rapports. Tous les types de liens sont inclus (liens personnalisés, liens de téléchargement et liens de sortie). Il n’inclut pas les appels de suivi de vue de page ([`t()`](/help/implement/vars/functions/t-method.md)).

## Comparaison avec des mesures similaires

* **événements de page par rapport aux vues[de](page-views.md)**page : Les événements de page comptabilisent le nombre d’appels de suivi de liens (`tl()`) et excluent les appels de suivi de vues de page (`t()`). Les vues de page sont le contraire ; il comptabilise le nombre d’appels de suivi de vue de page et exclut les liens.
