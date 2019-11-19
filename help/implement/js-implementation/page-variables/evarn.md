---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: edf88e40cae8b6886b04257f266666c13a37f88d

---


# eVarN

Les variables [!UICONTROL eVar] sont utilisées pour créer des rapports personnalisés.

<!-- 

eVarN.xml

 -->

Lorsqu’une variable eVar est définie sur une valeur pour un visiteur, la valeur est mémorisée jusqu’à son expiration. Tout événement de succès auquel est associé un visiteur alors que la valeur eVar est active est comptabilisé dans cette dernière.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 255 octets | V1-v75 ( [ou v100 ou v250](/help/implement/js-implementation/page-variables/page-variables.md)) | Conversion personnalisée | "" |

**Expiration**

Les `eVars` arrivent à expiration après une période que vous avez spécifiée. Une fois arrivées à expiration, elles ne reçoivent plus de crédit pour les événements de succès. Vous pouvez également configurer les eVars pour qu’elles arrivent à expiration lors d’un événement de succès. Ainsi, dans le cas d’une promotion interne qui arrive à expiration à la fin de la visite, celle-ci ne reçoit du crédit que pour les achats ou inscriptions qui ont lieu au cours de la visite pendant laquelle ils ont été activés.

Il existe deux méthodes pour faire expirer une eVar :

* Vous pouvez la configurer de manière à ce qu’elle arrive à expiration après une période ou un événement spécifique.
* Vous pouvez forcer l’expiration d’une eVar, ce qui se révèle utile pour redéfinir son objectif.

Prenons l’exemple d’une eVar, d’une durée de validité de 21 jours, qui est utilisée en mai pour faire état de promotions internes, et qui, en juin, est utilisée pour capturer des mots-clés de recherche interne. Dans ce cas, le 1er juin, vous devez forcer l’expiration de cette variable ou la réinitialiser. De cette manière, les valeurs de promotion interne ne figureront pas dans les rapports du mois de juin.

**Respect de la casse**

Les eVars ne sont pas sensibles à la casse, mais elles respectent la mise en majuscules de la première occurrence. Ainsi, si la première instance de la variable eVar1 est définie sur « Connecté », mais que toutes les instances suivantes sont transmises sous la forme « connecté », les rapports affichent toujours « Connecté » comme valeur de l’eVar.

**Compteurs**

Bien que les eVars soient généralement utilisées pour contenir des valeurs de chaîne, elles peuvent également être configurées pour faire office de compteurs. Elles s’avèrent particulièrement utiles sous cette forme lorsque vous essayez de comptabiliser le nombre d’actions qu’un utilisateur effectue avant un événement. Vous pouvez, par exemple, utiliser une eVar pour capturer le nombre de recherches internes avant un achat. Chaque fois qu’un visiteur effectue une recherche, l’eVar doit contenir une valeur « +1 ». Si un utilisateur effectue quatre recherches avant un achat, une instance est affichée pour chaque compte total : 1.00, 2.00, 3.00 et 4.00. Cependant, seule la valeur 4.00 reçoit du crédit pour l’événement d’achat (mesures Commandes et Recettes). Seuls les nombres positifs sont autorisés comme valeurs d’un compteur eVar.

**Sous-relations**

La possibilité de ventiler un rapport eVar personnalisée en fonction d’un autre constitue une exigence courante  pour ce type de rapport.  Par exemple, si une eVar contient le genre, et qu’une autre contient le salaire, vous pouvez poser la question suivante : parmi les visiteurs de sexe féminin, quel est le montant des recettes généré par les femmes dont le revenu annuel est supérieur à 50 000 euros. Toute eVar en sous-relation permet ce type de ventilation dans les rapports. Par exemple, si les sous-relations complètes sont activées dans l’eVar de genre, tous les autres rapports eVar personnalisés peuvent être ventilés par genre, et inversement. Pour qu’il soit possible d’afficher la sous-relation entre deux rapports, les sous-relations complètes doivent simplement êtres activées sur l’un d’eux. Par défaut, les rapports Campagne, Produits et Catégorie sont entièrement sous-liés (toute eVar peut être ventilée par campagne ou par produit).

**Syntaxe et valeurs possibles**

Bien qu’il soit possible de renommer les eVars, il doit toujours y être fait référence par eVarX dans le fichier JavaScript, où X représente un nombre compris entre 1 et 75 ([ ou 100, ou 250](/help/implement/js-implementation/page-variables/page-variables.md)).

```js
s.eVarX="value"
```

Les eVars présentent les mêmes limites que toutes les autres variables, sauf lorsqu’elles sont utilisées comme compteur. Si l’eVar est un « compteur », il est prévu qu’elle reçoive des valeurs numériques telles que « 1 » ou « 2,5 ». S’il y a plus de deux décimales, le compteur eVar arrondit la valeur à deux décimales. Un compteur eVar ne peut pas contenir de nombres négatifs.

**Exemples**

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**Paramètres de configuration**

Vous pouvez configurer les eVars dans Analytics &gt; Admin &gt; Suites de rapports &gt; Modifier les paramètres &gt; Conversion &gt; Variables de conversion]. Toutes peuvent être configurées avec un Nom, un Type, une Affectation, un paramètre Expire après ou Réintialiser. Chaque paramètre de configuration est décrit séparément.

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Paramètre </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nom </td> 
   <td> Permet de renommer un rapport eVar dans <span class="keyword">Analytics </span>. <p>L’eVar doit toujours être référencée sous la forme s.eVarX dans le code JavaScript, quel que soit le nom attribué au rapport dans <span class="keyword">Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td> Type </td> 
   <td> Permet d’indiquer si l’eVar est une chaîne de texte ou un compteur. </td> 
  </tr> 
  <tr> 
   <td> Affectation </td> 
   <td> Permet de configurer la valeur de l’eVar qui reçoit du crédit pour les événements de succès. <p>Si le paramètre Affectation est défini sur « Le dernier », B reçoit du crédit </p> <p>Si le paramètre Affectation est défini sur « Valeur d’origine (première) », A reçoit du crédit. </p> <p>Si le paramètre Affectation est défini sur « Linéaire », A et B reçoivent tous deux du crédit pour la moitié de la valeur d’achat. </p> </td> 
  </tr> 
  <tr> 
   <td> Expire après </td> 
   <td> Permet de déterminer si une eVar arrive à expiration lors d’un événement spécifique, tel qu’un achat, ou après une période personnalisée ou prédéfinie. </td> 
  </tr> 
  <tr> 
   <td> Réinitialiser </td> 
   <td> Lorsque vous cochez la case <span class="wintitle">Réinitialiser</span> pour une eVar et cliquez sur <span class="wintitle">Enregistrer</span> en bas de la page, toutes les valeurs de l’eVar en question expirent immédiatement. Ensuite, seules les nouvelles valeurs de l’eVar reçoivent du crédit pour les événements de succès. </td> 
  </tr> 
 </tbody> 
</table>

**Pièges, questions et conseils**

* Contrairement aux variables [!UICONTROL prop], les variables eVar ne sont pas autorisées comme listes de valeurs délimitées. Si vous renseignez une liste de valeurs dans une eVar (« un,deux,trois », par exemple), cette chaîne apparaît à l’identique dans les rapports.
* Les compteurs eVar ne peuvent pas contenir de nombres négatifs.
