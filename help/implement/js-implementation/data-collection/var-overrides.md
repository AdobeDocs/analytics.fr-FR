---
description: Les remplacements de variables permettent de modifier une valeur de variable pour un seul suivi ou un appel de lien de suivi.
keywords: Mise en œuvre d’Analytics
seo-description: Les remplacements de variables permettent de modifier une valeur de variable pour un seul suivi ou un appel de lien de suivi.
seo-title: Remplacements de variables
solution: Analytics
subtopic: Variables
title: Remplacements de variables
topic: Développeur et mise en œuvre
uuid: 3ec09ae8-b9df-426f-8065-42b4518e6c5f
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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

