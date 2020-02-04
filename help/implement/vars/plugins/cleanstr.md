---
title: cleanStr
description: Supprimez ou remplacez tous les caractères superflus d’une chaîne.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Module externe Adobe :cleanStr

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `cleanStr` module externe supprime ou remplace tous les caractères superflus d’une chaîne, y compris les caractères de balise HTML, les espaces blancs supplémentaires, les onglets et les retours chariot/nouvelle ligne. Il remplace également les guillemets simples gauche/droite (`‘` et `’`) les guillemets simples droits (`'`). Adobe recommande d’utiliser ce module externe si vous souhaitez supprimer les caractères superflus des valeurs de variable et que la fonction &quot;Nettoyer le texte&quot; dans Launch ne répond pas à vos besoins en matière d’implémentation. Ce module externe n’est pas nécessaire si les données collectées ne contiennent pas de caractères superflus ou si la fonction &quot;Nettoyer le texte&quot; du lancement est suffisante.

## Installation du module externe à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
1. Cliquez sur une propriété.
1. Accédez à l’onglet [!UICONTROL Extensions] , puis cliquez sur le bouton [!UICONTROL Catalogue] .
1. Installation et publication de l’extension Plugins [!UICONTROL Analytics] communs
1. Si ce n’est déjà fait, créez une règle intitulée &quot;Initialiser les modules externes&quot; avec la configuration suivante :
   * Condition : Aucun
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : Plug-ins Analytics courants
   * Type d&#39;action : Initialiser cleanStr
1. Enregistrez et publiez les modifications apportées à la règle.

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
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `cleanStr` méthode utilise les arguments suivants :

* **`str`**(obligatoire, chaîne) : Valeur que vous souhaitez nettoyer le codage HTML, les espaces blancs supplémentaires, les onglets ou d’autres caractères inutiles.

La méthode renvoie la valeur de l’ `str` argument avec tous les caractères superflus supprimés.

## Exemples

### Exemple n° 1

Supposons que les points suivants (où les points représentent les espaces et les flèches représentent les caractères de tabulation)

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Lorsque vous exécutez le code suivant...

```js
s.eVar1 = cleanStr(s.eVar1)
```

...eVar1 sera définie sur &quot;this is a messystring&quot; (avec tous les espaces supplémentaires et tous les caractères de tabulation supprimés).

### Exemple n° 2

Si la variable...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...et le code suivant s&#39;exécute...

```js
cleanStr(s.eVar1)
```

...la valeur finale de s.eVar1 sera toujours :

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

L’exécution du plug-in tout seul (sans affecter la valeur renvoyée à une variable) ne &quot;réinitialise&quot; pas en fait la variable transmise par l’intermédiaire de l’argument str.

## Historique des versions

### 1.0 (15 avril 2018)

* Version initiale.
