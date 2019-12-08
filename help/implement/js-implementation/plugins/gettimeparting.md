---
description: Le module externe getTimeParting renseigne les variables personnalisées avec les valeurs « heure du jour », « jour de la semaine », « jour du week-end » et « jour de semaine ». Analysis Workspace propose des dimensions de répartition des heures prêtes à l’emploi. Le module externe devrait être utilisé si des dimensions de répartition des heures sont requises dans d’autres solutions Analytics, hors d’Analysis Workspace.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getTimeParting

Le module externe getTimeParting renseigne les variables personnalisées avec les valeurs « heure du jour », « jour de la semaine », « jour du week-end » et « jour de semaine ». [!UICONTROL Analysis Workspace] propose des dimensions de répartition des heures prêtes à l’emploi. Le module externe devrait être utilisé si des dimensions de répartition des heures sont requises dans d’autres solutions Analytics, hors d’[!UICONTROL Analysis Workspace].

Ce module externe capture les informations de date et d’heure disponibles dans le navigateur Web de l’utilisateur. L’heure et le jour de la semaine sont obtenus à partir de ces informations. Il convertit ensuite ces données dans le fuseau horaire de votre choix. Il tient également compte de l’heure d’été.

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

## Code du module externe {#section_1390D6FA53BE4C40B748B0C0AE09C4FA}

**Section de configuration**

Insérez le code suivant dans la section du fichier [!DNL s_code.js] intitulée [!UICONTROL CONFIG SECTION] et effectuez les mises à jour nécessaires, comme indiqué ci-dessous.

`s._tpDST` - un tableau de valeurs d’heures d’été. Le tableau est structuré au format suivant : `YYYY:'MM/DD,MM/DD'`

```js
//time parting configuration 
//Australia 
s._tpDST = { 
2012:'4/1,10/7', 
2013:'4/7,10/6', 
2014:'4/6,10/5', 
2015:'4/5,10/4', 
2016:'4/3,10/2', 
2017:'4/2,10/1', 
2018:'4/1,10/7', 
2019:'4/7,10/6',
2020:'4/5,10/4',
2021:'4/4,10/3'} 
  
//US 
s._tpDST = { 
2012:'3/11,11/4', 
2013:'3/10,11/3', 
2014:'3/9,11/2', 
2015:'3/8,11/1', 
2016:'3/13,11/6', 
2017:'3/12,11/5', 
2018:'3/11,11/4', 
2019:'3/10,11/3',
2020:'3/8,11/1',
2021:'3/14,11/7'} 
  
//Europe 
s._tpDST = { 
2012:'3/25,10/28', 
2013:'3/31,10/27', 
2014:'3/30,10/26', 
2015:'3/29,10/25', 
2016:'3/27,10/30', 
2017:'3/26,10/29', 
2018:'3/25,10/28', 
2019:'3/31,10/27',
2020:'3/29,10/25',
2021:'3/28,10/31'}
```

Remarque destinée aux clients de l’hémisphère nord : dans le tableau, les valeurs d’heure d’été sont DST start, DST end.

Remarque destinée aux clients de l’hémisphère sud : dans le tableau, les valeurs d’heure d’été sont DST end, DST start.

**Paramètres**

```js
var tp = s.getTimeParting(h,z);
```

* h = (obligatoire) Hémisphère : indiquez l’hémisphère de conversion de l’heure. La valeur est « n » ou « s ». Cette valeur est utilisée pour déterminer comment utiliser le tableau d’heure d’été transféré. Si « n » est transféré, le module externe utilise les dates auxquelles l’heure d’été est active. Si « s » est transféré, le module externe utilise les dates auxquelles l’heure d’été est inactive.
* z = (facultatif) Fuseau horaire : si vous souhaitez que les données soient basées sur un fuseau horaire spécifique, vous devez l’indiquer ici en différence d’heures par rapport à GMT. Notez qu’il doit s’agir de l’heure GMT sans l’heure d’été. Si aucune valeur n’est indiquée, la valeur par défaut est GMT (c’est-à-dire « -5 » pour l’heure de New-York)

**Retours**

Retourne une valeur concaténée de l’heure au niveau de la minute et du jour de la semaine, par exemple :

```
8:03 AM|Monday
```

Vous pouvez alors utiliser [Classifications](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) pour regrouper des visites dans des périodes. Par exemple, vous pouvez définir une règle dans le Créateur de règles de classification pour regrouper les visites entre 9h00 et 9h59 sur « 9h00 -10h ». A la place des classifications, vous pouvez fournir une logique supplémentaire côté client pour regrouper les visites dans JavaScript.

**Exemple d’appel**

```js
var tp = s.getTimeParting('n','-7'); 
s.prop1 = tp;
```

**SECTION PLUGINS**

Ajoutez le code suivant à la [!UICONTROL SECTION PLUGINS] du fichier [!DNL s_code.js].

```js
/* 
 * Plugin: getTimeParting 3.4 
 */ 
s.getTimeParting=new Function("h","z","" 
+"var s=this,od;od=new Date('1/1/2000');if(od.getDay()!=6||od.getMont" 
+"h()!=0){return'Data Not Available';}else{var H,M,D,U,ds,de,tm,da=['" 
+"Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturda" 
+"y'],d=new Date();z=z?z:0;z=parseFloat(z);if(s._tpDST){var dso=s._tp" 
+"DST[d.getFullYear()].split(/,/);ds=new Date(dso[0]+'/'+d.getFullYea" 
+"r());de=new Date(dso[1]+'/'+d.getFullYear());if(h=='n'&&d>ds&&d<de)" 
+"{z=z+1;}else if(h=='s'&&(d>de||d<ds)){z=z+1;}}d=d.getTime()+(d.getT" 
+"imezoneOffset()*60000);d=new Date(d+(3600000*z));H=d.getHours();M=d" 
+".getMinutes();M=(M<10)?'0'+M:M;D=d.getDay();U=' AM';if(H>=12){U=' P" 
+"M';H=H-12;}if(H==0){H=12;}D=da[D];tm=H+':'+M+U;return(tm+'|'+D);}");
```

**Remarques**

* Les installations de module externe doivent toujours faire l’objet de tests afin de s’assurer que la collecte des données fonctionne comme prévu avant son déploiement dans un environnement de production.
* Vous devez définir les variables de configuration pour que le plug-in fonctionne correctement.

