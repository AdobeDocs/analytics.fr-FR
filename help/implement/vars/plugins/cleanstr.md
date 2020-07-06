---
title: cleanStr
description: Permet de supprimer ou de remplacer tous les caractères superflus d’une chaîne.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 100%

---


# Plug-in Adobe : cleanStr

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `cleanStr` supprime ou remplace tous les caractères superflus d’une chaîne, y compris les caractères de la balise HTML, les espaces supplémentaires, les tabulations et les retours (chariot/à la ligne). Il remplace également les guillemets simples gauches/droits (`‘` et `’`) par des guillemets simples droits (`'`). Adobe recommande d’utiliser ce plug-in si vous souhaitez supprimer les caractères superflus des valeurs de variable et si la fonction « Texte clair » de Launch ne répond pas à vos besoins en matière de mise en œuvre. Ce plug-in n’est pas nécessaire si les données collectées ne contiennent pas de caractères superflus ou si la fonction « Texte clair » de Launch est suffisante.

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
   * Type d’action : initialisation de cleanStr
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
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
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

### 1.0 (15 avril 2018)

* Version initiale.
