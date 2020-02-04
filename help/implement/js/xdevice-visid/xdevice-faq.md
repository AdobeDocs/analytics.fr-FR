---
title: FAQ sur l’identification des visiteurs sur plusieurs périphériques
description: Questions fréquentes sur l’identification des visiteurs sur plusieurs périphériques
translation-type: tm+mt
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# FAQ sur l’identification des visiteurs sur plusieurs périphériques

Questions fréquentes sur l’identification des visiteurs sur plusieurs périphériques.

**Quelle est la différence entre l’identification des visiteurs sur plusieurs périphériques et Analytics sur plusieurs périphériques ?**

L’identification des visiteurs sur plusieurs périphériques utilise la `visitorID` variable pour relier les périphériques, avec plusieurs limitations majeures. L’une des plus grandes limites de cette méthode d’identification est que les accès non authentifiés sont isolés, sauf si le périphérique a déjà été reconnu. Ces accès non authentifiés peuvent gonfler le nombre de visiteurs uniques.

Analytics sur plusieurs périphériques est la dernière méthode d’identification des visiteurs sur plusieurs périphériques d’Adobe. Il utilise le service d’ID d’expérience et le graphique de périphériques pour assembler rétroactivement les visites de différents périphériques. CDA exige l’utilisation de la `setCustomerIDs` fonction pour déterminer les périphériques utilisés par le même visiteur.

**Comment l’identification des visiteurs sur plusieurs périphériques gère-t-elle les segments ?**

L’identification des visiteurs sur plusieurs périphériques traite les segments de la même manière que d’autres fonctionnalités. Il examine chaque accès individuel pour voir s’il correspond aux critères du segment et inclut ces accès dans vos données s’il correspond. Les segments qui utilisent des conteneurs basés sur les visites et les visiteurs continuent de consulter l’identifiant visiteur. Assurez-vous que votre implémentation utilise la `visitorID` variable chaque fois que possible pour identifier de manière cohérente les visiteurs uniques en vue de la segmentation.
