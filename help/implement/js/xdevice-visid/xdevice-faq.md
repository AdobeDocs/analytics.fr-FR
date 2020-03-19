---
title: FAQ sur l’identification des visiteurs sur plusieurs appareils
description: Questions fréquentes sur l’identification des visiteurs sur plusieurs appareils
translation-type: ht
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# FAQ sur l’identification des visiteurs sur plusieurs appareils

Questions fréquentes sur l’identification des visiteurs sur plusieurs appareils.

**Quelle est la différence entre l’identification des visiteurs sur plusieurs appareils et Analytics sur plusieurs appareils ?**

L’identification des visiteurs sur plusieurs appareils utilise la variable `visitorID` pour relier les appareils, avec plusieurs limitations majeures. L’une des plus grandes limites de cette méthode d’identification est que les accès non authentifiés sont isolés, sauf si l’appareil a déjà été reconnu. Ces accès non authentifiés peuvent gonfler le nombre de visiteurs uniques.

Analytics sur plusieurs appareils est la dernière méthode d’identification des visiteurs sur plusieurs appareils d’Adobe. Il utilise le service Experience Cloud ID et le graphique d’appareils pour assembler rétroactivement les visites de différents appareils. CDA exige l’utilisation de la fonction `setCustomerIDs` pour déterminer les appareils utilisés par le même visiteur.

**Comment l’identification des visiteurs sur plusieurs appareils gère-t-elle les segments ?**

L’identification des visiteurs sur plusieurs appareils traite les segments de la même manière que d’autres fonctionnalités. Il examine chaque accès individuel pour voir s’il correspond aux critères du segment et inclut ces accès dans vos données s’ils correspondent. Les segments qui utilisent des conteneurs basés sur les visites et les visiteurs continuent de consulter l’identifiant visiteur. Assurez-vous que votre mise en œuvre utilise la variable `visitorID` chaque fois que possible pour identifier de manière cohérente les visiteurs uniques en vue de la segmentation.
