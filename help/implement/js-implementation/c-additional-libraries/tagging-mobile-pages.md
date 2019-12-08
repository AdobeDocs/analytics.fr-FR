---
description: Le code de suivi mobile est placé sur la page sous la forme d’une balise d’image générée par le serveur.
keywords: Analytics Implementation;mobile tracking;mobile protocols;prevent caching;alt tag;default image type
title: Balisage de pages pour les protocoles mobiles
topic: Developer and implementation
uuid: 5788beaf-f309-4918-a99c-a3e591668205
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Balisage de pages pour les protocoles mobiles

Le code de suivi mobile est placé sur la page sous la forme d’une balise d’image générée par le serveur.

Le code de suivi mobile est placé sur la page sous la forme d’une balise d’image générée par le serveur. Dans la mesure où les langages de script tels que JavaScript et WMLScript ne sont pas pris en charge par tous les périphériques mobiles, la balise Web de suivi ne peut pas être générée de manière dynamique via un langage de script.

Bien que la taille de l’image de balise mobile soit effectivement de 2x2 pixels, afin de garantir une prise en charge par l’ensemble des périphériques mobiles, vous devez définir les propriétés de hauteur et de largeur sur 5. Par exemple :

```
<img sr c="https://metric.mydomain.com/b/ss/<Report_Suite_Name>/5/<random_number>?pageName=" alt="" width="5" height="5"/>
```

## Utilisation d’un nombre aléatoire pour empêcher la mise en cache {#section_BF5C344A16034C439C8704632CF673A7}

Bien que les serveurs Adobe donnent aux navigateurs l’instruction de ne pas mettre en cache la balise Web de suivi, tous les navigateurs ne la suivent pas. Pour empêcher cette mise en cache, il est recommandé que le serveur Web génère de manière dynamique un nombre aléatoire dans le chemin de l’URL d’image. Ainsi, une plus grande précision des rapports est garantie. Le nombre aléatoire doit se trouver dans la dernière section du chemin, comme illustré dans cet exemple :

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" />.
```

## Inclusion d’une balise ALT {#section_FBD8B2FD1EA0429580C2B933DA300B07}

Certains navigateurs mobiles requièrent que toutes les images possèdent du texte de remplacement dans la balise d’image. L’exemple suivant montre comment l’attribut ALT doit apparaître dans la balise d’image :

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" alt=""/>.
```

Il est important que l’élément /5/ apparaisse toujours correctement dans le chemin. Il permet aux serveurs Adobe d’identifier les périphériques mobiles. Si l’élément /1/ standard est utilisé, les serveurs Adobe tentent de définir un cookie sur le périphérique mobile.

## Modification du type d’image par défaut {#section_2F969909010D4A64BF6E092A32ABADB7}

Si le type d’image par défaut n’est pas pris en charge sur un périphérique donné, aucune donnée n’est renvoyée. Pour éviter ce cas de figure, vous pouvez forcer le serveur de collecte de données Adobe à renvoyer un type de graphique bien spécifique pris en charge par le périphérique mobile. Le code qui suit le nom de la suite de rapports indique le type d’image :

* `/5/` renvoie le type d’image par défaut.
* `/5.1/` ou `/1/` renvoie toujours une image GIF.

* `/5.5/` renvoie toujours une image WBMP.

Reportez-vous à la section [Identification des visiteurs qui utilisent des protocoles mobiles](/help/implement/js-implementation/c-unique-visitors/visid-mobile.md).
