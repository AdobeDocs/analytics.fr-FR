---
description: Ce module externe fonctionne en utilisant l’API JavaScript Navigation Timing (Minutage de navigation) pour mesurer précisément les performances sur le web. Il fournit une méthode native permettant d’obtenir des statistiques de minutage précises et détaillées sur les événements de chargement de pages et les temps de chargement des ressources. Auparavant, les mesures de ce type utilisaient l’objet Date JavaScript pour les mesures de minutage ou une extrapolation rudimentaire des mesures de minutage de navigation. Bien qu’elles procurent des données de tendance sur les temps de chargement des pages, ces deux méthodes ne sont pas fiables.
keywords: Analytics Implementation
title: performanceTiming
topic: Developer and implementation
uuid: ab2a6c51-8791-41e7-9bea-c1ce8d312de8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# performanceTiming

Ce module externe fonctionne en utilisant l’API JavaScript Navigation Timing (Minutage de navigation) pour mesurer précisément les performances sur le web. Il fournit une méthode native permettant d’obtenir des statistiques de minutage précises et détaillées sur les événements de chargement de pages et les temps de chargement des ressources. Auparavant, les mesures de ce type utilisaient l’objet Date JavaScript pour les mesures de minutage ou une extrapolation rudimentaire des mesures de minutage de navigation. Bien qu’elles procurent des données de tendance sur les temps de chargement des pages, ces deux méthodes ne sont pas fiables.

## À quoi sert ce module externe {#section_4E0771B959FD4F86B4B91BD18CA01DF1}

>[!IMPORTANT]
>
>Il s’agit d’une version bêta du module externe ; d’autres mises à jour pourront être publiées par la suite.

Ce module externe se sert des événements détaillés ci-après pour effectuer le suivi des composants individuels de temps de chargement d’une page :

| Événement | Nom | Calcul d’après |
|---|---|---|
| 1 | Minutage de redirection | fetchStart - navigationStart |
| 2 | Minutage de mise en mémoire cache de l’application | domainLookupStart - fetchStart |
| 3 | Minutage DNS | domainLookupEnd - domainLookupStart |
| 4 | Minutage TCP | connectEnd - connectStart |
| 5 | Minutage d’une demande | responseStart - connectEnd |
| 6 | Minutage de réponse | responseEnd - responseStart |
| 7 | Minutage de traitement | loadEventStart - domLoading |
| 8 | Minutage au chargement onLoad | loadEventEnd - loadEventStart |
| 9 | Minutage de chargement total de la page | loadEventEnd - navigationStart |
| 10 | Instances de performances | Compteur |

Le schéma suivant illustre les attributs de minutage définis par les interfaces PerformanceTiming et PerformanceNavigation avec ou sans redirection, respectivement.

![](assets/timing-attributes.png)

Cliquez sur le lien suivant pour obtenir plus de détails sur l’objet Minutage de navigation :

[https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface](https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface)

En outre, le module externe a la possibilité d’utiliser l’objet performanceEntries pour enregistrer les détails relatifs au nom de la ressource, au début et à la durée du temps de chargement de la ressource pour chaque ressource individuelle chargée sur une page donnée. De nombreuses informations sont enregistrées avec ce module externe. En tant que tel, il nécessite que l’objet de stockage DOM soit activé afin de stocker les informations au chargement de la page entre deux pages vues. Assurez-vous que la politique de confidentialité de votre entreprise autorise l’utilisation de l’objet de stockage DOM avant d’activer cette fonctionnalité. Une variable listVar doit aussi être utilisée pour le suivi de toutes les ressources.

## Modules externes de prise en charge requis {#section_B6447EB6548942EFBC219AEFDC245639}

* appendList
* getPreviousValue

## Mise en œuvre et code du module externe {#section_564D77E1CF0E445586D95AD9769CE57D}

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et la mise en œuvre d’Adobe Analytics. Ce module externe est compatible uniquement avec les bibliothèques de suivi [!DNL AppMeasurement].

**Section Config (avant doPlugins) :**

`s.pte` : liste séparée par des virgules d’événements contenant les dix événements que vous souhaitez utiliser (événements 1 à 8), le minutage total de chargement de la page (événement 9) et les instances de performances totales (événement 10) – dans cet ordre spécifique.

`s.ptc` : défini pour déterminer si le module externe doit être exécuté dans doPlugins. Toujours défini sur « false ».

*Exemples d’appel*

```
s.pte = 'event10,event11,event12,event13,event14,event15,event16,event17,event18,event19' 
//[--------------------------- 1 to 8 ---------------------------][-- 9 --][- 10 -] 
s.ptc = false; 
```

**Section doPlugins :**

Pour initialiser le module externe, une ligne de code est requise dans la section `doPlugins` de votre s_code, de préférence après avoir désigné la variable `s.pageName`. Si vous souhaitez utiliser la fonction de temps de chargement des ressources dans le module externe, vous devez transmettre le nom de la variable de liste à utiliser. Sinon, seules les entrées de minutage de performances seront suivies dans les événements que vous avez spécifiés auparavant dans la variable `s.pte`.

> [!NOTE]Afin d’établir la corrélation des entrées de minutage de performances avec les pages de votre site, vous devez également initialiser le module externe `getPreviousValue`. Nous vous recommandons de comparer ces entrées de performances avec le nom de page précédent ou la valeur d’URL de page précédente.

*Exemples d’appel*

```
/* Performance Timing */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.performanceTiming('list2')  
```

**Section plugins :**

Enfin, ajoutez le module externe à proprement parler à votre mise en œuvre JavaScript.

```
/* Plugin: Performance Timing Tracking - 0.11 BETA */ 
s.performanceTiming=new Function("v","" 
+"var s=this;if(v)s.ptv=v;if(typeof performance!='undefined'){if(perf" 
+"ormance.timing.loadEventEnd==0){s.pi=setInterval(function(){s.perfo" 
+"rmanceWrite()},250);}if(!s.ptc||s.linkType=='e'){s.performanceRead(" 
+");}else{s.rfe();s[s.ptv]='';}}"); 
s.performanceWrite=new Function("","" 
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)" 
+";try{if(s.c_r('s_ptc')==''&&performance.timing.loadEventEnd>0){try{" 
+"var pt=performance.timing;var pta='';pta=s.performanceCheck(pt.fetc" 
+"hStart,pt.navigationStart);pta+='^^'+s.performanceCheck(pt.domainLo" 
+"okupStart,pt.fetchStart);pta+='^^'+s.performanceCheck(pt.domainLook" 
+"upEnd,pt.domainLookupStart);pta+='^^'+s.performanceCheck(pt.connect" 
+"End,pt.connectStart);pta+='^^'+s.performanceCheck(pt.responseStart," 
+"pt.connectEnd);pta+='^^'+s.performanceCheck(pt.responseEnd,pt.respo" 
+"nseStart);pta+='^^'+s.performanceCheck(pt.loadEventStart,pt.domLoad" 
+"ing);pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.loadEventStart" 
+");pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.navigationStart);" 
+"s.c_w('s_ptc',pta);if(sessionStorage&&navigator.cookieEnabled&&s.pt" 
+"v!='undefined'){var pe=performance.getEntries();var tempPe='';for(v" 
+"ar i=0;i<pe.length;i++){tempPe+='!';tempPe+=pe[i].name.indexOf('?')" 
+">-1?pe[i].name.split('?')[0]:pe[i].name;tempPe+='|'+(Math.round(pe[" 
+"i].startTime)/1000).toFixed(1)+'|'+(Math.round(pe[i].duration)/1000" 
+").toFixed(1)+'|'+pe[i].initiatorType;}sessionStorage.setItem('s_pec" 
+"',tempPe);}}catch(err){return;}}}catch(err){return;}"); 
s.performanceCheck=new Function("a","b","" 
+"if(a>=0&&b>=0){if((a-b)<60000&&((a-b)>=0)){return((a-b)/1000).toFix" 
+"ed(2);}else{return 600;}}"); 
s.performanceRead=new Function("","" 
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)" 
+";var cv=s.c_r('s_ptc');if(s.pte){var ela=s.pte.split(',');}if(cv!='" 
+"'){var cva=s.split(cv,'^^');if(cva[1]!=''){for(var x=0;x<(ela.lengt" 
+"h-1);x++){s.events=s.apl(s.events,ela[x]+'='+cva[x],',',2);}}s.even" 
+"ts=s.apl(s.events,ela[ela.length-1],',',2);}s.linkTrackEvents=s.apl" 
+"(s.linkTrackEvents,s.pte,',',2);s.c_w('s_ptc','',0);if(sessionStora" 
+"ge&&navigator.cookieEnabled&&s.ptv!='undefined'){s[s.ptv]=sessionSt" 
+"orage.getItem('s_pec');sessionStorage.setItem('s_pec','',0);}else{s" 
+"[s.ptv]='sessionStorage Unavailable';}s.ptc=true;"); 
/* Remove from Events 0.1 - Performance Specific,  
removes all performance events from s.events once being tracked. */ 
s.rfe=new Function("","" 
+"var s=this;var ea=s.split(s.events,',');var pta=s.split(s.pte,',');" 
+"try{for(x in pta){s.events=s.rfl(s.events,pta[x]);s.contextData['ev" 
+"ents']=s.events;}}catch(e){return;}"); 
/* Plugin Utility - RFL (remove from list) 1.0*/ 
s.rfl=new Function("l","v","d1","d2","ku","" 
+"var s=this,R=new Array(),C='',d1=!d1?',':d1,d2=!d2?',':d2,ku=!ku?0:" 
+"1;if(!l)return'';L=l.split(d1);for(i=0;i<L.length;i++){if(L[i].inde" 
+"xOf(':')>-1){C=L[i].split(':');C[1]=C[0]+':'+C[1];L[i]=C[0];}if(L[i" 
+"].indexOf('=')>-1){C=L[i].split('=');C[1]=C[0]+'='+C[1];L[i]=C[0];}" 
+"if(L[i]!=v&&C)R.push(C[1]);else if(L[i]!=v)R.push(L[i]);else if(L[i" 
+"]==v&&ku){ku=0;if(C)R.push(C[1]);else R.push(L[i]);}C='';}return s." 
+"join(R,{delim:d2})"); 
```

## Remarques {#section_131C5D97A0094880AFC3A2BBE0BC9DE4}

* Les installations de module externe doivent toujours faire l’objet de tests afin de s’assurer que la collecte des données fonctionne comme prévu avant son déploiement dans un environnement de production.
* Puisque le module externe transmet les données de performances pendant l’association à la page précédente, les données ne sont pas collectées pour la dernière page vue de la visite.
* Si vous effectuez le suivi du minutage des ressources, ce module externe dépend de la capacité à définir les valeurs de stockage DOM dans le navigateur web de l’utilisateur. Si l’utilisateur n’accepte pas les cookies et que le stockage DOM est activé, le module externe ne transmettra pas les données dans Analytics.
* Un très faible pourcentage d’utilisateurs ne transmettront aucune donnée sur le minutage de navigation en raison des restrictions de leur navigateur ; la logique est contenue dans le module externe afin de garantir que les données ne sont pas biaisées en conséquence, en particulier avec une petite portion de navigateurs mobiles. Toutefois, ce module externe a été testé avec succès dans IE, Firefox, Chrome et Safari.
* Créez des [!UICONTROL mesures calculées] afin de mieux récapituler et comprendre le comportement des visiteurs associé à ces mesures :

   * Minutage de redirection moyen (instances minutage de redirection/minutage de performances)
   * Minutage de mise en mémoire cache de l’application moyen (instances minutage de mise en mémoire cache de l’application/minutage de performances)
   * Minutage DNS moyen (instances minutage DNS/minutage de performances)
   * Minutage TCP moyen (instances minutage TCP/minutage de performances)
   * Minutage d’une demande moyen (instances minutage d’une demande/minutage de performances)
   * Minutage de réponse moyen (instances minutage de réponse/minutage de performances)
   * Minutage de traitement moyen (instances minutage de traitement/minutage de performances)
   * Minutage au chargement onLoad moyen (instances minutage au chargement onLoad/minutage de performances)
   * Minutage de chargement de page moyen (instances minutage de chargement total de page/minutage de performances)

