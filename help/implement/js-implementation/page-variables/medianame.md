---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# mediaName

Cette variable indique le nom de la vidéo ou de l’élément multimédia.


<!-- 

mediaName.xml

 -->

Elle est uniquement disponible par le biais de l’[!UICONTROL API pour l’insertion des données] et de la [!UICONTROL source de données à traitement complet].

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 64 Ko | pev3 | Vidéos ; Flux vidéo suivant ; Flux vidéo précédent ; Segments de la vidéo affichée ; Durée de consultation de la vidéo | Aucun |

**Syntaxe et valeurs possibles** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**Méthode autoTrack :**

Si vous utilisez [!UICONTROL s.Media.autoTrack], la variable *`mediaName`* ne doit pas être implémentée explicitement.  Elle est déterminée automatiquement par le code AppMeasurement pour JavaScript.

**Méthode de suivi manuel :**

Syntaxe :

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
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

```js
s.Media.close("de_bofr_1045Making_400k")
```

**Exemples** {#section_4B9584265B1A47289818141B2A88021D}

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
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**Pièges, questions et conseils** {#section_941A445BB52E4063B0F6920E61BB90DE}

* Vous ne devez appeler les méthodes de suivi de média que si le suivi du lecteur s’avère impossible à l’aide de [!UICONTROL s.Media.autoTrack] = true.
* Cette variable est stockée sous forme de variable TEXTE mySQL contrairement à VARCHAR(100).
