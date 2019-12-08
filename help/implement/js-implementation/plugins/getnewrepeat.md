---
description: Détermine s’il s’agit d’un nouveau visiteur ou d’un utilisateur fidèle, puis capture cette information dans une variable Analytics.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getNewRepeat
topic: Developer and implementation
uuid: e3e9f362-e0b1-4a2b-bb5b-98eddaa0a7f4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getNewRepeat

Détermine s’il s’agit d’un nouveau visiteur ou d’un utilisateur fidèle, puis capture cette information dans une variable Analytics.

Utilisez ce module externe pour répondre aux questions suivantes :

* Quel est le pourcentage de nouveaux visiteurs (par rapport aux utilisateurs récurrents) ?
* Les visiteurs récurrents génèrent-ils un taux de conversion par tête plus élevé que les nouveaux visiteurs ? Quel est ce ratio ?
* Les campagnes marketing génèrent-elles une persistance entre les visites ? Ainsi, les utilisateurs qui arrivent sur mon site par le biais de mes campagnes publicitaires y reviennent-ils par la suite ?

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

## Implémentation et code du module externe {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION** : aucune modification n’est requise pour cette section.

**Plugin Config**

Placez le code suivant dans la fonction *`s_doPlugins()`* située dans la section du fichier *`s_code.js`intitulée* Plugin Config *.* Sélectionnez une variable Trafic personnalisé (s.prop) ou Conversion personnalisée (s.eVar) à utiliser dans le cadre de la capture de données de valeurs persistantes. Il doit s’agir d’une variable que vous avez activée à l’aide d’Admin Console, mais qui, pour l’heure, n’est affectée à aucun autre usage. Vous pouvez utiliser l’exemple suivant et l’adapter en fonction de vos besoins.

`s.prop1=s.getNewRepeat(30,'s_getNewRepeat');`

*`s.getNewRepeat`* possède deux arguments facultatifs :

1. Le premier correspond à la durée du cookie, exprimée en jours. Si l’argument est omis, la valeur par défaut est de 30 jours.
1. Le deuxième argument facultatif est le nom du cookie. Une valeur par défaut est utilisée si cet argument est omis.

**PLUGINS SECTION** : ajoutez le code suivant à la section du fichier [!DNL s_code.js] intitulée PLUGINS SECTION. N’effectuez aucune modification dans cette partie du code du module externe.

```js
/* 
 * Plugin: getNewRepeat 1.2 - Returns whether user is new or repeat 
 */ 
s.getNewRepeat=new Function("d","cn","" 
+"var s=this,e=new Date(),cval,sval,ct=e.getTime();d=d?d:30;cn=cn?cn:" 
+"'s_nr';e.setTime(ct+d*24*60*60*1000);cval=s.c_r(cn);if(cval.length=" 
+"=0){s.c_w(cn,ct+'-New',e);return'New';}sval=s.split(cval,'-');if(ct" 
+"-sval[0]<30*60*1000&&sval[1]=='New'){s.c_w(cn,ct+'-New',e);return'N" 
+"ew';}else{s.c_w(cn,ct+'-Repeat',e);return'Repeat';}"); 
/* 
* Utility Function: split v1.5 (JS 1.0 compatible) 
*/ 
s.split=new Function("l","d","" 
+"var i,x=0,a=new Array;while(l){i=l.indexOf(d);i=i>-1?i:l.length;a[x" 
+"++]=l.substring(0,i);l=l.substring(i+d.length);}return a");
```

Les installations de module externe doivent toujours faire l’objet de tests approfondis afin de s’assurer que la collecte des données fonctionne comme prévu avant son déploiement dans un environnement de production.
