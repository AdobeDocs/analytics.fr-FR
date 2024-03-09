---
title: Événements de page
description: Nombre d’actions de suivi des liens déclenchées.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: 205d86b13046bd17e321734904bf57435ef6e106
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 33%

---

# Événements de page

Les &quot;Événements de page&quot; [metric](overview.md) indique le nombre de fois où un appel de suivi des liens a été effectué. Cette mesure s’avère utile lorsque vous souhaitez identifier les pages qui présentent le contenu le plus engageant. Le calcul de cette mesure s’avère particulièrement utile lorsqu’un visiteur peut effectuer une action sur la page sans accéder à une nouvelle page.

Par exemple, dans un parcours type d’un site d’e-commerce, un visiteur peut avoir plusieurs interactions sur une seule page. Ces interactions sont généralement configurées en tant que suivi des liens dans une mise en oeuvre Analytics standard ([`tl()`](/help/implement/vars/functions/tl-method.md)), lors d’une vue de page ([`t()`](/help/implement/vars/functions/t-method.md)) est réservé au chargement initial de la page. Cette méthode d’implémentation fournit un suivi d’événement enrichi qui fournit des informations sur les interactions qui se produisent avant qu’un visiteur ne continue son parcours.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)) dans une suite de rapports. Tous les types de lien sont inclus dans cette mesure, en particulier [Liens personnalisés](../dimensions/custom-link.md), [Liens de téléchargement](../dimensions/download-link.md), et [Liens de sortie](../dimensions/exit-link.md). Elle n’inclut pas les appels de page vue ([`t()`](/help/implement/vars/functions/t-method.md)).

## Comparaison avec des mesures similaires

* **Événements de page et [Pages vues](page-views.md)**: les événements de page comptabilisent le nombre d’appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)) et exclure les appels de suivi de pages vues ([`t()`](/help/implement/vars/functions/t-method.md)). Les pages vues sont l’inverse : elles comptabilisent le nombre d’appels de suivi de pages vues et excluent les liens.
