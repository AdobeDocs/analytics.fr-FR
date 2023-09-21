---
title: Appareils uniques
description: Nombre dʼappareils uniques.
feature: Metrics
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 91%

---

# Appareils uniques

Les &quot;appareils uniques&quot; [metric](overview.md) est un [Analyses entre appareils](../cda/overview.md) mesure qui comptabilise le nombre de périphériques uniques non identifiés et d’appareils virtuels uniques. Les appareils non identifiés sont des appareils qui ont généré des accès anonymes. Les appareils virtuels uniques sont des personnes distinctes identifiées par appareil.

## Méthode de calcul de cette mesure

Pour chaque appareil, additionnez toutes les personnes distinctes qui lui sont liées (y compris les personnes anonymes si l’appareil contient des accès non groupés).

Notez que cette mesure n’est pas égale à [Visiteurs uniques](unique-visitors.md) dans les suites de rapports autres que les analyses entre appareils. Par exemple, un appareil est partagé par 3 comptes différents. Si les 3 comptes visitent votre site dans une fenêtre de création de compte-rendu des performances, le rapport qui en résulte affiche 3 appareils uniques dans les analyses entre appareils. Les mêmes données en dehors des analyses entre appareils afficheraient 1 visiteur unique.

## Exemple

1. Sally arrive sur votre site par le biais d’une publicité sur son téléphone, mais elle n’est pas connectée.
1. Sally veut faire un achat, mais elle préférerait le faire sur l’ordinateur familial parce quʼelle y est déjà connectée. Sur l’ordinateur familial, elle effectue un achat.
1. Le lendemain, elle vérifie sa commande sur son téléphone et s’y authentifie.
1. Alice, la femme de Bob, navigue sur votre site en se connectant à son compte sur l’ordinateur familial.
1. Le frère de Bob, Charles, navigue également sur votre site en se connectant à son compte sur l’ordinateur familial.

![Nombre d’appareils uniques](/help/components/metrics/assets/Unique_Devices_Count.png)

Lʼaffichage de ces données dans une suite de rapports virtuelle d’analyse entre appareils avant que la [Relecture](/help/components/cda/replay.md) ne regroupe potentiellement les accès non authentifiés afficherait :

* **5 appareils uniques** : 1 pour Bob non authentifié + 2 pour Bob + 1 pour Alice + 1 pour Charles
* **4 [personnes](people.md)** : 1 [personne non identifiée](unidentified-people.md) + 3 [personnes identifiées](identified-people.md).
