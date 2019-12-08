---
description: Le module externe getVisitNum détermine le nombre de visites qu’un internaute a effectuées sur votre site et capture cette valeur dans une variable Analytics.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getVisitNum
topic: Developer and implementation
uuid: 27d57f92-fffb-44d0-b9ca-9da93323f64c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getVisitNum

Le module externe getVisitNum détermine le nombre de visites qu’un internaute a effectuées sur votre site et capture cette valeur dans une variable Analytics.

## Implémentation et code du module externe {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION** : aucune modification n’est requise pour cette section.

**Plugin Config**

Placez le code suivant dans la fonction *`s_doPlugins()`* située dans la section du fichier *`s_code.js`intitulée* Plugin Config *.* Sélectionnez une variable Trafic personnalisé (s.prop) ou Conversion personnalisée (s.eVar) à utiliser dans le cadre de la capture des données relatives au nombre de visites. Il doit s’agir d’une variable que vous avez activée à l’aide d’Admin Console, mais qui, pour l’heure, n’est affectée à aucun autre usage. Vous pouvez utiliser l’exemple suivant et l’adapter en fonction de vos besoins.

`s.prop1=s.getVisitNum();`

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

**PLUGINS SECTION** : ajoutez le code suivant à la section du fichier [!DNL s_code.js] intitulée PLUGINS SECTION. N’effectuez aucune modification dans cette partie du code du module externe.

```js
/* 
* Plugin: getVisitNum - version 3.0 
*/ 
s.getVisitNum=new Function("tp","c","c2","" 
+"var s=this,e=new Date,cval,cvisit,ct=e.getTime(),d;if(!tp){tp='m';}" 
+"if(tp=='m'||tp=='w'||tp=='d'){eo=s.endof(tp),y=eo.getTime();e.setTi" 
+"me(y);}else {d=tp*86400000;e.setTime(ct+d);}if(!c){c='s_vnum';}if(!" 
+"c2){c2='s_invisit';}cval=s.c_r(c);if(cval){var i=cval.indexOf('&vn=" 
+"'),str=cval.substring(i+4,cval.length),k;}cvisit=s.c_r(c2);if(cvisi" 
+"t){if(str){e.setTime(ct+1800000);s.c_w(c2,'true',e);return str;}els" 
+"e {return 'unknown visit number';}}else {if(str){str++;k=cval.substri" 
+"ng(0,i);e.setTime(k);s.c_w(c,k+'&vn='+str,e);e.setTime(ct+1800000);" 
+"s.c_w(c2,'true',e);return str;}else {s.c_w(c,e.getTime()+'&vn=1',e)" 
+";e.setTime(ct+1800000);s.c_w(c2,'true',e);return 1;}}"); 
s.dimo=new Function("m","y","" 
+"var d=new Date(y,m+1,0);return d.getDate();"); 
s.endof=new Function("x","" 
+"var t=new Date;t.setHours(0);t.setMinutes(0);t.setSeconds(0);if(x==" 
+"'m'){d=s.dimo(t.getMonth(),t.getFullYear())-t.getDate()+1;}else if(" 
+"x=='w'){d=7-t.getDay();}else {d=1;}t.setDate(t.getDate()+d);return " 
+"t;");
```

**Paramètres**

* tp = (chaîne, facultatif) Période de suivi. Utilisez « d » pour jour, « s » pour semaine, « m » pour mois, ou un nombre correspondant à un nombre personnalisé de jours.

   * Si jour, semaine ou mois est sélectionné alors le nombre de visites se réinitialise à la fin du jour/semaine/mois.
   * Si un nombre personnalisé de jours est sélectionné alors le nombre de visites est réinitialisé une fois ce nombre écoulé.
   * Si aucune valeur n’est indiquée alors « m » est utilisé.

* c = (chaîne, facultatif) Spécifiez le nom du cookie persistant. La valeur par défaut est « s_vnum ».
* c2 = (chaîne, facultatif) Spécifiez le nom du cookie persistant. La valeur par défaut est « s_invisit ».

**Retours**

* Retourne le nombre de visites (1, 2, 3 etc.) de la visite. Ce nombre n’est incrémenté que sur la première page de chaque visite.
* Retourne « nombre de visites inconnu » si le module externe ne peut pas identifier le nombre de visites (les cookies sont bloqués).

**Exemples**

```js
s.prop1=s.getVisitNum(365); //custom length, 365 days. Default cookie names 
s.prop1=s.getVisitNum('w'); //resets weekly 
s.prop1=s.getVisitNum('m','s_vmonthnum','s_monthinvisit'); //resets montly, custom cookie names 
s.prop1=s.getVisitNum('d'); //resets daily
```

**Remarques**

* Les installations de module externe doivent toujours faire l’objet de tests approfondis afin de s’assurer que la collecte des données fonctionne comme prévu avant son déploiement dans un environnement de production.
* Ce module externe repose sur la possibilité de définir des cookies dans le navigateur Web de l’utilisateur. Si l’utilisateur n’accepte pas les cookies, toutes les visites apparaissent comme s’il s’agissait de première visites.

