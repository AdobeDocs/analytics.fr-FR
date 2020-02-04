---
title: pt
description: Exécute une fonction sur une liste de variables.
translation-type: tm+mt
source-git-commit: 180ad544541f25d02b3a257559bc045abed7387b

---


# Module externe Adobe : pt

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `pt` module externe exécute une fonction ou une méthode dans une liste de variables Analytics. Par exemple, vous pouvez exécuter la `clearVars` méthode de manière sélective sur plusieurs variables sans appeler manuellement la méthode à chaque fois. Plusieurs autres plug-ins dépendent de ce code pour s’exécuter correctement. Ce module externe n’est pas nécessaire si vous n’avez pas besoin d’exécuter une fonction spécifique sur plusieurs variables Analytics à la fois, ou si vous n’utilisez aucun module externe dépendant.

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
   * Type d&#39;action : Initialiser pt
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
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `pt` méthode utilise les arguments suivants :

* **`l`**(obligatoire, chaîne) : Liste des variables sur lesquelles la fonction contenue dans l&#39;`cf`argument peut s&#39;exécuter.
* **`de`**(facultatif, chaîne) : Délimiteur qui sépare la liste des variables dans l’`l`argument. La valeur par défaut est une virgule (`,`).
* **`cf`**(obligatoire, chaîne) : Nom de la fonction de rappel contenue dans l’objet AppMeasurement à appeler par rapport à chacune des variables contenues dans l’`l`argument.
* **`fa`**(facultatif, chaîne) : Si la fonction de l’`cf`argument appelle des arguments supplémentaires lors de son exécution, incluez-les ici. Par défaut,`undefined`.

L’appel de cette méthode renvoie une valeur si la fonction de rappel (dans l’ `cf` argument) renvoie une valeur.

## Exemples d’appels

### Exemple n° 1

Le code suivant fait partie du plug-in getQueryParam.  Elle exécute la fonction d’aide getParameterValue sur chacune des paires clé-valeur contenues dans la chaîne de requête de l’URL (fullQueryString).  Pour extraire chaque paire clé-valeur, fullQueryString doit être délimité et séparé par un caractère d’esperluette &quot;&amp;&quot;. Le paramètreKey fait référence au paramètre de chaîne de requête que le module externe tente spécifiquement d&#39;extraire de la chaîne de requête.

```javascript
returnValue = s.pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

La ligne ci-dessus est un raccourci pour l’exécution du code qui ressemble à ce qui suit :

```js
var returnValue = "",
  parameters = fullQueryString.split("&"),
  parametersLength = parameters.length;
for(var i = 0; i < parametersLength; i++)
{
  returnValue = s.getParameterValue(parameters[i], parameterKey);
  if(returnValue !== "") break;
}
```

## Historique des versions

### 2.01 (24 septembre 2019)

* Modifications mineures du code pour réduire la taille globale

### 2.0 (17 avril 2018)

* Publication ponctuelle (recompilée, taille de code réduite).
* Ajout de la prise en charge du code H et d’AppMeasurement.

### 1.0 (23 septembre 2013)

* Version initiale.
