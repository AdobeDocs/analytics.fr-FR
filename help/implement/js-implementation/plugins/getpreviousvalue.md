---
description: Capture la valeur d’une variable Analytics sur la page vue suivante. Vous pouvez, par exemple, utiliser le module externe pour capturer la valeur s.pageName de la page vue précédente dans une variable Trafic personnalisé. Une option vous permet également de ne capturer une valeur précédente que si des événements de réussite désignés sont définis.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getPreviousValue
topic: Developer and implementation
uuid: 20da7b4a-9820-4690-a1cc-d10b6dd627a7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getPreviousValue

Capture la valeur d’une variable Analytics sur la page vue suivante. Vous pouvez, par exemple, utiliser le module externe pour capturer la valeur s.pageName de la page vue précédente dans une variable Trafic personnalisé. Une option vous permet également de ne capturer une valeur précédente que si des événements de réussite désignés sont définis.

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

## Implémentation et code du module externe {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION** : aucune modification n’est requise pour cette section.

**Plugin Config**

Placez le code suivant dans la fonction *`s_doPlugins()`* située dans la section du fichier *`s_code.js`intitulée* Plugin Config *.* Sélectionnez une variable Trafic personnalisé (s.prop) ou Conversion personnalisée (s.eVar) à utiliser dans le cadre de la capture de données de valeurs persistantes. Il doit s’agir d’une variable que vous avez activée à l’aide d’Admin Console, mais qui, pour l’heure, n’est affectée à aucun autre usage. Vous pouvez utiliser l’exemple suivant et l’adapter en fonction de vos besoins.

`s.prop1=s.getPreviousValue(s.pageName,'gpv_pn','event1');`

*`s.getPreviousValue`* possède trois arguments :

1. Variable à capturer dans la page précédente (*`s.pageName`* ci-dessus).
1. Nom de cookie à utiliser lors du stockage de la valeur à récupérer (*`gpv_pn`* ci-dessus).
1. Événements qui doivent être définis sur la page vue afin de déclencher la récupération de la valeur précédente (*`event1`* ci-dessus). Si ce paramètre n’est pas renseigné, le module externe capture la valeur précédente sur toutes les pages vues.

**PLUGINS SECTION** : ajoutez le code suivant à la section du fichier [!DNL s_code.js] intitulée PLUGINS SECTION. N’effectuez aucune modification dans cette partie du code du module externe.

```js
/* 
 * Plugin: getPreviousValue_v1.0 - return previous value of designated 
 * variable (requires split utility) 
 */ 
s.getPreviousValue=new Function("v","c","el","" 
+"var s=this,t=new Date,i,j,r='';t.setTime(t.getTime()+1800000);if(el" 
+"){if(s.events){i=s.split(el,',');j=s.split(s.events,',');for(x in i" 
+"){for(y in j){if(i[x]==j[y]){if(s.c_r(c)) r=s.c_r(c);v?s.c_w(c,v,t)" 
+":s.c_w(c,'no value',t);return r}}}}}else{if(s.c_r(c)) r=s.c_r(c);v?" 
+"s.c_w(c,v,t):s.c_w(c,'no value',t);return r}"); 
/* 
 * Utility Function: split v1.5 - split a string (JS 1.0 compatible) 
 */ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a"); 
```

**Remarques**

* Les installations de module externe doivent toujours faire l’objet de tests approfondis afin de s’assurer que la collecte des données fonctionne comme prévu avant son déploiement dans un environnement de production.
* Si aucune valeur n’est présente pour la variable sélectionnée sur une page donnée, le texte *aucune valeur* est défini dans le cookie.
* Un délai d’expiration de cookie fixe de 30 minutes est maintenant défini pour chaque cookie et actualisé lors de chaque rechargement de page. Le module externe fonctionne pendant toute la durée d’une visite.
* La fonction doit être appelée dans le cadre de la section plug-ins du code. Aussi, ce dernier s’exécute-t-il chaque fois que la fonction *`s.t()`* ou *`s.tl()`* est appelée.

* Une valeur doit être renseignée dans la variable choisie avant d’effectuer l’appel vers *`s.getPreviousValue`*. Étant donné que la fonction *`s_doPlugins()`* est exécutée après avoir renseigné les variables sur la page, cela pose rarement problème. Cela ne doit être inquiétant que si la variable utilisée avec ce module externe est renseignée dans la fonction *`s_doPlugins()`* et après l’appel à *`s.getPreviousValue`*.

