---
description: Si vous avez sélectionné la méthode de collecte de données du module externe JavaScript, copiez les lignes de code suivantes et ajoutez-les au code Adobe Analytics sur vos pages.
seo-description: Si vous avez sélectionné la méthode de collecte de données du module externe JavaScript, copiez les lignes de code suivantes et ajoutez-les au code Adobe Analytics sur vos pages.
seo-title: Code du module externe Adobe Analytics
title: Code du module externe Adobe Analytics
uuid: e99999be-1800-4d63-a4cb-df68a1b53d0d
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Code du module externe Adobe Analytics{#adobe-analytics-plug-in-code}

Si vous avez sélectionné la méthode de collecte de données du module externe JavaScript, copiez les lignes de code suivantes et ajoutez-les au code Adobe Analytics sur vos pages.

```
/* 
 * Plugin: getQueryParam 2.3 
 */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/* 
 * in the s_doPlugins function 
 */ 
s.eVar8=s.getQueryParam("MID"); // Message ID as assigned by broadmail 
s.eVar9=s.getQueryParam("RID"); // Recipient ID as assigned by broadmail 
 
I am not sure, if that is useful and/or necessary, but I though the  
client may specify the Post Click values in the s_doPlugins function as  
well. Maybe it were useful to add some example definitions like the  
following to indicate the use of these variables.
 
/* 
 * Optional custom settings of the Post Click data that is transferred to optivo broadmail.
 * Also to be defined in the s_doPlugins function.
 */ 
s.eVar10="May 10, 2012"; // the date the Post Click occurred 
s.eVar11="Post Click Product ID"; // e.g. "shoes" 
s.eVar12="Post Click Type of Action"; // e.g. "purchase"; 
```

> [!NOTE] Le plug-in ci-dessus suppose que certaines variables de commerce personnalisées (eVars) sont disponibles. Si les variables spécifiées dans le module externe ci-dessus ne sont pas disponibles dans votre déploiement Adobe Analytics, remplacez-les simplement par celles qui sont disponibles.

