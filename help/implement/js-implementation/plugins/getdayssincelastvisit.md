---
description: Détermine le nombre de jours depuis la dernière visite de l’utilisateur sur votre site et capture ces informations dans une variable Analytics.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getDaysSinceLastVisit
topic: Developer and implementation
uuid: cad95882-3bd0-4f94-a0c3-4e7b6058d246
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getDaysSinceLastVisit

Détermine le nombre de jours depuis la dernière visite de l’utilisateur sur votre site et capture ces informations dans une variable Analytics.

>[!IMPORTANT]
>
>[Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) inclut désormais une dimension **[!UICONTROL Jours depuis la dernière visite]** prête à l’emploi, annulant ainsi la nécessité de ce module externe.

Ces données relatives à la fréquence des retours peuvent être utilisées pour répondre aux questions suivantes :

* A quelle fréquence les utilisateurs reviennent-ils sur mon site ?
* Quelle relation existe-t-il entre la fréquence des retours et les conversions ? Les acheteurs réguliers effectuent-ils des visites fréquentes ou espacées ?
* Les utilisateurs qui arrivent sur mon site par le biais de mes campagnes publicitaires y reviennent-ils ensuite fréquemment ?

Le module externe peut également générer des valeurs utilisées pour la segmentation. Vous pouvez, par exemple, créer un segment afin d’afficher toutes les données relatives aux seules visites espacées de 30 jours ou davantage.

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

## Implémentation et code du module externe {#section_5600DBB819F143D59527A73BD94418DE}

**CONFIG SECTION**

Aucune modification n’est requise.

**Config du module**

Placez le code suivant dans la fonction `s_doPlugins()` située dans la section du fichier [!DNL s_code.js] intitulée *Plugin Config*. Sélectionnez une variable Trafic personnalisé (s.prop) et/ou une variable Conversion personnalisée (s.eVar) à utiliser dans le cadre de la capture de données sur la fréquence des retours. Il doit s’agir d’une variable que vous avez activée à l’aide d’Admin Console, mais qui, pour l’heure, n’est affectée à aucun autre usage. Le code suivant est donné à titre indicatif. Il doit être adapté en fonction de vos besoins.

```js
s.prop1=s.getDaysSinceLastVisit(Cookie_Name);
```

**SECTION PLUGINS** Ajoutez le code suivant à la section du fichier [!DNL s_code.js] intitulée *PLUGINS SECTION*. N’effectuez aucune modification dans cette partie du code du module externe.

```js
/* 
 * Plugin: Days since last Visit 1.1 - capture time from last visit 
 */ 
s.getDaysSinceLastVisit=new Function("c","" 
+"var s=this,e=new Date(),es=new Date(),cval,cval_s,cval_ss,ct=e.getT" 
+"ime(),day=24*60*60*1000,f1,f2,f3,f4,f5;e.setTime(ct+3*365*day);es.s" 
+"etTime(ct+30*60*1000);f0='Cookies Not Supported';f1='First Visit';f" 
+"2='More than 30 days';f3='More than 7 days';f4='Less than 7 days';f" 
+"5='Less than 1 day';cval=s.c_r(c);if(cval.length==0){s.c_w(c,ct,e);" 
+"s.c_w(c+'_s',f1,es);}else{var d=ct-cval;if(d>30*60*1000){if(d>30*da" 
+"y){s.c_w(c,ct,e);s.c_w(c+'_s',f2,es);}else if(d<30*day+1 && d>7*day" 
+"){s.c_w(c,ct,e);s.c_w(c+'_s',f3,es);}else if(d<7*day+1 && d>day){s." 
+"c_w(c,ct,e);s.c_w(c+'_s',f4,es);}else if(d<day+1){s.c_w(c,ct,e);s.c" 
+"_w(c+'_s',f5,es);}}else{s.c_w(c,ct,e);cval_ss=s.c_r(c+'_s');s.c_w(c" 
+"+'_s',cval_ss,es);}}cval_s=s.c_r(c+'_s');if(cval_s.length==0) retur" 
+"n f0;else if(cval_s!=f1&&cval_s!=f2&&cval_s!=f3&&cval_s!=f4&&cval_s" 
+"!=f5) return '';else return cval_s;");
```

**Remarques**

* Les installations de module externe doivent toujours faire l’objet de tests approfondis afin de s’assurer que la collecte des données fonctionne comme prévu avant son déploiement dans un environnement de production.
* Le module externe classe les utilisateurs selon la fréquence des retours dans les groupes suivants :

   * Première visite
   * Moins de 1 jour
   * Moins de 7 jours
   * Plus de 7 jours
   * Plus de 30 jours

* Ce module externe compte sur les cookies pour signaler qu’un utilisateur a déjà visité le site. Si le navigateur n’accepte pas les cookies, le plug-in renvoie la valeur *Cookies non pris en charge*.

