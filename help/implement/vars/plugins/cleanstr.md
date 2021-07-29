---
title: cleanStr
description: Permet de supprimer ou de remplacer tous les caractères superflus d’une chaîne.
exl-id: d699dcd4-5e0a-40d3-b345-e5b1a077d393
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 82%

---

# Plug-in Adobe : cleanStr

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `cleanStr` supprime ou remplace tous les caractères superflus d’une chaîne, y compris les caractères de la balise HTML, les espaces supplémentaires, les tabulations et les retours (chariot/à la ligne). Il remplace également les guillemets simples gauches/droits (`‘` et `’`) par des guillemets simples droits (`'`). Adobe recommande d’utiliser ce plug-in si vous souhaitez supprimer les caractères superflus des valeurs de variable et que la fonction &quot;Texte clair&quot; de Adobe Experience Platform ne répond pas à vos besoins de mise en oeuvre. Ce plug-in n’est pas nécessaire si les données collectées ne contiennent pas de caractères superflus, ou si la fonction &quot;Texte clair&quot; de l’interface utilisateur de la collecte de données est suffisante.

## Installation du module externe à l’aide de balises dans Adobe Experience Platform

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Catalogue].
1. Installez et publiez l’extension [!UICONTROL Plug-ins Analytics communs].
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation de cleanStr
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé de 

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous l’extension Adobe Analytics.
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

La méthode `cleanStr` utilise les arguments suivants :

* **`str`** (obligatoire, chaîne) : valeur souhaitée pour supprimer le codage HTML, les espaces supplémentaires, les tabulations ou autres caractères superflus.

La méthode renvoie la valeur de l’argument `str` avec tous les caractères superflus supprimés.

## Exemples

### Exemple 1

Prenons le scénario suivant (où les points représentent des espaces et les flèches des caractères de tabulation)

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Lorsque vous exécutez le code suivant…

```js
s.eVar1 = cleanStr(s.eVar1)
```

eVar1 est défini sur « this is a messystring » (avec tous les espaces supplémentaires et caractères de tabulation supprimés).

### Exemple 2

Si…

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

…et que le code suivant s’exécute…

```js
cleanStr(s.eVar1)
```

…alors la valeur finale de s.eVar1 reste :

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Exécuter le plug-in seul (sans attribuer la valeur renvoyée à une variable) ne « réinitialise » pas réellement la variable transmise par le biais de l’argument str.

## Historique des versions

### 2.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 1.0 (15 avril 2018)

* Version initiale.
