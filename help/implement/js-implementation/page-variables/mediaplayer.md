---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# mediaPlayer

Cette variable indique le lecteur utilisé pour exécuter une vidéo ou un élément multimédia.


<!-- 

mediaPlayer.xml

 -->

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | pev3 | Lecteurs vidéo | Aucun |

**Syntaxe et valeurs possibles** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**Méthode autoTrack :**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**Méthode de suivi manuel :**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valeurs possibles:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Exemples** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Pièges, questions et conseils** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

Vous ne devez appeler les méthodes de suivi de média que si le suivi du lecteur s’avère impossible à l’aide de s.Media.autoTrack = true.

