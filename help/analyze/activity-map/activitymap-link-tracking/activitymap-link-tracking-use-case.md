---
description: Vous pouvez différencier des liens en personnalisant l’ID de lien à l’aide de la variable s_objectID, en personnalisant la région et le fichier du module Activity Map d’AppMeasurement.
title: Différenciation de plusieurs liens se rapportant au même ID de lien et à la même région
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: User, Admin
exl-id: 43fe4eb9-08fe-4e20-bc02-3f712c3dec1d
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 57%

---

# Différenciation de plusieurs liens se rapportant au même ID de lien et à la même région

Vous pouvez différencier des liens en personnalisant l’ID de lien à l’aide de la variable s_objectID, en personnalisant la région et le fichier du module Activity Map d’AppMeasurement.

Par exemple, admettons que vous possédiez plusieurs liens « Buy » identifiés par Activity Map sous le même ID de lien et la même région :

<table id="table_3020E2C0175D455C84E794CF51BE5A93">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Exemple de code </th>
   <th colname="col2" class="entry"> ID de lien </th>
   <th colname="col3" class="entry"> Région </th>
  </tr>
 </thead>
  <tbody>
  <tr>
   <td colname="col1">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td>
   <td colname="col2">
     <br/>
     <br/>
    Acheter<br/>
     <br/>
     <br/>
    Acheter<br/>
     <br/>
     <br/>
    Acheter<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

Comment pouvez-vous personnaliser votre page web et le balisage pour différencier les valeurs de ces liens ? Trois options s’offrent à vous : vous pouvez personnaliser l’ID de lien, la région ou le fichier du module Activity Map d’AppMeasurement.

## Personnalisation de l’ID de lien à l’aide de s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

En créant un identifiant d’objet unique, `s_objectID`, pour un lien ou un emplacement de lien sur une page, vous pouvez améliorer le suivi du Activity Map ou utiliser Activity Map pour créer des rapports sur un emplacement ou un type de lien plutôt que sur l’URL du lien. Pour plus d’informations sur la variable , rendez-vous [ici](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=fr).`s_objectID`

>[!IMPORTANT]
>
>Notez qu’un point-virgule de fin (`;`) est requis lors de l’utilisation de `s_objectID` en Activity Map.

<table id="table_9439A5F320304E439A19842CF3EBA456">
 <thead>
  <tr>
   <th colname="col02" class="entry"> Exemple de code </th>
   <th colname="col2" class="entry"> ID de lien </th>
   <th colname="col3" class="entry"> Région </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt; </code><br/>
    <code>&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Product1<br/>
     <br/>
     <br/>
    Product2<br/>
     <br/>
     <br/>
    Product3<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
    recommendation panel<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Personnalisation de la région {#section_6B1EF302573B445DBAF44176D0A12DB9}

Vous pouvez personnaliser la région en vous assurant que la région de chaque lien &quot;Buy&quot; est définie. Pour ce faire, ajoutez une `"id"` à l’un des parents de chaque balise d’ancrage &quot;Buy&quot;.

>[!NOTE]
>
>Vous n’êtes pas strictement limité à la variable `"id"` comme identifiant de région. Vous pouvez également définir votre propre identifiant à l’aide de la variable JavaScript. `"s.ActivityMap.regionIDAttribute"`.

<table id="table_250DB52A869C466B942517BABA1C287B">
 <thead>
  <tr>
   <th colname="col02" class="entry"> Exemple de code </th>
   <th colname="col2" class="entry"> ID de lien </th>
   <th colname="col3" class="entry"> Région </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col02">
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Acheter<br/>
     <br/>
     <br/>
    Acheter<br/>
     <br/>
     <br/>
    Acheter<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    region a<br/>
     <br/>
     <br/>
    region b<br/>
     <br/>
     <br/>
    region c<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Personnalisation du fichier du module Activity Map d’AppMeasurement {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>Assurez-vous de tester le code modifié pour vous assurer qu’il fonctionne correctement. Adobe n’est pas responsable du comportement du code modifié.

Voici quelques exemples de fonctions de lien/région **génériques** que vous pouvez inclure (sous une forme modifiée) dans votre fichier AppMeasurement.js

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele) {
    if (ele.tagName == 'A' && ele.href) {
      return ele.href;
    }
  }
}
```

Le `linkName` est transmis pendant les appels à `s.tl()`.

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  }; 
  while ((ele && (ele = ele.parentNode))) {
    if ((className=ele.className) && classNames[className]) {
      return className;
    }
  }
  return "BODY";
}
```
