---
title: getAndPersistValue
description: Permet de stocker une valeur qui peut être récupérée ultérieurement à tout moment.
translation-type: ht
source-git-commit: a2970e05abf0d1f963175db6e3554aa0e3034a70
workflow-type: ht
source-wordcount: '934'
ht-degree: 100%

---


# Plug-in Adobe : getAndPersistValue

>[!IMPORTANT]
>
>Ce plug-in est fourni par le service Adobe Consulting afin de vous aider à tirer le meilleur parti d’Adobe Analytics. Le service à la clientèle d’Adobe ne fournit pas d’assistance pour ce plug-in, pas même pour l’installation ou le dépannage. Si vous avez besoin d’aide sur ce plug-in, contactez le gestionnaire de compte de votre organisation. Il peut organiser une réunion avec un consultant pour obtenir de l’aide.

Le plug-in `getAndPersistValue` vous permet de stocker une valeur dans un cookie qui peut être récupérée ultérieurement au cours d’une visite. Il joue un rôle similaire à celui de la fonction [!UICONTROL Durée du stockage] dans Adobe Experience Platform Launch. Adobe conseille d’utiliser ce plug-in si vous souhaitez conserver automatiquement une variable Analytics à la même valeur lors d’accès ultérieurs une fois la variable définie. Ce plug-in n’est pas nécessaire si la fonction [!UICONTROL Durée du stockage] de Launch est suffisante, ou si vous n’avez pas besoin de définir et de conserver des variables à la même valeur lors d’accès ultérieurs. La persistance intégrée des eVars ne nécessite pas l’utilisation de ce plug-in, car ces variables sont conservées côté serveur par Adobe.

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
   * Type d’action : initialisation de getAndPersistValue
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
/* Adobe Consulting Plugin: getAndPersistValue v3.0 (Requires AppMeasurement) */
function getAndPersistValue(vtp,cn,ex){var d=vtp,k=cn,l=ex;if("undefined"!==typeof d&&"-v"===d)return{plugin:"getAndPersistValue",version:"3.0"};var a=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof a&&(a.contextData.getAndPersistValue="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=new Date;k=k?k:"s_gapv";(l=l?l:0)?a.setTime(a.getTime()+864E5*l):a.setTime(a.getTime()+18E5);"undefined"!==typeof d&&d||(d=cookieRead(k));cookieWrite(k,d,a);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilisation du plug-in

La méthode `getAndPersist` utilise les arguments suivants :

* **`vtp`** (obligatoire) : valeur à conserver d’une page à l’autre.
* **`cn`** (facultatif) : nom du cookie permettant de stocker la valeur. Si cet argument n’est pas défini, le cookie est nommé `"s_gapv"`.
* **`ex`** (facultatif) : nombre de jours avant l’expiration du cookie. Si cet argument est défini sur `0` ou n’est pas défini, le cookie expire à la fin de la visite (30 minutes d’inactivité).

Si la variable de l’argument `vtp` est définie, alors le plug-in définit le cookie puis renvoie la valeur du cookie. Si la variable de l’argument `vtp` n’est pas définie, alors le plug-in renvoie uniquement la valeur du cookie.

## Exemples

### Exemple 1

Le code suivant définit eVar21 sur la valeur de « hello ».  Le code définit alors le cookie ev21gapv, qui expirera dans 28 jours, sur la valeur d’eVar21 (c’est-à-dire « hello »).  Le code définit (ou réinitialise) alors eVar21 sur la valeur du cookie ev21gapv.

```js
s.eVar21 = "hello";
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemple 2

Supposons qu’eVar21 n’ait pas encore été défini sur la page active, mais qu’il ait été défini sur « hello » sur une page précédente au cours des 28 derniers jours.   Le code suivant définit uniquement eVar21 sur la valeur du cookie ev21gapv (c’est-à-dire « hello »).  Le cookie ev21gapv n’est pas réinitialisé, car eVar21 n’était pas défini sur la page active avant l’appel de la fonction.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemple 3

Supposons qu’eVar21 n’ait pas encore été défini sur la page active, mais qu’il ait été défini sur « hello » sur une page précédente au cours des 28 derniers jours.  Le code suivant définit uniquement prop35 sur la valeur du cookie ev21gapv (c’est-à-dire « hello »).  Il ne définit pas eVar21.

```js
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemple 4

Le code suivant définit eVar21 sur la valeur de « howdy ».  Le code définit (ou réinitialise) alors le cookie ev21gapv, qui expirera dans 28 jours, sur la valeur d’eVar21 (c’est-à-dire « howdy »).  Le code définit alors prop35 sur la valeur du cookie ev21gapv (c’est-à-dire « howdy »).

```js
s.eVar21 = "howdy";
s.prop35 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemple 5

Supposons que s.eVar21 n’ait été défini sur aucune page au cours des 28 derniers jours.  Le code suivant définit s.eVar21 comme étant nul, car le cookie ev21gapv aurait expiré 28 jours après sa dernière définition.

```js
s.eVar21 = s.getAndPersistValue(s.eVar21,"ev21gapv",28);
```

### Exemple 6

Le code suivant définit eVar30 sur « shopping ».  Il définit alors le cookie s_gapv, qui expire à la fin de la session du navigateur, sur la valeur de s.eVar30 (c’est-à-dire « shopping »).  Il définit ensuite s.eVar30 sur la valeur du cookie s_gapv (autrement dit, l’appel getAndPersistValue renvoie la valeur du cookie s_gapv, qui dans ce cas est « shopping »).

```js
s.eVar30 = "shopping";
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

Si s.eVar30 n’est pas défini sur une valeur explicite sur des pages supplémentaires affichées pendant la session, mais est défini (dans doPlugins) via le code suivant…

```js
s.eVar30 = s.getAndPersistValue(s.eVar30);
```

…alors s.eVar30 sera défini sur « shopping » (soit la valeur persistante du cookie s_gapv).

## Historique des versions

### 3.0 (19 mars 2021)

* Ajout du numéro de version comme donnée contextuelle.

### 2.0 (16 avril 2018)

* Nouvelle version (taille de code réduite).
* La transmission de 0 dans l’argument `ex` force désormais l’expiration après 30 minutes d’inactivité plutôt que l’expiration à la fin de la session du navigateur.

### 1.0 (18 janvier 2016)

* Version initiale.
