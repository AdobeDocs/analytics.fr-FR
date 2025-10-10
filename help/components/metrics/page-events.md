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

La [mesure](overview.md) « Événements de page » indique le nombre de fois où un appel de suivi des liens a été effectué. Cette mesure s’avère utile lorsque vous souhaitez identifier les pages qui présentent le contenu le plus engageant. Le calcul de cette mesure s’avère particulièrement utile lorsqu’un visiteur peut effectuer une action sur la page sans accéder à une nouvelle page.

Par exemple, dans un parcours type d’un site d’e-commerce, un visiteur peut avoir plusieurs interactions sur une seule page. Une implémentation Analytics standard inclut ces interactions configurées comme un appel de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)), tandis qu’un appel de page vue ([`t()`](/help/implement/vars/functions/t-method.md)) est réservé au chargement initial de la page. Cette méthode d’implémentation fournit un suivi d’événement enrichi qui fournit insight sur les interactions qui se produisent avant qu’un visiteur ne poursuive son parcours.

## Méthode de calcul de cette mesure

Cette mesure comptabilise tous les appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)) dans une suite de rapports. Tous les types de liens sont inclus dans cette mesure, en particulier [Liens personnalisés](../dimensions/custom-link.md), [Liens de téléchargement](../dimensions/download-link.md) et [Liens de sortie](../dimensions/exit-link.md). Il n’inclut pas les appels de page vue ([`t()`](/help/implement/vars/functions/t-method.md)).

## Comparaison avec des mesures similaires

* **Événements de page par rapport à [Pages vues](page-views.md)** : les événements de page comptabilisent le nombre d’appels de suivi des liens ([`tl()`](/help/implement/vars/functions/tl-method.md)) et excluent les appels de suivi des pages vues ([`t()`](/help/implement/vars/functions/t-method.md)). Les pages vues sont l’inverse : il comptabilise le nombre d’appels de suivi des pages vues et exclut les liens.
