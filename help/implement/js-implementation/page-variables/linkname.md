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



# linkName

La variable  est facultative et utilisée dans le [!UICONTROL suivi des liens]. Elle détermine le nom d’un lien personnalisé, de téléchargement ou de sortie.


<!-- 

linkName.xml

 -->

Normalement, la variable *`linkName`* n’est pas nécessaire, car le troisième paramètre de la fonction *`tl()`* la remplace.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
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
   <td> 100 octets </td> 
   <td> pev2 </td> 
   <td> <p>Téléchargements de fichiers </p> <p>Liens personnalisés </p> <p>Liens de sortie </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Les [!UICONTROL liens personnalisés] désignent des liens qui envoient des données de suivi. La variable *`linkName`* (ou le troisième paramètre de la fonction *`tl()`*) identifie la valeur qui apparaît dans les rapports [!UICONTROL Liens personnalisés], [!UICONTROL Liens de téléchargement] ou [!UICONTROL Liens de sortie]. Si la valeur *`linkName`* n’est pas renseignée, l’URL du lien apparaît dans le rapport.

**Syntaxe et valeurs possibles** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

*`linkName`* n’est concerné par aucune limite, à l’exception des limites standard.

**Exemples** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**Paramètres de configuration** {#section_F15FF429FC274F708D50DF79D4668EA3}

Aucun

**Pièges, questions et conseils** {#section_170A78452A7340B5B229713AC1FB71FA}

* La variable *`linkName`* est remplacée par le troisième paramètre de la fonction *`tl()`*.

* Si la variable *`linkName`* et le troisième paramètre de la fonction *`tl()`* sont vides, l’URL complète du lien (à l’exception de la chaîne de requête) s’affiche dans le rapport (même dans le cas d’un lien relatif).
