---
description: Étapes pour commencer le suivi des liens dans Activity Map ou la version héritée de Carte des clics.
seo-description: Étapes pour commencer le suivi des liens dans Activity Map ou la version héritée de Carte des clics.
seo-title: Commencer le suivi des liens
solution: Analytics
title: Commencer le suivi des liens
topic: Activity Map
uuid: 425 cb 287-f 76 e -4430-802 f -288499711 ba 9
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Commencer le suivi des liens

Étapes pour commencer le suivi des liens dans Activity Map ou la version héritée de Carte des clics.

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour commencer le suivi des liens dans... </th> 
   <th colname="col2" class="entry"> Procédez comme suit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Ajoutez le contenu suivant au fichier Appmeasurement.js : 
    <code>/* START Activity Map MODULE Le module suivant active le suivi de Carte d'activités dans Adobe Analytics.Carte d'activités vous permet d'afficher des incrustations de données sur vos liens et contenus afin de comprendre comment les utilisateurs interagissent avec votre site Web.Si vous n'envisagez pas d'utiliser Carte d'activités, vous pouvez supprimer le bloc de code suivant de votre fichier appmeasurement. js.
  Additional documentation on how to configure Activity Map is available at:
      https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
     */
     function AppMeasurement_Module_Activity Map(g){func
     ...
     /* END Activity Map MODULE */
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Carte des clics (anciennement Carte des clics des visiteurs) </td> 
   <td colname="col2"> <p>Définissez la variable <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="https" scope="external">trackInlineStats</a> sur true. The syntax reads as follows: 
     <code>
       s.trackInlineStats=true
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

