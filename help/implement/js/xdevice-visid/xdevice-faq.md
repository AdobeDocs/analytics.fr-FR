---
title: FAQ sur l’identification des visiteurs sur plusieurs appareils
description: Questions fréquentes sur l’identification des visiteurs sur plusieurs appareils
feature: Implementation Basics
exl-id: da972fee-fe6e-45b2-af01-50674989c375
role: Developer
TQID: 'https://experienceleague.adobe.com/RBciiyfaq671zJ51QdJJDXcekFr-lfq0WPY0UAuWoVA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 80%

---

# FAQ sur l’identification des visiteurs sur plusieurs appareils

Questions fréquentes sur l’identification des visiteurs sur plusieurs appareils.

+++Quelle est la différence entre l’identification des visiteurs sur plusieurs appareils et Analytics sur l’ensemble des appareils ?
L’identification des visiteurs sur plusieurs appareils utilise la variable `visitorID` pour relier les appareils, avec plusieurs limitations majeures. L’une des plus grandes limites de cette méthode d’identification est que les accès non authentifiés sont isolés, sauf si l’appareil a déjà été reconnu. Ces accès non authentifiés peuvent gonfler le nombre de visiteurs uniques.

Analytics sur l’ensemble des appareils est la dernière méthode d’identification des visiteurs sur plusieurs appareils d’Adobe. Il utilise le service Experience Cloud ID et le groupement basé sur les champs pour regrouper rétroactivement les visites de différents appareils. CDA exige l’utilisation de la fonction `setCustomerIDs` pour déterminer les appareils utilisés par le même visiteur.
+++

+++Comment l’identification des visiteurs sur plusieurs appareils gère-t-elle les segments ?
L’identification des visiteurs sur plusieurs appareils traite les segments de la même manière que d’autres fonctionnalités. Il examine chaque accès individuel pour voir s’il correspond aux critères du segment et inclut ces accès dans vos données s’ils correspondent. Les segments qui utilisent des conteneurs basés sur les visites et les visiteurs continuent de consulter l’identifiant visiteur. Assurez-vous que votre mise en œuvre utilise la variable `visitorID` à chaque fois que c’est possible pour identifier de manière cohérente les visiteurs uniques en vue de la segmentation.
+++
