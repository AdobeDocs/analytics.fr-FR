---
title: Événements de page
description: Nombre d’actions de suivi des liens déclenchées.
translation-type: ht
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: ht
source-wordcount: '143'
ht-degree: 100%

---


# Événements de page

La mesure « Événements de page » indique le nombre de fois où un appel de suivi des liens a été effectué. Cette mesure s’avère utile lorsque vous souhaitez identifier les pages qui présentent le contenu le plus engageant. Le calcul de cette mesure s’avère particulièrement utile lorsqu’un visiteur peut effectuer une action sur la page sans accéder à une nouvelle page.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)) dans une suite de rapports. Tous les types de liens sont inclus (liens personnalisés, liens de téléchargement et liens de sortie). Elle n’inclut pas les appels de suivi de pages vues ([`t()`](/help/implement/vars/functions/t-method.md)).

## Comparaison avec des mesures similaires

* **Événements de page par rapport aux [Pages vues](page-views.md)** : les événements de page comptabilisent le nombre d’appels de suivi des liens (`tl()`) et excluent les appels de suivi de pages vues (`t()`). Les pages vues ont un fonctionnement contraire : elles comptabilisent le nombre d’appels de suivi de pages vues et excluent les liens.
