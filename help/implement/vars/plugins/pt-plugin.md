---
title: pt
description: Permet d’exécuter une fonction sur une liste de variables.
translation-type: tm+mt
source-git-commit: e2afe854a4141510fe2ecd85aa6df59f6751d0f5

---


# Plug-in Adobe : pt

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `pt` exécute une fonction ou une méthode dans une liste de variables Analytics. Par exemple, vous pouvez exécuter la méthode [`clearVars`](../functions/clearvars.md) de manière sélective sur plusieurs variables sans avoir à l’appeler manuellement à chaque fois. Plusieurs autres plug-ins dépendent de ce code pour s’exécuter correctement. Ce plug-in n’est pas nécessaire si vous n’avez pas besoin d’exécuter une fonction spécifique sur plusieurs variables Analytics à la fois, ou si vous n’utilisez aucun plug-in dépendant.

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
   * Type d’action : initialisation de pt
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
/* Adobe Consulting Plugin: pt v2.01 */
 s.pt=function(l,de,cf,fa){if(l&&this[cf]){l=l.split(de||",");de=l.length;for(var e,c=0;c<de;c++)if(e=this[cf](l[c],fa))return e}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `pt` utilise les arguments suivants :

* **`l`** (obligatoire, chaîne) : liste des variables sur lesquelles la fonction contenue dans l’argument `cf` peut s’exécuter.
* **`de`** (facultatif, chaîne) : délimiteur qui sépare la liste des variables dans l’argument `l`. Par défaut, il s’agit d’une virgule (`,`).
* **`cf`** (obligatoire, chaîne) : nom de la fonction de rappel contenue dans l’objet AppMeasurement à appeler par rapport à chacune des variables contenues dans l’argument `l`.
* **`fa`** (facultatif, chaîne) : si la fonction de l’argument `cf` appelle des arguments supplémentaires lors de son exécution, incluez-les ici. La valeur par défaut est `undefined`.

L’appel de cette méthode renvoie une valeur si la fonction de rappel (dans l’argument `cf`) en renvoie une.

## Exemples d’appels

### Exemple 1

Le code suivant fait partie du plug-in getQueryParam.  Il exécute la fonction d’assistance getParameterValue sur chacune des paires clé-valeur contenues dans la chaîne de requête de l’URL (fullQueryString).  Pour extraire chaque paire clé-valeur, la chaîne fullQueryString doit être délimitée et séparée par une esperluette « &amp; ». parameterKey fait référence au paramètre de chaîne de requête que le plug-in cherche spécifiquement à extraire de la chaîne de requête.

```javascript
returnValue = s.pt(fullQueryString, "&", "getParameterValue", parameterKey)
```

La ligne ci-dessus est un raccourci pour exécuter un code semblable à celui présenté ci-dessous :

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

### 2.01 (24 septembre 2019)

* Modifications mineures du code pour réduire la taille globale.

### 2.0 (17 avril 2018)

* Nouvelle version (recompilé, taille de code réduite).
* Ajout de la prise en charge du code H et d’AppMeasurement.

### 1.0 (23 septembre 2013)

* Version initiale.
