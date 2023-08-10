---
title: Événements de page
description: Nombre d’actions de suivi des liens déclenchées.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: 5e70a84c7793b516c0eca2776d8bbfd3ea3fc02b
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 60%

---

# Événements de page

La mesure « Événements de page » indique le nombre de fois où un appel de suivi des liens a été effectué. Cette mesure s’avère utile lorsque vous souhaitez identifier les pages qui présentent le contenu le plus engageant. Le calcul de cette mesure s’avère particulièrement utile lorsqu’un visiteur peut effectuer une action sur la page sans accéder à une nouvelle page.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les [Appels de suivi de liens (`tl()`)](/help/implement/vars/functions/tl-method.md) dans une suite de rapports. Tous les types de liens sont inclus (liens personnalisés, liens de téléchargement et liens de sortie). Elle n’inclut pas [Appels de suivi des pages vues (`t()`)](/help/implement/vars/functions/t-method.md).

## Comparaison avec des mesures similaires

* **Événements de page et [Pages vues](page-views.md)**: les événements de page comptabilisent le nombre d’appels de suivi des liens (`tl()`) et exclure les appels de suivi de pages vues (`t()`). Les pages vues sont l’inverse : elles comptabilisent le nombre d’appels de suivi de pages vues et excluent les liens.
