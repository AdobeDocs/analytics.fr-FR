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



# linkType

La variable est une variable facultative utilisée dans le cadre du suivi des liens. Elle détermine le rapport dans lequel un nom de lien ou une URL doit apparaître (liens personnalisés, de téléchargement ou de sortie).


<!-- 

linkType.xml

 -->

Normalement, la variable *`linkType`* n’est pas nécessaire, car le second paramètre de la fonction *`tl()`* la remplace.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
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
   <td> Un seul caractère </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>Téléchargements de fichiers </p> <p>Liens personnalisés </p> <p>Liens de sortie </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Les liens personnalisés envoient des données à Analytics. La variable *`linkType`* (ou le second paramètre de la fonction *`tl()`*) est utilisée pour identifier le rapport dans lequel le nom du lien ou de l’URL apparaît (Rapports de liens [!UICONTROL personnalisés], de [!UICONTROL téléchargement] ou de [!UICONTROL sortie]).

Pour les liens de sortie et de téléchargement, la variable *`linkType`* est automatiquement renseignée selon que le lien sur lequel l’utilisateur a cliqué est un lien de sortie ou de téléchargement. Un lien personnalisé peut être configuré pour envoyer des données à l’un des trois rapports avec cette variable ou avec le deuxième paramètre de la fonction *`tl()`*. En définissant *`linkType`* sur « o », « e » ou « d », l’URL de *`linkName`* ou du lien est envoyée respectivement au rapport [!UICONTROL Liens personnalisés], [!UICONTROL Liens de sortie] ou [!UICONTROL Téléchargements de fichiers].

**Syntaxe et valeurs possibles** {#section_18DB3A8083FB4F75B970055ED336DA4E}

La syntaxe de la variable *`linkType`* est différente selon si vous utilisez du code XML ou une chaîne de requête.

Si vous utilisez du code XML, la variable ne peut contenir qu’un seul caractère, à savoir « o », « e » ou « d ».

```js
s.tl(this,'o','Link Name');
```

Si vous utilisez la chaîne de requête `pe`, vous devez recourir à `lnk_d`, `lnk_e` ou `lnk_o`.

**Exemples** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**Paramètres de configuration** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

Aucun

**Pièges, questions et conseils** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* Si la valeur *`linkType`* n’est pas spécifiée, les liens personnalisés (« o ») sont supposés.
