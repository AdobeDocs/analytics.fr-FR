---
title: getTimeParting
description: Mesurez le moment où une action spécifique a lieu.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Module externe Adobe : getTimeParting

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin d’optimiser l’utilisation d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getTimeParting` module externe vous permet de capturer les détails du moment où une activité mesurable a lieu sur votre site. Ce module externe est utile lorsque vous souhaitez ventiler les mesures en fonction d’une division répétable du temps sur une période donnée. Par exemple, vous pouvez comparer les taux de conversion entre deux jours différents de la semaine, par exemple tous les dimanches et tous les jeudis. Vous pouvez également comparer les périodes de la journée, par exemple tous les matins et toutes les soirées.

Analysis Workspace fournit des dimensions prêtes à l’emploi similaires, légèrement formatées différemment de ce module externe. Pour plus d’informations, voir Dimensions [de répartition du](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) temps dans le guide de l’utilisateur Analyser. Certaines organisations estiment que les dimensions prêtes à l’emploi d’Analysis Workspace sont suffisantes.

> [IMPORTANT] version 4.0+ de ce module externe est significativement différent des versions antérieures. Adobe recommande vivement de mettre en oeuvre ce module externe &quot;à partir de zéro&quot;. Le code référençant le module externe avant la version 4.0 n’est pas compatible avec la version actuelle de ce module.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur une propriété.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Catalogue] .
1. Installation et publication de l’extension Plugins [!UICONTROL Analytics] communs
1. Pour toute règle de lancement dans laquelle vous souhaitez utiliser le module externe, ajoutez une action avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialiser addProductEvar
1. Enregistrer et publier les modifications apportées à la règle

## Installation du module externe à l’aide de l’éditeur de code personnalisé Lancer

Si vous ne souhaitez pas utiliser l’extension du module externe, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur la propriété souhaitée.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Développez la section [!UICONTROL Configurer le suivi à l’aide de l’accordéon de code] personnalisé, qui affiche le bouton [!UICONTROL Ouvrir l’éditeur] .
1. Ouvrez l’éditeur de code personnalisé et collez le code du module externe fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du module externe à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide `s_gi`). La conservation des commentaires et des numéros de version du code dans votre implémentation permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getTimeParting` méthode utilise l’argument suivant :

**`t`**(Facultatif mais recommandé, chaîne) : Nom du fuseau horaire auquel convertir l’heure locale du visiteur.  Par défaut, heure UTC/GMT. Voir[Liste des fuseaux horaires](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)de la base de données TZ sur Wikipedia pour une liste complète des valeurs valides.

Les valeurs valides courantes sont les suivantes :

* `"America/New_York"` pour l’heure de l’Est
* `"America/Chicago"` pour le temps central
* `"America/Denver"` pour le temps de montagne
* `"America/Los_Angeles"` pour le Pacifique

L’appel de cette méthode renvoie une chaîne contenant les éléments suivants délimités par une barre verticale (`|`) :

* L&#39;année en cours
* Le mois en cours
* Jour du mois
* Jour de la semaine
* Heure actuelle (AM/PM)

## Exemples d’appels

### Exemples de fuseaux horaires spécifiques

Utilisez l’exemple de code suivant si le client se trouve à Paris :

```js
s.eVarX = getTimeParting("Europe/Paris");
```

Si le client se trouve à San Jose, en Californie :

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```

Si le client est dans le pays africain du Ghana :

```js
s.eVarX = getTimeParting();
```

Le Ghana se trouve dans le fuseau horaire UTC/GMT.  Cet exemple montre qu&#39;aucun argument de module externe ne sera nécessaire dans de telles circonstances.

### Comptabilisation des navigateurs Internet Explorer

Utilisez l’exemple suivant si vous souhaitez exclure les données de division du temps des visiteurs d’Internet Explorer (puisque la valeur renvoyée par les navigateurs IE ne peut être que l’heure locale du visiteur).

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Résultats des appels

Si un visiteur de Denver se rend sur un site le 31 août 2020 à 9h15,

Exécution du code suivant...

```js
s.eVar10 = getTimeParting("Europe/Athens");
```

...définirait s.eVar10 sur &quot;year=2020| month=August| date=31| day=Friday| time=18:15 PM&quot;

Pendant que le code suivant...

```js
s.eVar10 = getTimeParting("America/Nome");
```

...définirait s.eVar10 sur &quot;year=2020| month=August| date=31| day=Friday| time=6:15 AM&quot;

Le code suivant...

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

...définirait s.eVar10 sur &quot;year=2020| month=August| date=31| day=Friday| heure=20h45&quot;

Et le code suivant...

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

...définirait s.eVar10 sur &quot;year=2020| month=Septembre| date=1| day=samedi| time=1:15 AM&quot;

## Historique des versions

### 6.2 (5 novembre 2019)

* Correctifs pour petits bogues
* Réduction de la taille globale du code

### 6.1 (26 novembre 2018)

* Correctif pour les navigateurs Internet Explorer. Ils peuvent renvoyer l’heure, mais uniquement l’heure locale du visiteur.

### 6.0 (14 août 2018)

* Réécrire pour répondre aux normes internationales. Convertit désormais correctement l’épargne-jour et tous les fuseaux horaires.

### 5.0 (17 avril 2018)

* Version ponctuelle (recompilée, taille de code réduite)
* Suppression du besoin du `tpDST` paramètre, puisque les dates de début/fin de l’économie d’été sont désormais détectées automatiquement

### 4.0 (22 août 2016)

* Fournit une toute nouvelle solution et inclut désormais des informations sur l’année, le mois et la date.
