---
description: Les remplacements de variables permettent de modifier une valeur de variable pour un seul suivi ou un appel de lien de suivi.
keywords: Analytics Implementation
subtopic: Variables
title: Remplacements de variables
topic: Developer and implementation
uuid: 3ec09ae8-b9df-426f-8065-42b4518e6c5f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Remplacements de variables

Les remplacements de variables permettent de modifier une valeur de variable pour un seul suivi ou un appel de lien de suivi.

Pour remplacer des variables, créez un objet, attribuez des valeurs de variable et transmettez cet objet comme premier paramètre à la fonction `s.t()` ou comme quatrième paramètre à la fonction `s.tl()` :

```js
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
  
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
  
s.t(overrides);  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

```js
s.linkTrackVars="eVar1,eVar2,eVar3,events"; 
s.eVar1="one"; 
s.eVar2="two"; 
s.eVar3="three"; 
 
overrides = new Object(); 
overrides.eVar1="1_one"; 
overrides.eVar2=""; 
 
s.tl(this,'e','AnotherSite',overrides,'navigate')  
// values passed: eVar1="1_one", eVar2="", eVar3="three"
```

