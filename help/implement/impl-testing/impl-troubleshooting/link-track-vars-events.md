---
description: 'Une implémentation de suivi de liens réussie repose sur la maîtrise des variables s.linkTrackVars et s.linkTrackEvents. Vous pouvez ainsi transmettre des valeurs de variable personnalisée lors des opérations des utilisateurs. '
keywords: Mise en œuvre d’Analytics
seo-description: 'Une implémentation de suivi de liens réussie repose sur la maîtrise des variables s.linkTrackVars et s.linkTrackEvents. Vous pouvez ainsi transmettre des valeurs de variable personnalisée lors des opérations des utilisateurs. '
seo-title: Utilisation des variables s.linkTrackVars et s.linkTrackEvents
solution: Analytics
title: Utilisation des variables s.linkTrackVars et s.linkTrackEvents
topic: Développeur et mise en œuvre
uuid: f 6 b 7019 b -987 b -4 b 7 d-a 446-80205 f 7 cc 36 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Utilisation des variables s.linkTrackVars et s.linkTrackEvents

Une implémentation de suivi de liens réussie repose sur la maîtrise des variables s.linkTrackVars et s.linkTrackEvents. Vous pouvez ainsi transmettre des valeurs de variable personnalisée lors des opérations des utilisateurs. 

Si vous implémentez le suivi des liens personnalisés et si vous définissez des variables [!UICONTROL personnalisées] et la variable *`events`*, assurez-vous que la [!UICONTROL variable s. linktrackvars] contient une liste séparée par des virgules de toutes les variables que vous transmettez, y compris la *`events`* variable. Vérifiez également que [!UICONTROL s.linkTrackEvents] comprend la liste de tous les événements séparés par des virgules que vous transmettez.

La définition de [!UICONTROL s.linkTrackVars] et [!UICONTROL s.linkTrackEvents] ne définit pas ces variables/événements. Elle prépare uniquement le code [!DNL Analytics] à le faire. Vous devez toujours définir ces variables manuellement, comme illustré dans l’exemple ci-après. 

```js
<script language="javascript"> 
function customLinks () { 
 var s=s_gi('myreportsuite'); 
 s.linkTrackVars="prop1,eVar7,products,events"; 
 s.linkTrackEvents="event5,event9"; 
 s.prop1="Link Click"; 
 s.eVar7="my_page.html"; 
 s.events="event5"; 
 s.tl(true,'o','Custom Link Click'); 
} 
</script> 
<a href="my_page.html" onclick="customLinks();">My Page</a> 
```

Vous pouvez remarquer que la variable events est répertoriée dans la variable [!UICONTROL s.linkTrackVars]. Les événements qui peuvent être transmis sont compris dans la variable [!UICONTROL s.linkTrackEvents] et aussi dans [!UICONTROL s.events] plus loin dans la fonction. Chacune des variables transmises sont répertoriées dans [!UICONTROL s.linkTrackVars] avant d’être renseignées plus loin dans la fonction. « event9 » a été également inclus dans [!UICONTROL s.linkTrackEvents], mais pas dans [!UICONTROL s.events]. Il n’est pas enregistré, mais il pourrait l’être si l’utilisateur avait choisi de définir s.events="event5,event9".

Le suivi automatique des téléchargements de fichiers et celui des liens de [!UICONTROL sortie] fonctionnent différemment. [!UICONTROL s.linkTrackVars] et [!UICONTROL s.linkTrackEvents] sont inclus dans le fichier [!DNL s_code.js] standard et sont définis sur « none ». En règle générale, ces variables sont toujours définies sur « none » dans le fichier [!DNL s_code.js] pour que le suivi automatique des liens, contrairement au [!UICONTROL suivi des liens personnalisés], utilise les valeurs de [!UICONTROL s.linkTrackVars] et [!UICONTROL s.linkTrackEvents] définies dans le fichier JavaScript global. Elles transmettent également les valeurs existantes dès qu’un téléchargement de fichier ou un lien de sortie [!UICONTROL Exit] est enregistré.

Examinez l’exemple dans lequel s.channel="Home" lorsque la page se charge et s.linkTrackVars="channel" dans le fichier [!DNL s_code.js]. Si un utilisateur clique pour télécharger un fichier, le suivi automatique des téléchargements de fichiers transmet les données dans [!DNL Analytics], notamment la valeur de [!UICONTROL s.channel] définie lors du chargement de la page. La valeur « Home » est transmise une seconde fois, ce qui augmente les données de pages vues pour cette valeur dans le rapports [!UICONTROL Sections du site].

Adobe conseille vivement de laisser [!UICONTROL s.linkTrackVars] et [!UICONTROL s.linkTrackEvents] définis sur « none » dans le fichier JavaScript global et de les définir explicitement pour l’implémentation du [!UICONTROL suivi des liens personnalisés].
