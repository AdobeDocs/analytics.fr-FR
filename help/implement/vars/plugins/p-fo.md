---
title: p_fo (Page d'abord uniquement)
description: Assurez-vous que certaines routines ne se déclenchent qu’une seule fois par page.
translation-type: tm+mt
source-git-commit: 26f06adbef1608a6e01df3ab1d3ad4ba78abc28f

---


# Module externe Adobe :p_fo (Page d&#39;abord uniquement)

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin d’optimiser l’utilisation d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `p_fo` module externe est un utilitaire qui vérifie l’existence d’un objet JavaScript spécifique. Si l’objet n’existe pas, le module externe crée l’objet et renvoie `true`. Si l’objet JavaScript existe déjà sur la page, il renvoie `false`. Ce module externe est utile pour exécuter le code une seule fois sur une page. Plusieurs autres plug-ins dépendent de ce code pour fonctionner. Ce module externe est inutile si vous n’êtes pas inquiet du nombre de fois où le code s’exécute sur une page ou si vous n’utilisez aucun module externe dépendant.

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
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `p_fo` méthode utilise les arguments suivants :

* **on** (obligatoire, chaîne) : Nom de l’objet JavaScript créé par le module externe si l’objet n’existe pas encore sur la page.

Si l’objet n’existe pas encore, cette méthode renvoie `true` et crée l’objet. Si l’objet existe déjà, cette méthode renvoie `false`.

## Exemples d’appels

### Exemple n° 1

Le code suivant vérifie l’existence de l’objet &quot;myobject&quot; dans la page.  Si l’objet &quot;myobject&quot; n’existe pas, le code crée l’objet &quot;myobject&quot; et renvoie la valeur true.  Par conséquent, le code de l’instruction conditionnelle (c.-à-d. Console.log(&#39;hello&#39;);) s’exécutera.

D’un autre côté, si l’objet &quot;myobject&quot; existe déjà lors de l’appel p_fo, la fonction p_fo renvoie la valeur false et, par conséquent, l’instruction conditionnelle est considérée comme false.  Dans ce cas, le code de l’instruction conditionnelle ne s’exécute pas.

```javascript
if(s.p_fo("myobject"))
{
  console.log("hello");
}
```

**** REMARQUE : Chaque fois qu’un nouvel objet de page/DOM est chargé (ou que la page active est rechargée), l’objet spécifié dans l’argument on n’existe plus et le plug-in p_fo renvoie à nouveau la valeur true la première fois qu’il s’exécute après la fin du chargement de la page.

## Historique des versions

### 2.0

* Publication ponctuelle (recompilée, taille de code réduite).
* Modification du type de valeur de retour d’un entier en booléen

### 1.0

* Version initiale.
