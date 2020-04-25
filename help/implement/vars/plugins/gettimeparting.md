---
title: getTimeParting
description: Permet de mesurer le moment où une action spécifique a lieu.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : getTimeParting

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getTimeParting` vous permet de saisir les détails du moment où une activité mesurable a lieu sur votre site. Ce plug-in est utile lorsque vous souhaitez ventiler des mesures en fonction d’une division répétable du temps sur une période donnée. Ainsi, vous pouvez comparer les taux de conversion entre deux jours différents de la semaine, par exemple tous les dimanches contre tous les jeudis. Vous pouvez également comparer les périodes de la journée, par exemple tous les matins contre tous les soirs.

Analysis Workspace fournit des dimensions similaires, prêtes à l’emploi, dont le format est légèrement différent de celui de ce plug-in. Pour plus d’informations, consultez la section [Dimensions de répartition du temps](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) dans le guide d’utilisation Analyser. Certaines organisations estiment que les dimensions prêtes à l’emploi d’Analysis Workspace sont suffisantes.

>[IMPORTANT] La version 4.0+ de ce plug-in est sensiblement différente par rapport aux versions précédentes. Adobe recommande vivement de mettre en œuvre ce plug-in de A à Z. Le code référençant le plug-in avant la version 4.0 n’est pas compatible avec la version actuelle de ce plug-in.

## Installation du plug-in à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation de getTimeParting
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé de Launch

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Configurer le suivi à l’aide d’un code personnalisé], qui affiche le bouton [!UICONTROL Ouvrir l’éditeur].
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getTimeParting` utilise l’argument suivant :

**`t`** (facultatif mais recommandé, chaîne) : nom du fuseau horaire auquel convertir l’heure locale du visiteur.  Par défaut, il s’agit de l’heure UTC/GMT. Consultez la [liste des fuseaux horaires de la tz database](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) sur Wikipédia pour obtenir une liste complète des valeurs valides.

Les valeurs valides courantes sont les suivantes :

* `"America/New_York"` pour l’heure de l’Est
* `"America/Chicago"` pour l’heure normale du Centre
* `"America/Denver"` pour l’heure des Rocheuses
* `"America/Los_Angeles"` pour l’heure du Pacifique

L’appel de cette méthode renvoie une chaîne contenant les éléments suivants délimités par une barre verticale (`|`) :

* L’année en cours
* Le mois en cours
* Le jour du mois
* Le jour de la semaine
* L’heure actuelle (matin/après-midi)

## Exemples d’appels

### Exemples de fuseaux horaires spécifiques

Utilisez l’exemple de code suivant si le client se trouve à Paris, en France :

```js
s.eVarX = getTimeParting("Europe/Paris");
```

Si le client se trouve à San José, en Californie :

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```

Si le client se trouve dans le pays africain du Ghana :

```js
s.eVarX = getTimeParting();
```

Le Ghana se trouve dans le fuseau horaire UTC/GMT.  Cet exemple montre qu’aucun argument de plug-in ne sera nécessaire dans de telles circonstances.

### Prise en compte des navigateurs Internet Explorer

Utilisez l’exemple suivant si vous souhaitez exclure les données relatives à la répartition du temps des visiteurs d’Internet Explorer (puisque la valeur renvoyée par les navigateurs IE ne peut être que l’heure locale du visiteur).

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Résultats des appels

Si un visiteur de Denver, dans le Colorado, se rend sur un site le 31 août 2020 à 9 h 15 :

En exécutant le code suivant…

```js
s.eVar10 = getTimeParting("Europe/Athens");
```

…s.eVar10 serait défini sur « year=2020 | month=August | date=31 | day=Friday | time=6:15 PM ».

Alors que le code suivant…

```js
s.eVar10 = getTimeParting("America/Nome");
```

…définirait s.eVar10 sur « year=2020 | month=August | date=31 | day=Friday | time=6:15 AM ».

Le code suivant…

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

…définirait s.eVar10 sur « year=2020 | month=August | date=31 | day=Friday | time=8:45 PM ».

Et le code suivant…

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

…définirait s.eVar10 sur « year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM ».

## Historique des versions

### 6.2 (5 novembre 2019)

* Corrections de bogues mineurs
* Réduction de la taille globale du code

### 6.1 (26 novembre 2018)

* Correctif pour les navigateurs Internet Explorer. Ils peuvent indiquer l’heure, mais uniquement en fonction de l’heure locale du visiteur.

### 6.0 (14 août 2018)

* Réécriture complète pour tenir compte des normes internationales. L’heure d’été et tous les fuseaux horaires sont désormais convertis correctement.

### 5.0 (17 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Suppression de la nécessité du paramètre `tpDST`, puisque les dates de début et de fin de l’heure d’été sont désormais détectées automatiquement.

### 4.0 (22 août 2016)

* Fournit une toute nouvelle solution et inclut désormais des informations sur l’année, le mois et la date.
