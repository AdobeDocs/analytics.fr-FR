---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: ce200ed36f8c61d2870ea1500664673fa1cc4b5e

---


# Variable de liste

Connue également sous le nom de variable de liste. A l’instar de la fonction Propriétés de liste, les variables de liste autorisent plusieurs valeurs dans la même demande d’image. Elles se comportent également de la même manière que les eVars, lesquelles persistent au-delà de la demande d’image sur laquelle elles ont été définies. Vous pouvez utiliser ces variables pour afficher les causes et les effets parmi plusieurs éléments sur une seule page, tels que des listes de produits, de cadeaux, d’affinements de recherche ou encore d’annonces graphiques.

<!-- 

listN.xml (bob edit)

 -->

**Considérations**

* Elles mémorisent leurs valeurs spécifiques en référençant le cookie VisitorID dans le navigateur du visiteur.
* 250 valeurs au maximum sont stockées à la fois par visiteur. Si cette limite de 250 valeurs par visiteur est dépassée, seules les 250 dernières valeurs sont utilisées. L’expiration de ces valeurs dépend de l’expiration configurée pour la variable.
* Chaque valeur délimitée peut contenir, au maximum, 255 caractères (ou moins en cas d’utilisation de caractères codés sur plusieurs octets). Il s’agit de la longueur maximale de chaque élément.
* Le nombre de caractères de cette variable n’est pas limité. La seule exception concerne les anciens navigateurs Internet Explorer qui imposent une limite de 2 083 caractères à toutes les demandes d’URL.
* Au total, trois variables de liste sont disponibles par suite de rapports.
* Le code H23 ou ultérieur est nécessaire pour utiliser des variables de liste.
* Les variables de liste peuvent être classifiées.
* Si des valeurs en double sont définies dans une même demande d’image, les variables de liste dédupliquent toutes les instances de celles-ci.
* Les variables de liste les plus granulaires peuvent être segmentées au niveau des accès (ou des pages vues). Si une variable de liste contient trois valeurs dans une même demande d’image, les règles de segmentation qui correspondent à une valeur incluent les trois valeurs dans les rapports. A l’inverse, si une règle d’exclusion définie correspond à une seule valeur, les trois valeurs sont exclues.

**Configuration** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

La configuration est accessible dans Admin Console ; vous pouvez la mettre à jour sans faire appel au service à la clientèle :

1. Sélectionnez **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administration]** &gt; **[!UICONTROL Suites de rapports]**.
1. Sélectionnez la suite de rapports.
1. Cliquez sur **[!UICONTROL Modifier les paramètres]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Variables de liste]** .

* **Nom** : chaque valeur délimitée peut contenir, au maximum, 255 caractères (ou moins en cas d’utilisation de caractères codés sur plusieurs octets). Il s’agit de la longueur maximale de chaque élément.
* **Délimiteur de valeurs** : caractère utilisé pour séparer les valeurs dans la variable de liste. Il s’agit généralement de caractères tels que des virgules, deux-points, barres verticales, etc.

   >[!NOTE]
   >
   >Les caractères à plusieurs octets ne peuvent pas servir de délimiteurs dans les variables de liste. Le délimiteur doit être un caractère à un seul octet.

* **Expiration** : à l’instar d’une expiration d’eVar, cette valeur détermine la période qui peut s’écouler entre la variable de liste et l’événement de conversion à relier.

   * **Au niveau d’une page vue ou d’une visite** : les événements de succès au-delà de la page vue ou de la visite ne sont reliés à aucune des valeurs dans la variable de liste.
   * **Sur la base d’une période, telle qu’un jour, une semaine, un mois, etc.** : les événements de succès au-delà de la période spécifiée ne sont reliés à aucune des valeurs dans la variable de liste. Un nombre personnalisé de jours peut être également défini.
   * **Evénements de conversion spécifiques** : tout autre événement de succès qui se déclenche après l’événement désigné n’est relié à aucune des valeurs dans la variable de liste.
   * **Jamais** : une période indéfinie peut s’écouler entre la variable de liste et l’événement de succès.

* **Affectation** : ce paramètre détermine comment les événements de succès répartissent le crédit entre les valeurs :

   * **Complète** : toutes les valeurs de la variable définies avant l’expiration de celle-ci obtiennent un crédit complet pour les événements de succès.
   * **Linéaire** : toutes les valeurs de la variable définies avant l’expiration de celle-ci obtiennent un crédit divisé pour les événements de conversion.
   * Les valeurs de la variable ne sont jamais remplacées. Elles sont ajoutées aux valeurs qui obtiennent le crédit pour les événements de succès.

* **Valeurs max.** : désigne le nombre de valeurs actives autorisées pour cette variable de liste. Par exemple, si ce paramètre est défini sur 3, seules les 3 dernières valeurs capturées sont enregistrées et toute valeur capturée précédemment est ignorée. Notez que si plusieurs valeurs pour la même variable de liste sont envoyées sur le même accès, alors que vous avez limité l’utilisation des valeurs maximales, chaque valeur aura le même horodatage et vous n’aurez aucune garantie quant à la valeur enregistrée.

   250 valeurs au maximum sont stockées à la fois par visiteur. Si cette limite de 250 valeurs par visiteur est dépassée, seules les 250 dernières valeurs sont utilisées. L’expiration de ces valeurs dépend de l’expiration configurée pour la variable.

   Le paramètre Valeurs max. se révèle particulièrement utile pour limiter l’attribution à un nombre spécifique de valeurs. Par exemple, si une variable de liste est définie sur « A,B,C » sur la première page d’une liste, puis sur « X,Y,Z » sur la page suivante, l’attribution est distribuée à ces six valeurs sur la base de l’allocation. Si vous souhaitez limiter l’attribution aux seules valeurs « X,Y,Z », vous pouvez définir ce paramètre sur 3.

Pour configurer ou modifier les variables de liste, sélectionnez **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administration]** &gt; **[!UICONTROL Suites de rapports]** &gt; **[!UICONTROL Modifier les paramètres]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Variables de liste]**.

**Exemples de mise en œuvre** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

La virgule est utilisée comme délimiteur de valeurs dans les exemples suivants :

**Définition d’une seule valeur dans une variable de liste :**

```js
s.list1="Cat";
```

**Transmission de plusieurs valeurs :**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**Affectation de recettes à une variable de liste :**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

Ce résultat présente trois éléments avec, pour chacun d’eux, des recettes de 50 USD. (Bannière publicitaire supérieure ; Annonce de barre latérale ; Campagne interne 1.) Notez que le total de ce rapport déduplique les recettes, de telle sorte qu’il fera également état de 50 USD.

**Affectation de recettes à une variable de liste qui a été définie plusieurs fois lors d’une visite :**

**Affectation** : complète

**Expiration** : visite

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Activity Map </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Page 1 </td> 
   <td colname="col2"> <code> s.list1="value1,value2,value3"; </code> </td> 
   <td colname="col3"> (non défini) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page 2 </td> 
   <td colname="col2"> <code> s.list1="value4,value5,value6"; </code> </td> 
   <td colname="col3"> <p> <code> s.events="purchase"; </code> </p> <p> <code> s.products=";product;1;200" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Résultat :** toutes les valeurs définies dans la variable de liste 1 à tout moment pendant la visite (value1,value2,value3,value4,value5,value6) reçoivent un crédit complet pour l’achat.

