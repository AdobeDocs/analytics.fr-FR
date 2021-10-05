---
title: Appareils uniques
description: Nombre dʼappareils uniques.
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: db88bd439c036e97cca641f31f4fc3101a368636
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 93%

---

# Appareils uniques

La mesure « Appareils uniques » est une mesure d&#39;[analyse entre appareils](../cda/overview.md) qui comptabilise le nombre d’appareils non identifiés uniques et d’appareils virtuels uniques. Les appareils non identifiés sont des appareils qui ont généré des accès anonymes. Les appareils virtuels uniques sont des personnes distinctes identifiées par appareil.

## Méthode de calcul de cette mesure

Pour chaque appareil, additionnez toutes les personnes distinctes qui lui sont liées (y compris les personnes anonymes si l’appareil contient des accès non groupés).

Notez que cette mesure n’est pas égale à [Visiteurs uniques](unique-visitors.md) dans les suites de rapports autres que les analyses entre appareils. Par exemple, un appareil est partagé par 3 comptes différents. Si les 3 comptes visitent votre site dans une fenêtre de création de compte-rendu des performances, le rapport qui en résulte affiche 3 appareils uniques dans les analyses entre appareils. Les mêmes données en dehors des analyses entre appareils afficheraient 1 visiteur unique.

## Exemple

1. Bob arrive sur votre site par le biais d’une publicité sur son téléphone, mais il n’est pas connecté.
1. Bob veut faire un achat, mais il préférerait le faire sur l’ordinateur familial parce qu’il y est déjà connecté. Sur l’ordinateur familial, il effectue un achat.
1. Le lendemain, il vérifie sa commande sur son téléphone et s’y authentifie.
1. Alice, la femme de Bob, navigue sur votre site en se connectant à son compte sur l’ordinateur familial.
1. Le frère de Bob, Charles, navigue également sur votre site en se connectant à son compte sur l’ordinateur familial.

![Nombre d’appareils uniques](/help/components/metrics/assets/Unique_Devices_Count.png)

L’affichage de ces données dans une suite de rapports virtuelle CDA avant [Lecture](/help/components/cda/replay.md) pouvant potentiellement assembler des accès non authentifiés présenterait :

* **5 appareils uniques** : 1 pour Bob non authentifié + 2 pour Bob + 1 pour Alice + 1 pour Charles
* **4 [personnes](people.md)** : 1 [personne non identifiée](unidentified-people.md) + 3 [personnes identifiées](identified-people.md).
