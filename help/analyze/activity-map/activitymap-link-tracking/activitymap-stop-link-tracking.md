---
description: Étapes pour arrêter le suivi des liens dans Activity Map ou la version héritée de Carte des clics.
seo-description: Étapes pour arrêter le suivi des liens dans Activity Map ou la version héritée de Carte des clics.
seo-title: Arrêt du suivi des liens
solution: Analytics
title: Arrêt du suivi des liens
topic: Activity Map
uuid: e 17 fb 7 bd-d 6 ed -45 c 3-a 006-9150 d 5718 cff
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Arrêt du suivi des liens

Étapes pour arrêter le suivi des liens dans Activity Map ou la version héritée de Carte des clics.

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pour arrêter le suivi des liens dans... </th> 
   <th colname="col2" class="entry"> Procédez comme suit : </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Supprimez le contenu suivant du fichier Appmeasurement.js : 
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
   <td colname="col2"> <p>Définissez la variable <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="https" scope="external">trackInlineStats</a> sur false (valeur par défaut). The syntax reads as follows: 
     <code>
       s.trackInlineStats=false
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

