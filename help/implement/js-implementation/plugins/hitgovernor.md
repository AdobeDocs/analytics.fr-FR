---
description: Le module externe s.hitGovernor effectue le suivi du nombre total de demandes d’images Analytics envoyées au cours d’une période récurrente prédéfinie et peut réaliser une logique supplémentaire en cas de besoin si le nombre total dépasse un certain seuil.
seo-description: Le module externe s.hitGovernor effectue le suivi du nombre total de demandes d’images Analytics envoyées au cours d’une période récurrente prédéfinie et peut réaliser une logique supplémentaire en cas de besoin si le nombre total dépasse un certain seuil.
seo-title: hitGovernor
title: hitGovernor
uuid: d 9091 eae -005 a -43 c 2-b 419-980 b 795 bc 2 a 9
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# hitGovernor

Le module externe s.hitGovernor effectue le suivi du nombre total de demandes d’images Analytics envoyées au cours d’une période récurrente prédéfinie et peut réaliser une logique supplémentaire en cas de besoin si le nombre total dépasse un certain seuil.

## hitGovernor {#topic_56B636A42A624B38A0A446C607ACD700}

Le module externe s.hitGovernor effectue le suivi du nombre total de demandes d’images Analytics envoyées au cours d’une période récurrente prédéfinie et peut réaliser une logique supplémentaire en cas de besoin si le nombre total dépasse un certain seuil.

Bien que le trafic provenant de bots, d’araignées, d’agents d’utilisateurs spécifiques ou d’une liste spécifique d’adresses IP peut être identifié comme trafic de bot ou exclu des rapports, il est possible qu’une portion du trafic capturé dans vos suites de rapports ne devrait pas être comptabilisée. Par exemple, un nombre élevé de clics ou de pages vues au cours d’un laps de temps non raisonnable (c’est-à-dire environ une demande par seconde) peut être le signe d’un trafic malveillant.

Ce module externe vous permet de bloquer automatiquement ce trafic pendant la durée de vie restante de ce visiteur. De plus, ce trafic peut être identifié de manière dynamique au sein des rapports.

## Fonctionnement du module externe Hit Governor {#section_541BC639E31442D09B1C85A2FFCDC02C}

Le module externe incrémente une valeur de cookie chaque fois qu’une demande d’image est envoyée à vos serveurs de suivi et en effectue un suivi au cours d’une période récurrente. La période par défaut est d’une minute, mais elle peut être remplacée. (Voir [Mise en œuvre](../../../implement/js-implementation/plugins/hitgovernor.md#task_D4BDB524AA294C139AFCAE2B61FEA3F2) ci-dessous) If the total number of hits during that time frame exceeds the default hit threshold (60), a final custom link image request is sent to set the *`exceptionFlag`* context data variable. Le seuil d’accès par défaut peut également être remplacé.

Si vous le souhaitez, à partir de ce point, la collecte du trafic de ce visiteur spécifique peut cesser pendant une période par défaut de 60 jours. Le blocage du trafic requiert une ligne de code supplémentaire dans votre fonction doPlugins, comme décrit ci-dessous. La période peut également être ajustée. The logic allows time to either include that visitor's IP address, User Agent, or [!DNL Experience Cloud] Visitor ID in the proper permanent exception logic, or to reset the timeout period after the sixty days have elapsed. Si ce trafic est identifié comme frauduleux par le module externe après 60 jours, il est à nouveau marqué comme une exception et n’est pas collecté pendant 60 jours.

## Création de rapports {#section_E742F19B528041808454744DB2C7007C}

Aucune variable ni événement par défaut ne doit être configuré. Toutefois, nous recommandons fortement de configurer une logique de règles de traitement pour définir des variables et des événements en conséquence. Ces variables et événements personnalisés peuvent inclure :

* [!DNL Experience Cloud] Visitor ID
* Adresse IP
* Agent utilisateur
* Événement d’exception avec indicateur

La création de segments avec ces variables vous permettrait ensuite de créer des segments et des suites de rapports virtuels afin d’afficher l’impact global de ces accès ambigus sur le site.

Nous recommandons d’utiliser les valeurs capturées dans les rapports pour mettre à jour les règles de bots, les règles DB VISTA ou les exclusions IP de l’entreprise.

## Implémentation {#task_D4BDB524AA294C139AFCAE2B61FEA3F2}

Pour mettre en œuvre le module externe hitGovernor :

1. Modification de la bibliothèque AppMeasurement.

   Pour initialiser le module externe, incluez cette ligne de code (en gras) au sein de la fonction `registerPostTrackCallback` dans le code de bibliothèque AppMeasurement.

   >[!NOTE]
   >
   >Although the `registerPostTrackCallback` functionality is included in AppMeasurement libraries 1.8.0+, it is not included in any custom code configuration by default. Elle est incluse après et *hors de* la fonction doPlugins.

   ```
    s.registerPostTrackCallback(function(){ 
       
<b> s.governor();</b> 
   });
   ```

   Below the doPlugins section of your AppMeasurement file, include the plugin code contained in [Plugin Source Code](../../../implement/js-implementation/plugins/hitgovernor.md#reference_76423C81A7A342B2AC4BE41490B27DE0), below.

   The hit limit threshold, hit timing threshold, and traffic exclusion time frames can all be overridden by setting these variables, outside of the plugin itself and preferably with your other configuration variables:

<table id="table_9959A40F5F0B40B39DB86E21D03E25FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Syntax </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Hit Limit Threshold </p> </td> 
   <td colname="col2"> <p> <code> s.hl = 60; </code> </p> </td> 
   <td colname="col3"> <p>The total number of hits that should not be exceeded during a given timeframe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hit Time Threshold </p> </td> 
   <td colname="col2"> <p> <code> s.ht = 10; </code> </p> </td> 
   <td colname="col3"> <p>The window, in seconds, for when hits are recorded. This number is divided by six to determine the rolling timing windows. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclusion Threshold </p> </td> 
   <td colname="col2"> <p> <code> s.he = 60; </code> </p> </td> 
   <td colname="col3"> <p>Number of days that the exclusion cookie is set for that visitor. </p> </td> 
  </tr> 
 </tbody> 
</table>

   >[!NOTE]
   >
   >Your implementation might use a different object name than the default analytics "s" object. If so, please update the object name accordingly.

1. Configure processing rules.

   This plugin records flagged exceptions as context data in a link tracking image request. As such, processing rules must be configured to assign track those flagged exceptions into appropriate variables like those below.

   ![](assets/hitgov-config.png)

1. (Optional) Include the traffic-blocking code in doPlugins.

   After traffic has been identified as an exception, any subsequent hits from that visitor can be blocked entirely by including this code within the `doPlugins` function:

   ```
   //Check for hit governor flag 
         if(s.Util.cookieRead('s_hg')==9)s.abort=true;
   ```

   If this code is not included, traffic from that visitor will be flagged but not blocked. 

## Plugin Source Code {#reference_76423C81A7A342B2AC4BE41490B27DE0}

This code should be added below the doPlugins section of your AppMeasurement library.

```
//Hit Governor (Version 0.1 BETA, 11-13-17) 
s.governor=new Function("","" 
+"var s=this;if(typeof s.hl=='undefined'){s.hl=60;}if(typeof s.ht=='u" 
+"ndefined'){s.ht=60;}if(typeof s.he=='undefined'){s.he=60;}if(s.Util" 
+".cookieRead('s_hg')==8){var i=new Date(),y=i.getFullYear(),m=i.getM" 
+"onth(),d=i.getDate(),i=new Date(y,m,d+s.he);s.Util.cookieWrite('s_h" 
+"g',9,i);return;}var f=s.Util.cookieRead('s_hc'),g=Number(s.Util.coo" 
+"kieRead('s_ht')),h=Math.floor((new Date()).getTime()),ha=f!=''?f.sp" 
+"lit('|').map(Number):[0,0,0,0,0],i=ha.reduce(function(ha,b){return " 
+"ha+b;},0),j=g==0?0:Math.floor(((h-g)/(s.ht/6))/1000);if(g==0)s.Util" 
+".cookieWrite('s_ht',h);if(i<s.hl){if(j>=1){if(j>=6){ha=[0,0,0,0,0];" 
+"}else{for(var k=0;k<j;k++){ha.unshift(0);ha.pop();}}s.Util.cookieWr" 
+"ite('s_ht',h);}}else{s.Util.cookieWrite('s_hg',8);s.linkTrackVars+=" 
+"',contextData.exceptionFlag';s.contextData['exceptionFlag']='true';" 
+"s.tl(this,'o','exceptionFlag');}ha[0]++;s.Util.cookieWrite('s_hc',h" 
+"a.join('|'));"); 

```

