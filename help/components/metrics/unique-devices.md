---
title: Appareils uniques
description: Nombre dʼappareils uniques.
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: 407111f6016fe8595f1d5c3464e36dfd4d314630
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 6%

---

# Appareils uniques

La mesure &quot;Appareils uniques&quot; est une mesure [Analyses entre appareils](../cda/overview.md) qui comptabilise le nombre d’appareils non identifiés uniques et d’appareils virtuels uniques. Les périphériques non identifiés sont des périphériques qui ont généré des accès anonymes. Les périphériques virtuels uniques sont des personnes distinctes identifiées par chaque périphérique.

## Méthode de calcul de cette mesure

Pour chaque appareil, additionnez toutes les personnes distinctes qui lui sont liées (y compris les personnes anonymes si l’appareil contient des accès non assemblés).

Notez que cette mesure n’est pas égale à [Visiteurs uniques](unique-visitors.md) dans les suites de rapports autres que les analyses entre appareils. Par exemple, un appareil est partagé par 3 comptes différents. Si les 3 comptes visitent votre site dans une fenêtre de création de rapports, le rapport qui en résulte affiche 3 périphériques uniques dans les analyses entre appareils. Les mêmes données en dehors des analyses entre appareils afficheraient 1 visiteur unique.

## Exemple

1. Bob arrive sur votre site par le biais d’une publicité, mais il n’est pas connecté.
1. Bob veut faire un achat, mais il préférerait le faire sur l&#39;ordinateur de la famille parce qu&#39;il y est déjà connecté. Sur l&#39;ordinateur familial, il fait un achat.
1. Le lendemain, il vérifie sa commande sur son téléphone et s&#39;y authentifie.
1. Alice, la femme de Bob, navigue sur votre site en se connectant à son compte sur l&#39;ordinateur de la famille.
1. Le frère de Bob, Charles, navigue également sur votre site en se connectant à son compte sur l&#39;ordinateur de la famille.

![Nombre d’appareils uniques](/help/components/metrics/assets/Unique_Devices_Count.png)

L’affichage de ces données dans une suite de rapports virtuelle des analyses entre appareils avant [Relecture](/help/components/cda/replay.md) affiche :

* **5 appareils** uniques : 1 pour Bob non authentifié + 2 pour Bob + 1 pour Alice + 1 pour Charles
* **4  [personnes](people.md)** : 1  [Personnes non identifiées](unidentified-people.md)  + 3 personnes  [identifiées](identified-people.md).

