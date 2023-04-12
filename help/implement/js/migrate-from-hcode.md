---
title: Migration vers AppMeasurement pour JavaScript
description: Déterminez ce qui est nécessaire pour migrer votre mise en œuvre hors du code H.
feature: Implementation Basics
exl-id: ed606ab4-bd7d-4871-baa1-77e30fdd419e
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 91%

---

# Migration vers AppMeasurement pour JavaScript

Si votre mise en œuvre utilise toujours le code H, Adobe recommande vivement d’effectuer la migration vers la dernière version d’AppMeasurement. Il est recommandé d’implémenter Analytics par le biais des [balises dans Adobe Experience Platform](../launch/overview.md), mais il est possible d’utiliser une implémentation JavaScript mise à jour.

Les modifications notables suivantes sont présentes dans AppMeasurement par rapport au code H :

* 3 à 7 fois plus rapide que le code H.
* Plus clair que le code H : 21 ko décompressé par rapport au code H, qui est de 33 ko décompressé.
* La bibliothèque et le code de page peuvent être déployés dans la balise `<head>`.
* Le code H existant au niveau de la page est compatible avec AppMeasurement.
* La bibliothèque fournit des utilitaires natifs pour obtenir des paramètres de requête, lire et écrire des cookies et effectuer le suivi avancé des liens.
* La bibliothèque ne prend pas en charge les variables de configuration de compte dynamique (y compris `dynamicAccountSelection`, `dynamicAccountMatch` et `dynamicAccountList`).

Les étapes suivantes décrivent un processus de migration type.

1. **Téléchargez le nouveau fichier AppMeasurement** : accédez au nouveau fichier en vous connectant à Adobe Analytics, puis en accédant à Admin > Tous les administrateurs > Gestionnaire de code. Le fichier compressé téléchargé contient un fichier minifié `AppMeasurement.js`, ainsi que des modules Media et Integrate.
1. **Copiez vos personnalisations `s_code.js` dans`AppMeasurement.js`** : déplacez tout le code situé avant la section `DO NOT ALTER ANYTHING BELOW THIS LINE` dans `s_code.js` au début de `AppMeasurement.js`.
1. **Mettre à jour tous les modules externes**: Assurez-vous d’utiliser la dernière version de chaque plug-in répertorié dans votre `s_code.js` fichier . Cette étape comprend les modules Media et Integrate.
1. **Déployez le fichier AppMeasurement.js** : téléchargez votre fichier `AppMeasurement.js` sur votre serveur web.
1. **Mettez à jour les références de script pour renvoyer vers`AppMeasurement.js`** : assurez-vous que toutes les pages font référence à `AppMeasurement.js` au lieu de `s_code.js`.

## Exemple de code Appmeasurement

Un fichier type `AppMeasurement.js`. Assurez-vous que les variables de configuration sont définies au-dessus de la fonction `doPlugins`.

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
made when instructed to do so by your Adobe Account Team.*/
s.trackingServer="example.data.adobedc.net";

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

Veillez également à inclure une référence à `AppMeasurement.js` et `VisitorAPI.js` sur chaque page. Voir [Mise en œuvre JavaScript](/help/implement/js/overview.md) pour plus d’informations.
