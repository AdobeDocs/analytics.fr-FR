---
title: cleanStr
description: Permet de supprimer ou de remplacer tous les caractères superflus d’une chaîne.
feature: Variables
exl-id: d699dcd4-5e0a-40d3-b345-e5b1a077d393
source-git-commit: c53f886d5329e2a3b5023f9396c3aa2360a86901
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 80%

---

# Plug-in Adobe : cleanStr

{{plug-in}}

Le plug-in `cleanStr` supprime ou remplace tous les caractères superflus d’une chaîne, y compris les caractères de la balise HTML, les espaces supplémentaires, les tabulations et les retours (chariot/à la ligne). Il remplace également les guillemets simples gauches/droits (`‘` et `’`) par des guillemets simples droits (`'`). Adobe recommande d’utiliser ce plug-in si vous souhaitez supprimer les caractères superflus des valeurs de variable et que la fonction &quot;Texte clair&quot; de la collecte de données Adobe Experience Platform ne répond pas à vos besoins de mise en oeuvre. Ce plug-in n’est pas nécessaire si les données collectées ne contiennent pas de caractères superflus, ou si la fonction &quot;Texte clair&quot; de la collecte de données Adobe Experience Platform est suffisante.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize cleanStr
1. Save and publish the changes to the rule.-->

## Installation du plug-in à l’aide de l’éditeur de code personnalisé

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

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
/* Adobe Consulting Plugin: cleanStr v2.0 (No Prerequisites Required) */
function cleanStr(str){var a=str;if("-v"===a)return{plugin:"cleanStr",version:"2.0"};a:{if("undefined"!==typeof window.s_c_il){var b=0;for(var c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c){b=c;break a}}b=void 0}"undefined"!==typeof b&&(b.contextData.cleanStr="2.0");if("string"===typeof a){a=a.replace(/<\/?[^>]+(>|$)/g,"");a=a.trim();a=a.replace(/[\u2018\u2019\u201A]/g,"'");a=a.replace(/\t+/g,"");for(a=a.replace(/[\n\r]/g," ");-1<a.indexOf("  ");)a=a.replace(/\s\s/g," ");return a}return""}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La fonction `cleanStr` utilise les arguments suivants :

* **`str`** (obligatoire, chaîne) : valeur souhaitée pour supprimer le codage HTML, les espaces supplémentaires, les tabulations ou autres caractères superflus.

La fonction renvoie la valeur de lʼargument `str` avec tous les caractères superflus supprimés.

## Exemples

```js
// Returns the value "this is a messystring". Note that both tabs and extra spaces are present in the original string.
// Multiple spaces are reduced to one, while tabs are omitted entirely.
s.eVar1 = "  this  is a      messy  string    ";
s.eVar1 = cleanStr(s.eVar1)

// This function call does not do anything because the code does not assign the returned value to a variable.
s.eVar1 = "  this  is a      messy  string    ";
cleanStr(s.eVar1);
```

## Historique des versions

### 2.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 1.0 (15 avril 2018)

* Version initiale.
