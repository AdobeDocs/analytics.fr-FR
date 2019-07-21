---
description: 'Vous pouvez différencier des liens en personnalisant l’ID de lien à l’aide de la variable s_objectID, en personnalisant la région et le fichier du module Activity Map d’AppMeasurement. '
seo-description: Vous pouvez différencier des liens en personnalisant l’ID de lien à l’aide de la variable s_objectID, en personnalisant la région et le fichier du module Activity Map d’AppMeasurement.
seo-title: Différenciation des liens faisant référence au même ID de lien et région
solution: Analytics
title: Différenciation des liens faisant référence au même ID de lien et région
topic: Activity Map
uuid: f 2 da 0 cda-a 33 b -4 a 12-8 d 99-1 f 58386 d 6 d 30
translation-type: tm+mt
source-git-commit: 4f313ae50c4d5a0f3bfec493c2d554bc8614aeef

---


# Différenciation des liens faisant référence au même ID de lien et région

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
    <code>&lt; div id = "recommendation panel" &gt; 
 &lt; div &gt; 
 &lt; a href = "product1.html" &gt; Acheter &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a href = "product2.html" &gt; Acheter &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a href = "product3.html" &gt; Acheter &lt;/a &gt; 
 &lt;/div &gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p> </p>Buy <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p> </p>recommendation panel <p> </p> <p> </p> <p>recommendation panel </p> <p> </p> <p> </p> <p>recommendation panel </p> </td> 
  </tr> 
 </tbody> 
</table>

Comment pouvez-vous personnaliser votre page web et le balisage pour différencier les valeurs de ces liens ? Trois options s’offrent à vous : vous pouvez personnaliser l’ID de lien, la région ou le fichier du module Activity Map d’AppMeasurement.

## Personnalisation de l’ID de lien à l’aide de s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

En créant un identifiant d’objet unique pour un lien ou emplacement de lien sur une page, vous pouvez améliorer le suivi d’Activity Map ou utiliser Activity Map pour créer des rapports sur un emplacement ou un type de lien plutôt que sur l’URL du lien. Pour plus d’informations sur la variable s_objectID, rendez-vous [ici](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html).

>[!IMPORTANT]
>
>Notez qu'un point-virgule de fin (;) est requis lors de l'utilisation de s_ objectid dans Carte d'activités.

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
    <code>&lt; div id = "recommendation panel" &gt; 
 &lt; div &gt; 
 &lt; a onclick = « s_ objectid ='Product 1 ';  » href = "product1.html" &gt; Acheter &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a onclick = « s_ objectid ='Product 2 ';  » href = "product2.html" &gt; Acheter &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a onclick = « s_ objectid ='Product 3 ';  » href = "product3.html" &gt; Acheter &lt;/a &gt; 
 &lt;/div &gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p>Product1 <p> </p> <p> </p> <p>Product2 </p> <p> </p> <p> </p> <p>Product3 </p> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p>recommendation panel </p> <p> </p> <p> </p> <p>recommendation panel </p> <p> </p> <p> </p> <p>recommendation panel </p> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Personnalisation de la région {#section_6B1EF302573B445DBAF44176D0A12DB9}

Vous pouvez personnaliser la région en vous assurant que la région de chaque lien « Buy » est définie. Pour ce faire, ajoutez un paramètre « id » à l’un des parents de chaque balise d’ancrage « Buy ».

>[!NOTE]
>
>Vous n'êtes pas strictement limité au paramètre « id » comme identifiant de région. Vous pouvez également définir votre propre identifiant à l'aide de la variable JavaScript « s. activitymap. regionidattribute ».

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
    <code>&lt; div id = "recommendation panel" &gt; 
 &lt; div id = "region a" &gt; 
 &lt; a href = "product1.html" &gt; Acheter &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div id = "region b" &gt; 
 &lt; a href = "product2.html" &gt; Acheter &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div id = "region c" &gt; 
 &lt; a href = "product3.html" &gt; Acheter &lt;/a &gt; 
 &lt;/div &gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p>region a <p> </p> <p> </p> <p>region b </p> <p> </p> <p> </p> <p>region c </p> </td> 
  </tr> 
 </tbody> 
</table>

## Personnalisation du fichier du module Activity Map d’AppMeasurement {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>Assurez-vous de tester le code modifié pour vous assurer qu'il fonctionne correctement. Adobe n’est pas responsable du comportement du code modifié.

Voici quelques exemples de fonctions** generic** link/region que vous pouvez inclure (sous forme de formulaire modifié) dans votre fichier appmeasurement. js.

```
s.ActivityMap.link = function(ele,linkName){ 
if(linkName){ 
return linkName; 
} 
if(ele){ 
if(ele.tagName == 'A' && ele.href){ 
return ele.href; 
} 
} 
} 
```

La variable linkName est transmise à s.tl lors des appels.

```
s.ActivityMap.region = function(ele){ 
var className, 
classNames = { 
'header': 1, 
'navbar': 1, 
'left-content': 1, 
'main-content': 1, 
'footer': 1, 
}; 
  while( (ele && (ele = ele.parentNode))){ 
if( (className=ele.className) && classNames[className]){ 
return className; 
} 
} 
return "BODY"; 
} 
```

