---
description: valeur nulle
keywords: Analytics Implementation;link reference;redir
title: Mesure de liens personnalisés sur des protocoles mobiles
topic: Developer and implementation
uuid: eb82de26-da2e-41c2-8924-59b6b5ccef28
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mesure de liens personnalisés sur des protocoles mobiles

De nombreux mobinautes téléchargent sur leurs appareils des fichiers tels que des podcasts, des sonneries, etc. Etant donné que de nombreux appareils mobiles ne prennent pas en charge le langage JavaScript, la mesure des liens doit être implémentée par le biais de redirections. Pour utiliser des redirections, vous devez modifier les liens href dans le fichier HTML afin d’inclure l’élément REDIR. Le format général d’un lien personnalisé est le suivant :

```
https://<your_Namespace>.112.2o7.net/b/ss/<RSID>/4/REDIR/
?url=<destination_URL>&pe=<link_type>&pev1=<current_URL>&pev2=<link_name>
```

Veuillez tenir compte des points suivants lors de la création d’une référence de lien :

* La valeur URL doit être en codage URL.
* Vous devez définir un paramètre pageName ou URL de page (g).
* Les variables dynamiques peuvent lire le paramètre URL, mais pas le définir.
* Si aucun cookie n’est défini, les serveurs Adobe effectuent une négociation du cookie standard.
* Pour effectuer le suivi des liens, vous devez inclure les paramètres pe, pev1 et pev2.

Une URL de mesure de liens personnalisés se présente comme suit :

```
<a href=" https://johnny_appleseed.122.2o7.net/b/ss/appleseedpodcasts/4/REDIR/
?url=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pe=lnk_d
&pev1=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pev2=pl anting_apple_trees&">Planting an Apple Tree</a>
```

Pour plus d’informations, voir le [livre blanc Redirections de suivi de liens de sortie](https://marketing.adobe.com/resources/help/en_US/whitepapers/redirects/).
