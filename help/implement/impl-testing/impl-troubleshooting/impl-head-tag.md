---
description: Le code Analytics crée un objet image, à savoir une image invisible qui n’apparaît pas sur votre page.
keywords: Analytics Implementation
title: Placement du code Analytics dans la balise d’en-tête
topic: Developer and implementation
uuid: e8f91d3c-cb72-454d-9bd4-ff54d83d981f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Placement du code Analytics dans la balise d’en-tête

Le code Analytics crée un objet image, à savoir une image invisible qui n’apparaît pas sur votre page.

>[!NOTE]
>
>Cette section s’applique uniquement à l’implémentation du fichier s_code.js hérité. [AppMeasurement pour JavaScript 1.0](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) prend en charge le déploiement de la bibliothèque et du code de page dans la balise `<head>`.

Auparavant, le code JavaScript Analytics était placé entre les balises <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> et </head> balises. En le plaçant entre ces balises, l’image de 1x1 pixel qui était renvoyée par la demande qui avait envoyé les données vers les serveurs Adobe n’avait aucune incidence sur la disposition de la page. Insérer le code dans l’en-tête du document signifie qu’il apparaît plus haut dans le code. Il s’exécute ainsi plus tôt, ce qui permet de comptabiliser les pages vues pour les chargements de page partiels de façon plus efficace.

Certains éléments du code requièrent la présence de l’objet de corps. Comme les navigateurs Web exécutent le code dans l’ordre de réception, si le code JavaScript Analytics se trouve dans l’en-tête du document, il s’exécute avant la création de l’objet de corps. Votre implémentation ne collecte donc pas les données [!UICONTROL ClickMap], et le suivi automatique des téléchargements de fichiers ou des liens de [!UICONTROL sortie] n’est pas disponible. Vous ne recevez également pas les données de type de connexion ou de page d’accueil. Placer le code dans l’en-tête du document fonctionne, mais le résultat obtenu est une version très limitée d’Analytics. Les utilisateurs peuvent alors se demander pourquoi certains rapports et outils, notamment [!UICONTROL ClickMap] n’enregistrent pas de données.

Le code Analytics peut être placé n’importe où dans les balises BODY (<BODY></BODY>) d’une page HTML bien formée. Adobe conseille de placer le code dans un fichier d’inclusion global en haut de la page (à l’intérieur d’une balise BODY HTML). A l’exception des points ci-dessous, le code peut occuper n’importe quelle position sur la page :

* En cas de placement dans un tableau, le code doit être inséré dans des <td></td> balises. Par exemple, ne placez pas le code entre une balise d’ouverture <tr> et <td> de fermeture.
* Le code qui définit les variables doit figurer après la référence au fichier s_code.js.
* Assurez-vous que les [!UICONTROL identifiants de suite de rapports] dans la variable *`s_account`* du fichier s_code.js sont correctement définis. En règle générale, cette variable est définie correctement lorsque le code est téléchargé à partir du gestionnaire de code pour une suite de rapports spécifique ou lorsqu’il fourni par un conseiller technique Adobe.

Si vous souhaitez intégrer Analytics à Target, le fichier d’inclusion JavaScript doit être placé en bas de la page. L’exemple suivant montre le placement correct du code Analytics :

```js
<html> 
<head></head> 
<body> 
<!-- Analytics code version: H.20.3.
Copyright 1997-2009 Omniture, Inc. More info available at 
https://www.omniture.com --> 
<script language="JavaScript" type="text/javascript" src="https://www.yourdomain.com/js/s_code.js"></script> 
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
/************* DO NOT ALTER ANYTHING BELOW THIS LINE ! **************/ 
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<!-- End Analytics code version: H.20.3. --> 
</body> 
</html> 
```

