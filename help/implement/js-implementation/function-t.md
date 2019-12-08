---
description: La fonction s.t() compile toutes les variables définies sur la page dans une demande d’image et l’envoie aux serveurs Adobe.
keywords: track;Analytics Implementation;page tracking;track page
subtopic: Functions
title: Fonction s.t() – Suivi des pages
topic: Developer and implementation
uuid: 67696e46-1e0d-4200-bfad-4217d1023948
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Fonction s.t() – Suivi des pages

La fonction s.t() compile toutes les variables définies sur la page dans une demande d’image et l’envoie aux serveurs Adobe.

## Propriétés d’une fonction {#section_DB1F3E216DCD4E12AE42BBDCD25B9626}

* La suppression de l’appel de la fonction [!UICONTROL s.t()] empêche les données d’atteindre [!DNL Analytics]. Plusieurs appels de la fonction [!UICONTROL s.t()] déclenchent plusieurs demandes d’image (ce qui multiplie par deux le trafic signalé sur votre site).

* Si vous souhaitez déclencher plusieurs demandes d’image lors d’un seul chargement de page, il est conseillé d’utiliser la fonction [!UICONTROL s.tl()].
* Le déclenchement de cette fonction augmente toujours les [!UICONTROL pageviews] et inclut systématiquement la variable [!UICONTROL s.pageName].

## Implémentation {#section_F75C7BD4A8954CD5BE066C6B88A4A01C}

Lors de la génération du code dans le [!UICONTROL gestionnaire de code], les lignes de code suivantes sont fournies dans la partie inférieure du code de page :

```js
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" /></noscript> 
```

Chaque ligne de code a un rôle spécifique :

```js
var s_code=s.t();if(s_code)document.write(s_code)//-->
```

Cette ligne de code est celle qui déclenche réellement la fonction JavaScript. La variable [!UICONTROL s_code] et la méthode document.write qui l’accompagne sont destinées aux navigateurs qui ne prennent pas en charge les objets image (navigateurs Netscape dont la version est antérieure à la version 3 et Internet Explorer dont la version est antérieure à la version 4 ; estimation à moins de 0,5 % des utilisateurs Internet).

```js
<script language="JavaScript" type="text/javascript"><!--if(navigator.appVersion.indexOf('MSIE')>=0)document.write(unescape('%3C')+'\!-'+'-')//--></script> 
<noscript><img  
src="https://yournameserver.112.2o7.net/b/ss/yourreportsuiteid/1/H.23.6--NS/0" height="1" width="1" border="0" alt="" />
```

Pour toute question concernant la fonction [!UICONTROL s.t()], contactez le gestionnaire de compte de votre société. Il peut organiser une réunion avec un consultant en implémentation Adobe qui peut vous aider.
