---
description: Si vous avez sélectionné la méthode de collecte de données du plug-in JavaScript, copiez les lignes de code suivantes et ajoutez-les au code Analytics de vos pages.
seo-description: Si vous avez sélectionné la méthode de collecte de données du plug-in JavaScript, copiez les lignes de code suivantes et ajoutez-les au code Analytics de vos pages.
seo-title: Code du module externe Analytics
title: Code du module externe Analytics
uuid: c 75 a 6 cd 2-ee 7 a -4 c 2 f -98 a 8-4618 d 0617 b 4 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Code du module externe Analytics{#analytics-plug-in-code}

Si vous avez sélectionné la méthode de collecte de données du plug-in JavaScript, copiez les lignes de code suivantes et ajoutez-les au code Analytics de vos pages.

`/*`

`* Plugin: getQueryParam 2.3`

`*/ s.getQueryParam=new Function("p","d","u","" +"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" +"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" +".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" +"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" +"=p.length?i:i+1)}return v"); s.p_gpv=new Function("k","u","" +"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" +"=s.pt(q,'&','p_gvf',k)}return v"); s.p_gvf=new Function("t","k","" +"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" +"rue':t.substring(i+1);if(p.toLowerCase()==k. oLowerCase())return s." +"epa(v)}return ''");`

`/*in the s_doPlugins function`

`s.campaign=s.getQueryParam("ET_CID"); //places query param value from cid in campaign variable s.eVar2=s.getQueryParam("ET_RID"); //places query param value from rid in eVar2 variable`

>[!NOTE]
>
>Le module externe ci-dessus suppose que certaines variables de commerce (evars) sont disponibles. Si les variables spécifiées dans le module externe ci-dessus ne sont pas disponibles dans votre déploiement Analytics, remplacez-les simplement par celles disponibles.

