---
title: p_fo (Page First Only)
description: Permet de s’assurer que certaines routines ne se déclenchent qu’une seule fois par page.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Plug-in Adobe : p_fo (Page First Only)

>[!IMPORTANT] Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `p_fo` est un utilitaire qui vérifie l’existence d’un objet JavaScript spécifique. Si l’objet n’existe pas, alors le plug-in le crée et renvoie la valeur `true`. Si l’objet JavaScript existe déjà sur la page, alors il renvoie la valeur `false`. Ce plug-in est utile pour exécuter le code une seule fois sur une page. Plusieurs autres plug-ins dépendent de ce code pour fonctionner. Ce plug-in n’est pas nécessaire si vous n’avez pas besoin de connaître le nombre de fois que le code s’exécute sur une page ou si vous n’utilisez aucun plug-in dépendant.

## Installation du plug-in à l’aide de l’extension Adobe Experience Platform Launch

Adobe propose une extension qui vous permet d’utiliser les plug-ins les plus couramment utilisés.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Installation et publication de l’ [!UICONTROL Common Analytics Plugins] extension
1. Si ce n’est pas déjà fait, créez une règle intitulée « Initialiser les plug-ins » avec la configuration suivante :
   * Condition : aucune
   * Événement : Core - Bibliothèque chargée (Haut de la page)
1. Ajoutez une action à la règle ci-dessus avec la configuration suivante :
   * Extension : plug-ins Analytics communs
   * Type d’action : initialisation de p_fo
1. Enregistrez et publiez les modifications apportées à la règle.

## Installation du plug-in à l’aide de l’éditeur de code personnalisé de Launch

Si vous ne souhaitez pas utiliser l’extension du plug-in, vous pouvez utiliser l’éditeur de code personnalisé.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de votre choix.
1. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under the Adobe Analytics extension.
1. Développez l’ [!UICONTROL Configure tracking using custom code] accordéon, ce qui révèle le [!UICONTROL Open Editor] bouton.
1. Ouvrez l’éditeur de code personnalisé et collez le code de plug-in fourni ci-dessous dans la fenêtre de modification.
1. Enregistrez et publiez les modifications apportées à l’extension Analytics.

## Installation du plug-in à l’aide d’AppMeasurement

Copiez et collez le code suivant n’importe où dans le fichier AppMeasurement après l’instanciation de l’objet de suivi Analytics (à l’aide de [`s_gi`](../functions/s-gi.md)). La conservation des commentaires et des numéros de version du code dans votre mise en œuvre permet à Adobe de résoudre les éventuels problèmes.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `p_fo` utilise les arguments suivants :

* **on** (obligatoire, chaîne) : nom de l’objet JavaScript créé par le plug-in si celui-ci n’existe pas encore sur la page.

Si l’objet n’existe pas encore, cette méthode renvoie la valeur `true` et crée l’objet. Si l’objet existe déjà, cette méthode renvoie la valeur `false`.

## Exemples d’appels

### Exemple 1

Le code suivant vérifie l’existence de l’objet « myobject » dans la page.  Si l’objet « myobject » n’existe pas, le code le crée et renvoie la valeur true.  Par conséquent, le code de l’instruction conditionnelle (c’est-à-dire console.log(&quot;hello&quot;);) s’exécutera.

D’autre part, si l’objet « myobject » existe déjà au moment de l’appel p_fo, la fonction p_fo renvoie la valeur false et, par conséquent, l’instruction conditionnelle est définie sur false.  Dans ce cas, le code de l’instruction conditionnelle ne s’exécute pas.

```javascript
if(s.p_fo("myobject"))
{
  console.log("hello");
}
```

**REMARQUE :** chaque fois qu’un nouveau modèle DOM/nouvel objet de page se charge (ou que la page active se recharge), l’objet spécifié dans l’argument on disparaît et le plug-in p_fo renvoie à nouveau la valeur true la première fois qu’il s’exécute après la fin du chargement de la page.

## Historique des versions

### 2.0

* Nouvelle version (recompilé, taille de code réduite).
* Modification du type de la valeur renvoyée, qui passe d’un entier à une valeur booléenne.

### 1.0

* Version initiale.
