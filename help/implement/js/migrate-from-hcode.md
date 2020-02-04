---
title: Migration vers AppMeasurement pour JavaScript
description: Déterminez ce qui est nécessaire pour migrer votre implémentation hors du code H.
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Migration vers AppMeasurement pour JavaScript

Si votre implémentation utilise toujours le code H, Adobe recommande vivement d’effectuer la migration vers la dernière version d’AppMeasurement. Il est recommandé d’implémenter Analytics par le biais d’ [Adobe Experience Platform Launch](../launch/overview.md) , mais il est possible d’utiliser une mise en oeuvre JavaScript mise à jour.

Les modifications notables suivantes sont présentes dans AppMeasurement par rapport au code H :

* 3 à 7 fois plus rapide que le code H.
* Plus clair que le code H - 21kb décompressé par rapport au code H, qui est de 33kb décompressé.
* La bibliothèque et le code de page peuvent être déployés dans la balise `<head>`.
* Le code H existant au niveau de la page est compatible avec AppMeasurement.
* La bibliothèque fournit des utilitaires natifs pour obtenir des paramètres de requête, lire et écrire des cookies et effectuer le suivi avancé des liens.
* La bibliothèque ne prend pas en charge les variables de configuration de compte dynamique (y compris `dynamicAccountSelection`, `dynamicAccountMatch`et `dynamicAccountList`).
* Le module Survey n’est pas pris en charge.

Les étapes suivantes décrivent un processus de migration type.

1. **Téléchargez le nouveau fichier** AppMeasurement : Accédez au nouveau fichier en vous connectant à Adobe Analytics, puis en accédant à Admin > Gestionnaire de code. Le fichier compressé téléchargé contient un `AppMeasurement.js` fichier minifié, ainsi que des modules Media et Integrate.
1. **Copiez vos`s_code.js`personnalisations dans`AppMeasurement.js`**: Déplacez tout le code situé avant la`DO NOT ALTER ANYTHING BELOW THIS LINE`section`s_code.js`au début de`AppMeasurement.js`.
1. **Mettre à jour tous les plug-ins**: Vérifiez que vous utilisez la dernière version de chaque module externe répertorié dans votre `s_code.js` fichier. Cela inclut les modules Media et Integrate.
1. **Déployez le fichier** AppMeasurement.js : Téléchargez votre `AppMeasurement.js` fichier sur votre serveur Web.
1. **Mettez à jour les références de script pour pointer vers`AppMeasurement.js`**: Assurez-vous que toutes les pages font référence`AppMeasurement.js`à`s_code.js`.

## Exemple de code Appmeasurement

Un `AppMeasurement.js` fichier type. Assurez-vous que les variables de configuration sont définies au-dessus de la `doPlugins` fonction.

```js
// Initialize AppMeasurement
var s = s_gi("examplersid");

/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/;
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE");

/************************** CONFIG SECTION **************************/;
/* You may add or alter any code config here. */
s.trackDownloadLinks = true;
s.trackExternalLinks = true;
s.trackInlineStats = true;
s.linkDownloadFileTypes = "exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx";
s.linkInternalFilters = "javascript:,example.com";

s.usePlugins = true;
function s_doPlugins(s) {

// Use implementation plug-ins that are defined below in this section

}
s.doPlugins = s_doPlugins;

/* WARNING: Changing any of the below variables will cause drastic
changes to how your visitor data is collected.  Changes should only be
made when instructed to do so by your account manager.*/
s.trackingServer="example.sc.omtrdc.net";

/************************** PLUGINS SECTION *************************/

// Copy and paste implementation plug-ins here. Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** MODULES *****************************/

// Copy and paste implementation modules (Media, Integrate) here.

/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  */
```

## Exemple de code de page

Code type chargé sur chaque page.

```html
<script src="AppMeasurement.js"></script>
<script language="JavaScript" type="text/javascript">
s.pageName = "Example page name";
s.eVar1 = "Example eVar value";
s.events = "event1";
s.t();
</script>
```

Veillez également à inclure une référence à `AppMeasurement.js` et `VisitorAPI.js` sur chaque page. Voir Mise en oeuvre [](/help/implement/js/overview.md) JavaScript pour plus d’informations.
