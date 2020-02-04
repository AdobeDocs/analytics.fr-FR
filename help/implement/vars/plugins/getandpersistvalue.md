---
title: getAndPersistValue
description: Stockez une valeur qui peut être récupérée ultérieurement à tout moment.
translation-type: tm+mt
source-git-commit: e08f3e168a779f9678a109d7f533761629cd38f3

---


# Module externe Adobe : getAndPersistValue

> [!IMPORTANT] Ce module externe est fourni par le service de conseil d’Adobe afin d’optimiser l’utilisation d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce module externe, y compris l’installation ou le dépannage. Si vous avez besoin d’aide sur ce module externe, contactez le gestionnaire de compte de votre entreprise. Ils peuvent organiser une réunion avec un consultant pour obtenir de l&#39;aide.

Le `getAndPersistValue` module externe vous permet de stocker une valeur dans un cookie qui peut être récupérée ultérieurement au cours d’une visite. Il joue un rôle similaire à la fonction de durée [!UICONTROL de] stockage dans Adobe Experience Platform Launch. Adobe conseille d’utiliser ce module externe si vous souhaitez conserver automatiquement une variable Analytics à la même valeur dans les accès suivants une fois la variable définie. Ce module externe n’est pas nécessaire si la fonction de durée [!UICONTROL de] stockage de Launch est suffisante ou si vous n’avez pas besoin de définir et de conserver des variables avec la même valeur dans les accès suivants. La persistance intégrée des eVars ne nécessite pas l’utilisation de ce module externe, car ces variables persistent côté serveur par Adobe.

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
/* Adobe Consulting Plugin: getAndPersistValue v2.0 */
s.getAndPersistValue=function(vtp,cn,ex){var b=new Date;cn=cn?cn:"s_gapv";(ex=ex?ex:0)?b.setTime(b.getTime()+864E5*ex): b.setTime(b.getTime()+18E5);vtp||(vtp=this.c_r(cn));this.c_w(cn,vtp,b);return vtp};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du module externe

La `getAndPersist` méthode utilise les arguments suivants :

* **`vtp`**(obligatoire) : Valeur à conserver d’une page à l’autre
* **`cn`**(facultatif) : Nom du cookie pour stocker la valeur. Si cet argument n’est pas défini, le cookie est nommé`"s_gapv"`
* **`ex`**(facultatif) : Nombre de jours avant l’expiration du cookie. Si cet argument est`0`ou n’est pas défini, le cookie expire à la fin de la visite (30 minutes d’inactivité).

Si la variable de l’ `vtp` argument est définie, le plug-in définit le cookie, puis renvoie la valeur du cookie. Si la variable de l’ `vtp` argument n’est pas définie, le module externe renvoie uniquement la valeur du cookie.

## Exemples

### Exemple n° 1

Le code suivant définit eVar21 sur la valeur de &quot;hello&quot;.  Le code définira alors le cookie ev21gapv, qui expirera dans 28 jours, égal à la valeur d’eVar21 (c.-à-d. &quot;bonjour&quot;).  Le code définira alors (re)eVar21 sur la valeur du cookie ev21gapv.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemple n° 2

Supposons que l’eVar21 n’ait pas encore été définie sur la page active, mais qu’elle ait été définie sur &quot;salut&quot; sur une page précédente au cours des 28 derniers jours.   Le code suivant définit uniquement eVar21 sur la valeur du cookie ev21gapv (c.-à-d. &quot;bonjour&quot;).  Le cookie ev21gapv n’est pas réinitialisé, car eVar21 n’était pas définie sur la page active avant l’appel de la fonction.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemple n° 3

Supposons que l’eVar21 n’ait pas encore été définie sur la page active, mais qu’elle ait été définie sur &quot;salut&quot; sur une page précédente au cours des 28 derniers jours.  Le code suivant définit uniquement prop35 sur la valeur du cookie ev21gapv (c.-à-d. &quot;bonjour&quot;).  Il ne définit pas eVar21.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemple n° 4

Le code suivant définit eVar21 sur la valeur de &quot;howdy&quot;.  Le code définira ensuite (ou réinitialisera) le cookie ev21gapv, qui expirera dans 28 jours, égal à la valeur d’eVar21 (c.-à-d. &quot;howdy&quot;).  Le code définira ensuite prop35 comme la valeur du cookie ev21gapv (c.-à-d. &quot;howdy&quot;).

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemple n° 5

Supposons que s.eVar21 n&#39;ait été défini sur aucune page au cours des 28 derniers jours.  Le code suivant définit s.eVar21 comme étant nul, car le cookie ev21gapv aurait expiré 28 jours après sa dernière définition.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemple n° 6

Le code suivant définit eVar30 sur &quot;shopping&quot;.  Il définira ensuite le cookie s_gapv, qui expirera à la fin de la session du navigateur, comme la valeur de s.eVar30 (c.-à-d. &quot;shopping&quot;).  Il définira ensuite s.eVar30 sur la valeur du cookie s_gapv (c&#39;est-à-dire que l&#39;appel getAndPersistValue renvoie la valeur du cookie s_gapv, qui est dans ce cas &quot;shopping&quot;).

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

Si s.eVar30 n’est pas définie sur une valeur explicite sur des pages supplémentaires affichées pendant la session, mais est définie (dans doPlugins) via le code suivant...

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

...s.eVar30 sera définie sur &quot;shopping&quot; (c&#39;est-à-dire la valeur persistante du cookie s_gapv).

## Historique des versions

### 2.0 (16 avril 2018)

* Publication ponctuelle (taille de code réduite)
* La transmission de 0 dans l’ `ex` argument force désormais l’expiration après 30 minutes d’inactivité plutôt que l’expiration à la fin de la session du navigateur.

### 1.0 (18 janvier 2016)

* Version initiale.
