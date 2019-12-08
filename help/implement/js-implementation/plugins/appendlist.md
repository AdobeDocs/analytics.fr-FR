---
description: Le module externe (plug-in) apl (ou appendList) permet d’ajouter une valeur à toute liste délimitée, avec la possibilité d’effectuer une vérification sensible ou non à la casse afin de s’assurer que la valeur en question ne figure pas déjà dans la liste. Le module externe APL est référencé par plusieurs modules externes standard, mais il peut être utilisé directement dans un éventail de situations.
keywords: Analytics Implementation
subtopic: Plug-ins
title: appendList
topic: Developer and implementation
uuid: e923c86c-eaa6-4e17-a3a4-0e08af886674
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# appendList

Le module externe (plug-in) apl (ou appendList) permet d’ajouter une valeur à toute liste délimitée, avec la possibilité d’effectuer une vérification sensible ou non à la casse afin de s’assurer que la valeur en question ne figure pas déjà dans la liste. Le module externe APL est référencé par plusieurs modules externes standard, mais il peut être utilisé directement dans un éventail de situations.

Ce module externe permet d’effectuer les opérations suivantes :

* Ajouter un événement à la variable « events » en cours
* Ajouter une valeur à la variable « list » sans dupliquer une valeur de la liste
* Ajouter un produit à la variable « products » en cours sur la base d’une logique de page
* Ajouter des valeurs aux paramètres *`linkTrackVars`* et *`linkTrackEvents`*

**Cas d’utilisation 1**

<table id="table_5AAC1D9892CD4E5C9060E119EE4E7DC8"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Scénario </p> </td> 
   <td colname="col2"> <p>Add <span class="term"> event1 </span> to the current events variable while ensuring the event isn't duplicated. </p> <p>s.events="scCheckout" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Résultats </p> </td> 
   <td colname="col2"> <p>s.events="scCheckout,event1" </p> </td> 
  </tr> 
 </tbody> 
</table>

**Cas d’utilisation 2**

<table id="table_C4356C9AB95948F3929A7B75E07AE9E7"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Scénario </p> </td> 
   <td colname="col2"> <p>Ajouter la valeur <span class="term"> history </span> à la variable de liste <span class="varname"> prop1 </span>, avec <span class="term"> history </span> et <span class="term"> History </span> considérés comme la même valeur. </p> <p>s.prop1="Science,History" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code </p> </td> 
   <td colname="col2"> <p>s.prop1=s.apl(s.prop1,"history",",",2) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Résultats </p> </td> 
   <td colname="col2"> <p>s.prop1="Science,History" </p> <p> <span class="term"> history </span> n’est pas ajouté, car <span class="term"> History </span> figure déjà dans la liste. </p> </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

## Implémentation {#section_F4C91CA2037F478C9F7B53F357E6A5F0}

Procédez comme suit pour implémenter le module externe APL.

1. Demandez le code du module externe au service à la clientèle ou à votre conseiller Adobe attitré.
1. Ajoutez le ou les appels à la fonction API dans la fonction *`s_doPlugins`*.

Le code peut se présenter comme suit sur votre site :

```js
/* Plugin Config */ 
 
s.usePlugins=true 
 
function s_doPlugins(s) { 
 
/* Add calls to plugins here */ 
 
s.events=s.apl(s.events,"event1",",",1) 
 
} 
 
s.doPlugins=s_doPlugins
```

**Navigateurs pris en charge**

Pour utiliser ce module externe, il faut que le navigateur prenne en charge JavaScript version 1.0.

**Informations sur le module externe**

<table id="table_7B9EDD616C164D6B8B53558337DF12C2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Informations sur le module externe </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Paramètres </p> </td> 
   <td colname="col2"> <p>apl((L,v,d,u) </p> <p>L = Liste source ; une liste vide est acceptée </p> <p> v = Valeur à ajouter </p> <p> d = Délimiteur de liste </p> <p> u (facultatif, 0 par défaut) Vérification de valeur unique. 0 = Pas de vérification de valeur unique ; la valeur est toujours ajoutée. 1 = Vérification non sensible à la casse ; la valeur n’est ajoutée que si elle ne figure pas dans la liste. 2 = Vérification sensible à la casse ; la valeur n’est ajoutée que si elle ne figure pas dans la liste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valeur renvoyée </p> </td> 
   <td colname="col2"> <p>Liste d’origine, avec une valeur ajoutée, le cas échéant </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exemples d’utilisation </p> </td> 
   <td colname="col2"> <p>s.events=s.apl(s.events,"event1",",",1); </p> </td> 
  </tr> 
 </tbody> 
</table>

La liste source L peut être vide, comme par exemple *`L=""`*. La valeur renvoyée est soit une liste vide, soit une liste ne contenant qu’une seule valeur.

**Code du module externe**

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin Utility: apl v1.1 
 */ 
s.apl=new Function("l","v","d","u","" 
+"var s=this,m=0;if(!l)l='';if(u){var i,n,a=s.split(l,d);for(i=0;i<a." 
+"length;i++){n=a[i];m=m||(u==1?(n==v):(n.toLowerCase()==v.toLowerCas" 
+"e()));}}if(!m)l=l?l+d+v:v;return l"); 
 
/******************************************************************** 
 * 
 * Commented example of how to use this is doPlugins function 
 * 
 *******************************************************************/ 
  
 Not Applicable - Utility function only 
 
/******************************************************************** 
 * 
 * Config variables (should be above doPlugins section) 
 * 
 *******************************************************************/ 
 
 None 
 
/******************************************************************** 
 * 
 * Utility functions that may be shared between plug-ins (name only) 
 * 
 *******************************************************************/ 
  
 s.split
```

