---
description: Consigne la durée en secondes pendant laquelle votre page a été l’onglet actif dans le navigateur et transmet cette valeur dans une mesure sur la prochaine page vue.
keywords: Analytics Implementation
title: getPageVisibility
topic: Developer and implementation
uuid: 3891e2aa-d5c1-4a2b-8522-eb2bae39ea2e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getPageVisibility

Consigne la durée en secondes pendant laquelle votre page a été l’onglet actif dans le navigateur et transmet cette valeur dans une mesure sur la prochaine page vue.

> [!NOTE] Il s’agit d’une version bêta du module externe ; d’autres mises à jour pourront être publiées par la suite.

Ce module externe exige [getVisitStart](/help/implement/js-implementation/plugins/getvisitstart.md).

Ce module externe consigne également la durée totale en secondes pendant laquelle la page s’est trouvée dans le navigateur (durée d’affichage active et passive). Vous devez utiliser le module externe getPreviousValue pour effectuer le suivi du nom de page précédent associé aux événements de visibilité de la page. Le suivi de ces valeurs permet de mieux comprendre l’engagement des visiteurs et d’effectuer un suivi plus précis sur le comportement des visiteurs sur vos sites.

Utilisez le module externe getPreviousValue pour effectuer le suivi du nom de page précédent associé aux événements de visibilité de la page. Le suivi de ces valeurs permet de mieux comprendre l’engagement des visiteurs et d’effectuer un suivi plus précis sur le comportement des visiteurs sur vos sites.

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collection des données sur votre site. Aussi, cette opération doit-elle être réalisée par un développeur maîtrisant l’utilisation et l’implémentation d’Analytics. Ce module externe est compatible uniquement avec les bibliothèques de suivi [!DNL AppMeasurement].

## Modules externes de prise en charge requis {#section_0CA7624F4A7B4B5F851A4300937887AD}

* appendList
* getPreviousValue
* getVisitStart

## Implémentation et code du module externe {#section_543ABD8B3E6A48A5AFD86CFEDE144696}

**Section de configuration**

La variable `s.pvel` doit contenir les trois événements à utiliser :

| Événement | Définition |
|---|---|
| Total des secondes de visibilité de la page (nombre) | Durée totale pendant laquelle la page était active dans le navigateur. |
| Total des secondes de la page (nombre) | Durée pendant laquelle la page a été chargée dans le navigateur, quel que soit son état de visibilité. |
| Total des instances de visibilité de la page (compteur) | Nombre total de fois où une valeur a été consignée pour les deux événements précédents. |

**Exemples d’appel**

```
//Page Visibility Event List (total page visibility seconds, total page seconds, total page visibility instances) 
s.pvel='event7,event8,event9' 
```

**Section doPlugins**

Pour initialiser le module externe, deux lignes de code sont requises dans la section `doPlugins` de votre s_code, de préférence après avoir désigné la variable `s.pageName`.

**Exemples d’appel**

```
/* Page Visibility */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.getPageVisibility(); 
```

**Section des modules externes**

```
/* Page Visibility Plugin 0.1 (BETA) */ 
s.getPageVisibility=new Function("","" 
+"var s=this;if(s.getVisitStart()){s.Util.cookieWrite('s_pvs','');s.U" 
+"til.cookieWrite('s_tps','');}if(s.Util.cookieRead('s_pvs')&&s.pvt<1" 
+"){if(parseInt(s.Util.cookieRead('s_pvs'))<=parseInt(s.Util.cookieRe" 
+"ad('s_tps'))){s.pve=s.pvel.split(',');s.events=s.apl(s.events,s.pve" 
+"[0]+'='+(parseInt(s.Util.cookieRead('s_pvs'))),',',2);s.Util.cookie" 
+"Write('s_pvs','');s.events=s.apl(s.events,s.pve[1]+'='+(parseInt(s." 
+"Util.cookieRead('s_tps'))),',',2);s.Util.cookieWrite('s_tps','');s." 
+"events=s.apl(s.events,s.pve[2],',',2);}}s.pvi=setInterval(s.pvx,100" 
+"0);s.wpvi=setInterval(s.wpvc,5000);"); 
s.gbp=new Function("","" 
+"if('hidden'in document){return null;}var bp=['moz','ms','o','webkit" 
+"'];for(var i=0;i<bp.length;i++){var p=bp[i]+'Hidden';if(p in docume" 
+"nt){return bp[i];}}return null;"); 
s.hp=new Function("p","" 
+"if(p){return p+'Hidden';}else{return'hidden';}"); 
s.vs=new Function("p","" 
+"if(p){return p+'VisibilityState';}else{return'visibilityState';}"); 
s.ve=new Function("p","" 
+"if(p){return p+'visibilitychange';}else{return'visibilitychange';}"); 
s.pvx=new Function("","" 
+"s.pvt+=1;"); 
s.wpvc = function(){var tempDate = Date.now();s.Util.cookieWrite('s_tps', 
Math.ceil((tempDate - s.totalTime)/1000));s.Util.cookieWrite('s_pvs', s.pvt)} 
document.addEventListener('visibilitychange',function(event){if(document.hidden){s.visibility = false;clearTimeout(s.pvi);}else{s.visibility=true;s.pvi=setInterval(s.pvx,1000);}});s.totalTime=new Date();s.pvt=0;s.prefix=s.gbp;s.hidden=s.hp(s.prefix);s.visibility=true;s.visibilityState=s.vs(s.prefix);s.visibilityEvent=s.ve(s.prefix); 
```

## Remarques {#section_47964BB9D0A24BFEB4B2498A41D8B017}

* Les installations de module externe doivent toujours faire l’objet de tests afin de s’assurer que la collecte des données fonctionne comme prévu avant son déploiement dans un environnement de production.
* Puisque le module externe transmet la durée en secondes de visibilité de la page et le total des secondes pendant l’association à la page précédente, les données ne sont pas collectées pour la dernière page vue de la visite.
* Ce module externe repose sur la possibilité de définir des cookies dans le navigateur Web de l’utilisateur. Si l’utilisateur n’accepte pas les cookies propriétaires, le module externe ne transmet pas les données dans Analytics.
* Le module externe crée ses propres cookies propriétaires nommés `s_tps` et `s_pvs`.

* Un très petit pourcentage d’utilisateurs ne transmettra pas le pourcentage des données affichées sur la page en raison des limitations du navigateur et la logique est contenue dans le module externe afin de s’assurer que les données ne sont pas biaisées. Toutefois, ce module externe a été testé avec succès dans IE, Firefox, Chrome et Safari.
* En raison de la façon dont le module externe mesure le total des secondes et associe cette valeur au nom de page précédente, il y aura des différences entre les mesures de durée par défaut passée sur la page et les mesures de total des secondes.
* Il est possible de créer des [!UICONTROL mesures calculées] afin de mieux récapituler et comprendre le comportement des visiteurs associé à ces mesures :

   * **Quotient de visibilité de la page**(Total des secondes de visibilité de la page / Total des secondes de la page)
   * **Total des secondes** masquées (Total des secondes de la page - Total des secondes de visibilité de la page)
   * **Moyenne des secondes de visibilité de la page**(Total des secondes de visibilité de la page / Total des instances de visibilité de la page)
   * **Moyenne des secondes masquées de la page**((Total des secondes de la page - Total des secondes de visibilité de la page) / Total des instances de visibilité de la page)

* En raison de la façon dont le module externe arrondit les secondes, il se peut qu’il y ait 1 ou 2 secondes de différence entre le total des secondes de visibilité de la page et le total des secondes, le total des secondes étant plus élevé. (A résoudre dans une prochaine mise à jour)
* L’utilisation du module externe getVisitStart devrait tenir compte des visiteurs qui ont commencé une nouvelle visite après plus de 30 minutes d’inactivité. Cela ne fonctionne pas comme prévu; toutefois, il y aura probablement une solution lorsque nous intégrerons le "total des secondes actives" dans une prochaine version du module externe.

## Questions fréquentes {#section_1ED9391D3BAA4208817F0DF69ABBB25E}

**Ce module externe lancera-t-il des appels de serveur supplémentaires ?**

Le module externe consignera uniquement les valeurs de visibilité de la page lors des prochains appels de serveur de page vue. Aucun appel de serveur supplémentaire ne sera utilisé conjointement à ce module externe.

**Si je ne souhaite pas capturer le total des secondes de la page ou le total des instances de visibilité de la page, puis-je laisser ces valeurs en dehors de la liste d’événements ?**

Oui, le total des secondes de la page et le total des instances de visibilité sont des événements facultatifs et peuvent être laissés hors de la liste si nécessaire.

**Les événements capturés seront-ils utiles si je les utilise dans des rapports autres que le nom de la page précédente ?**

Puisque le module externe enregistre les valeurs sur la demande d’image suivante, seules les autres eVars capturées dans un contexte de page précédente peuvent être appliquées, c’est-à-dire. 'URL de la page précédente'.

**Le module externe enverra-t-il la durée de visibilité lors d’un appel s.tl() ou seulement lors d’un appel s.t() ?**

La durée de visibilité est uniquement consignée avec les appels s.t().
