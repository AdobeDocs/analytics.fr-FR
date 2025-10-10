---
title: FAQ sur l’identification des visiteurs sur plusieurs appareils
description: Questions fréquentes sur l’identification des visiteurs sur plusieurs appareils
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 90%

---

# FAQ sur l’identification des visiteurs sur plusieurs appareils

Questions fréquentes sur l’identification des visiteurs sur plusieurs appareils.

+++Quelle est la différence entre l’identification des visiteurs sur plusieurs appareils et Analytics sur l’ensemble des appareils ?
L’identification des visiteurs sur plusieurs appareils utilise la variable `visitorID` pour relier les appareils, avec plusieurs limitations majeures. L’une des plus grandes limites de cette méthode d’identification est que les accès non authentifiés sont isolés, sauf si l’appareil a déjà été reconnu. Ces accès non authentifiés peuvent gonfler le nombre de visiteurs uniques.

Analytics sur l’ensemble des appareils est la dernière méthode d’identification des visiteurs sur plusieurs appareils d’Adobe. Il utilise le service Experience Cloud ID et le graphique d’appareils pour assembler rétroactivement les visites de différents appareils. CDA exige l’utilisation de la fonction `setCustomerIDs` pour déterminer les appareils utilisés par le même visiteur.
+++

+++Comment l’identification des visiteurs sur plusieurs appareils gère-t-elle les segments ?
L’identification des visiteurs sur plusieurs appareils traite les segments de la même manière que d’autres fonctionnalités. Il examine chaque accès individuel pour voir s’il correspond aux critères du segment et inclut ces accès dans vos données s’ils correspondent. Les segments qui utilisent des conteneurs basés sur les visites et les visiteurs continuent de consulter l’identifiant visiteur. Assurez-vous que votre mise en œuvre utilise la variable `visitorID` à chaque fois que c’est possible pour identifier de manière cohérente les visiteurs uniques en vue de la segmentation.
+++
