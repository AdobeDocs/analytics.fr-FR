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


# mediaSession

Cette variable indique les segments lus d’une vidéo ou d’une ressource multimédia.


<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> Taille maximale </th> 
   <th class="entry"> Paramètre du débogueur </th> 
   <th class="entry"> Rapports renseignés </th> 
   <th class="entry"> Valeur par défaut </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 octets </td> 
   <td> pev3 </td> 
   <td> Durée de consultation de la vidéo <p>Segments de vidéo affichés </p> </td> 
   <td> Aucun </td> 
  </tr> 
 </tbody> 
</table>

**Syntaxe et valeurs possibles** {#section_9A63266633C4427CB4A6549E4D887B85}

**Méthode autoTrack :**

Si vous utilisez [!UICONTROL s.Media.autoTrack], la *`mediaName`* ne doit pas être implémentée explicitement.  Elle est déterminée automatiquement par le code AppMeasurement pour JavaScript.

**Méthode de suivi manuel :**

du lien personnalisé:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

Valeurs possibles:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**Exemples** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**Pièges, questions et conseils** {#section_1BCEB037AB724B6EBE87420BD3604B88}

Vous ne devez appeler les méthodes de suivi de média que si le suivi du lecteur s’avère impossible à l’aide de [!UICONTROL s.Media.autoTrack] = true.
