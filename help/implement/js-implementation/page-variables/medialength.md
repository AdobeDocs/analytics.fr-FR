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


# mediaLength

La variable définit la longueur totale du média en cours de lecture.


<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
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
   <td> Pas de taille maximale pour la requête pev3 complète ; la taille est limitée à la longueur maximale de l’URL du navigateur. </td> 
   <td> pev3 </td> 
   <td> Durée de consultation de la vidéo ; <p>Segments de vidéo affichés </p> </td> 
   <td> Aucun </td> 
  </tr> 
 </tbody> 
</table>

**Syntaxe et valeurs possibles** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

**Méthode autoTrack :**

Si vous utilisez [!UICONTROL s.Media.autoTrack], la variable [!UICONTROL mediaLength] ne doit pas être implémentée explicitement. Elle est déterminée automatiquement par le code AppMeasurement pour JavaScript.

**Méthode de suivi manuel :**

Syntaxe :

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valeurs possibles:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Exemples** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Pièges, questions et conseils** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* Vous ne devez appeler les méthodes de suivi de média que si le suivi du lecteur s’avère impossible à l’aide de [!UICONTROL s.Media.autoTrack] = true.
* Si le suivi n’est pas effectué à l’aide de la méthode [!UICONTROL autoTrack], veillez à définir la durée en secondes.

