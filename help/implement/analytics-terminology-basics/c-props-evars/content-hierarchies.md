---
description: Les hiérarchies du contenu servent le plus souvent à présenter les différents chemins que les visiteurs ont empruntés à partir d’une page, d’un niveau, etc.
keywords: Implémentation d'Analytics ; hiérarchies de contenu ; hier
seo-description: Les hiérarchies du contenu servent le plus souvent à présenter les différents chemins que les visiteurs ont empruntés à partir d’une page, d’un niveau, etc.
seo-title: Décompte des hiérarchies du contenu
solution: Analytics
title: Décompte des hiérarchies du contenu
topic: Développeur et mise en œuvre
uuid: d 41 df 92 d -65 fb -44 de-bf 46-8 fac 24303 papa
translation-type: tm+mt
source-git-commit: 1bc1c7a1e00d7b59cd39f368ac9afb745bea9e47

---


# Décompte des hiérarchies du contenu

Les hiérarchies du contenu servent le plus souvent à présenter les différents chemins que les visiteurs ont empruntés à partir d’une page, d’un niveau, etc.

**Comment dois-je effectuer le suivi de ma[!UICONTROL hiérarchie du contenu] ?**

Vous devez, tout d’abord, comprendre les exigences, en termes de génération de rapports, liées au suivi des [!UICONTROL hiérarchies du contenu]. Si les exigences de suivi de la hiérarchie sont très détaillées, il est, le plus souvent, conseillé d’utiliser la variable de hiérarchie ( *`hier`*) est recommandée. Les hiérarchies nécessitent généralement une stricte taxonomie prédéfinie, dans laquelle un même nœud enfant réside rarement sous plusieurs nœuds parents. Examinez l’exemple suivant :

[!UICONTROL Hiérarchie mondiale]

Tous les sites &gt; Régions &gt; Pays &gt; Langue &gt; Catégorie

Dans cet exemple, la ventilation de la hiérarchie peut débuter au niveau de la langue. Si une exigence consiste à fournir un rapport sur le trafic global en langue anglaise, le problème peut se présenter si Anglais apparaît sous Etats-Unis, Angleterre, Australie, etc. Les hiérarchies vous permettent uniquement d’effectuer des explorations. Pour qu’il soit possible de réaliser des découpes horizontales à travers plusieurs catégories, la bonne pratique consiste à utiliser une [!UICONTROL variable de trafic personnalisé] (prop).

Si vous souhaitez permettre aux utilisateurs d’explorer le site (de la même manière qu’ils naviguent) et de fournir un rapport sur les [!UICONTROL visiteurs uniques] à chaque niveau de la hiérarchie, il est conseillé d’opter pour la variable de hiérarchie.

Dans certaines occasions, l’utilisation simultanée des propriétés et de la variable *`hier`* est pertinente. Vous trouverez ci-dessous la prop prise en charge pour chaque type de variable :

<table id="table_E960D100DA0F433A94A4B246D6EF0D0A"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> Props </th> 
   <th class="entry"> Hiérarchie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Corrélations </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_2A70A61A78024204B6CEE4FFF9A0851E" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Cheminement </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_EE5ED36AC75F4D648F54858D796F82BD" /> </p> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Page vue </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_5BB82776D41642E78C2ECFD71DD33164" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_18F34EE8957946AF9D6C2C9B492CEDB7" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Visiteurs uniques </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_A475267547B94DB4A1EEFD903B2CA1EB" /> </p> </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_1E9E302D999146128CDBCE13E52BC38C" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Classifications </td> 
   <td> <p><img  src="assets/check-mark.png" id="image_FC5FEFE7BA8C4475BA4F31D57302BE6B" /> </p> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

