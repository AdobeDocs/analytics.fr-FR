---
description: Réservez les eVars nécessaires dans l’outil d’administration d’Adobe Analytics avant d’utiliser le code ci-dessous.
title: Code du plug-in de paramètre de chaîne de requête
uuid: a71e7774-bc7a-414e-a116-739770b900bf
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Code du plug-in de paramètre de chaîne de requête {#query-string-param-plug-in-code}

Réservez les eVars nécessaires dans l’outil d’administration d’Adobe Analytics avant d’utiliser le code ci-dessous.

Une fois que vous avez sélectionné les eVars à réserver, remplacez eVarN par l’eVar correspondant, par exemple eVar10.

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
 
/*in the s_doPlugins function - Replace N with actual eVar number*/ 
s.eVarN=s.getQueryParam("<insert Selligent QS Param>");  
//places query param value from Message ID in eVarN variable s.eVarN=s.getQueryParam("<insert Selligent QS Param>");  
//places query param value from Recepient ID in eVarN variable 
```

