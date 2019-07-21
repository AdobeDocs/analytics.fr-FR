---
description: Capture la valeur d’une variable Analytics sur la page vue suivante. Vous pouvez, par exemple, utiliser le module externe pour capturer la valeur s.pageName de la page vue précédente dans une variable Trafic personnalisé. Une option vous permet également de ne capturer une valeur précédente que si des événements de succès désignés sont définis.
keywords: Mise en œuvre d’Analytics
seo-description: Capture la valeur d’une variable Analytics sur la page vue suivante. Vous pouvez, par exemple, utiliser le module externe pour capturer la valeur s.pageName de la page vue précédente dans une variable Trafic personnalisé. Une option vous permet également de ne capturer une valeur précédente que si des événements de réussite désignés sont définis.
seo-title: getPreviousValue
solution: Analytics
subtopic: Modules externes
title: getPreviousValue
topic: Développeur et mise en œuvre
uuid: 20 da 7 b 4 a -9820-4690-a 1 cc-d 10 b 6 dd 627 a 7
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getPreviousValue

Capture la valeur d’une variable Analytics sur la page vue suivante. Vous pouvez, par exemple, utiliser le module externe pour capturer la valeur s.pageName de la page vue précédente dans une variable Trafic personnalisé. Une option vous permet également de ne capturer une valeur précédente que si des événements de succès désignés sont définis.

>[!NOTE]
>
>Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

## Implémentation et code du module externe {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION** : aucune modification n’est requise pour cette section.

**Plugin Config**

Placez le code suivant dans la fonction *`s_doPlugins()`* qui se trouve dans la section du *`s_code.js`* fichier intitulée *Plugin Config*. Sélectionnez une variable Trafic personnalisé (s.prop) ou Conversion personnalisée (s.eVar) à utiliser dans le cadre de la capture de données de valeurs persistantes. Il doit s’agir d’une variable que vous avez activée à l’aide d’Admin Console, mais qui, pour l’heure, n’est affectée à aucun autre usage. Vous pouvez utiliser l’exemple suivant et l’adapter en fonction de vos besoins.

`s.prop1=s.getPreviousValue(s.pageName,'gpv_pn','event1');`

*`s.getPreviousValue`* possède trois arguments :

1. The variable to be captured from the previous page ( *`s.pageName`* above).
1. The cookie name for use in storing the value for retrieval ( *`gpv_pn`* above).
1. The events that must be set on the page view in order to trigger the retrieval of the previous value ( *`event1`* above). Si ce paramètre n’est pas renseigné, le module externe capture la valeur précédente sur toutes les pages vues.

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

* Une valeur doit être renseignée dans la variable choisie avant d’effectuer l’appel vers *`s.getPreviousValue`*. Because the *`s_doPlugins()`* function is executed after the variables on the page are populated, this issue rarely occurs. It should only be a matter of concern if the variable used with this plug-in is populated within the *`s_doPlugins()`* function and after the call to *`s.getPreviousValue`*.

