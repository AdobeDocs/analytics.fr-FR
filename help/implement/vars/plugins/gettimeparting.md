---
title: getTimeParting
description: Permet de mesurer le moment où une action spécifique a lieu.
feature: Variables
exl-id: 3fab36c8-a006-405a-9ef1-2547c2b36b0d
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 77%

---

# Plug-in Adobe : getTimeParting

{{plug-in}}

Le plug-in `getTimeParting` vous permet de saisir les détails du moment où une activité mesurable a lieu sur votre site. Ce plug-in est utile lorsque vous souhaitez répartir des mesures en fonction d’une division répétable du temps sur une période donnée. Ainsi, vous pouvez comparer les taux de conversion entre deux jours différents de la semaine, par exemple tous les dimanches contre tous les jeudis. Vous pouvez également comparer les périodes de la journée, par exemple tous les matins contre tous les soirs.

Analysis Workspace fournit des dimensions similaires, prêtes à l’emploi, dont le format est légèrement différent de celui de ce plug-in. Pour plus d’informations, consultez la section [Dimensions de répartition du temps](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) dans le guide d’utilisation Analyser. Certaines organisations estiment que les dimensions prêtes à l’emploi d’Analysis Workspace sont suffisantes.

>[!IMPORTANT]
>
>La version 4.0+ de ce plug-in est sensiblement différente par rapport aux versions précédentes. Adobe recommande vivement de mettre en œuvre ce plug-in de A à Z. Le code référençant le plug-in avant la version 4.0 n’est pas compatible avec la version actuelle de ce plug-in.

## Installation du module externe à l’aide de l’extension SDK Web

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec le SDK Web.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur **[!UICONTROL Balises]** sur la gauche, puis cliquez sur la propriété de balise de votre choix.
1. Cliquez sur **[!UICONTROL Extensions]** sur la gauche, puis cliquez sur le bouton **[!UICONTROL Catalogue]** tab
1. Recherchez et installez le **[!UICONTROL Plug-ins SDK Web courants]** extension .
1. Cliquez sur **[!UICONTROL Éléments de données]** sur la gauche, puis cliquez sur l’élément de données souhaité.
1. Définissez le nom de l’élément de données souhaité avec la configuration suivante :
   * Extension : modules externes SDK Web courants
   * Élément de données : `getTimeParting`
1. Définissez la variable `Time Zone` sur la droite.
1. Enregistrez et publiez les modifications sur l’élément de données.

## Installation manuelle du plug-in implémentant le SDK Web

Ce module externe n’est pas encore pris en charge pour une utilisation dans une mise en oeuvre manuelle du SDK Web.

## Installation du module externe à l’aide de l’extension Adobe Analytics

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés avec Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation de getTimeParting
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension de plug-in Plugins Analytics communs, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à la [collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous l’extension Adobe Analytics.
1. Développez l’accordéon [!UICONTROL Configurer le suivi à l’aide d’un code personnalisé], qui affiche le bouton [!UICONTROL Ouvrir l’éditeur].
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.3 (No Prerequisites Needed) */
function getTimeParting(t){var c=t;if("-v"===t)return{plugin:"getTimeParting",version:"6.3"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getTimeParting="6.3");c=document.documentMode?void 0:c||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:c,minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `getTimeParting` utilise lʼargument suivant :

**`t`** (facultatif mais recommandé, chaîne) : nom du fuseau horaire auquel convertir l’heure locale du visiteur.  Par défaut, il s’agit de l’heure UTC/GMT. Consultez la [liste des fuseaux horaires de la tz database](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) sur Wikipédia pour obtenir une liste complète des valeurs valides.

Les valeurs valides courantes sont les suivantes :

* `"America/New_York"` pour l’heure de l’Est
* `"America/Chicago"` pour l’heure normale du Centre
* `"America/Denver"` pour l’heure des Rocheuses
* `"America/Los_Angeles"` pour l’heure du Pacifique

Lʼappel de cette fonction renvoie une chaîne contenant les éléments suivants délimités par une barre verticale (`|`) :

* L’année en cours
* Le mois en cours
* Le jour du mois
* Le jour de la semaine
* L’heure actuelle (matin/après-midi)

## Exemples

```js
// Use the following code if the visitor resides in Paris, France
s.eVar8 = getTimeParting("Europe/Paris");

// Use the following code if the visitor resides in San Jose, California
s.eVar17 = getTimeParting("America/Los_Angeles");

// Use the following code if the visitor resides in Ghana.
// Note that Ghana is in GMT time, the default time zone that the plug-in uses with no argument
s.eVar22 = getTimeParting();

// Internet Explorer only returns the visitor's local time. Use this conditional statement to accommodate IE visitors
if(!document.documentMode) s.eVar39 = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";

// Given a visitor from Denver Colorado visits a site on August 31, 2020 at 9:15 AM
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"
s.eVar10 = getTimeParting("Europe/Athens");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"
s.eVar11 = getTimeParting("America/Nome");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"
s.eVar12 = getTimeParting("Asia/Calcutta");

// Returns the string value "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"
s.eVar13 = getTimeParting("Australia/Sydney");
```

## Historique des versions

### 6.3 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 6.2 (5 novembre 2019)

* Corrections de bogues mineurs
* Réduction de la taille globale du code

### 6.1 (26 novembre 2018)

* Correctif pour les navigateurs Internet Explorer. Ils peuvent renvoyer l’heure, mais uniquement à l’heure locale du visiteur.

### 6.0 (14 août 2018)

* Réécriture complète pour tenir compte des normes internationales. L’heure d’été et tous les fuseaux horaires sont désormais convertis correctement.

### 5.0 (17 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Suppression de la nécessité du paramètre `tpDST`, puisque les dates de début et de fin de l’heure d’été sont désormais détectées automatiquement.

>[!CAUTION]
>
>Les versions précédentes de ce module externe ne tenaient pas compte de toutes les années à venir. Si vous utilisez une version précédente de ce module externe, Adobe recommande vivement dʼeffectuer la mise à niveau vers la dernière version afin dʼéviter des erreurs JavaScript et des pertes de données. Si la mise à niveau de ce module nʼest pas possible, veillez à ce que la variable `s._tpdst` du code de module externe contienne les années appropriées dans le futur.

### 4.0 (22 août 2016)

* Fournit une toute nouvelle solution et inclut désormais des informations sur l’année, le mois et la date.
