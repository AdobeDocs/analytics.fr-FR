---
title: linkDownloadFileTypes
description: Déterminez les extensions de fichier qui sont automatiquement suivies en tant que liens de téléchargement.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkDownloadFileTypes

Lorsqu’ [`trackDownloadLinks`](trackdownloadlinks.md) est activé et qu’un clique sur un lien, AppMeasurement vérifie que l’URL du lien contient des extensions de type de fichier. Si l’URL du lien contient un type de fichier trouvé dans `linkDownloadFileTypes`, une demande d’image de lien de téléchargement est automatiquement envoyée.

Utilisez `linkDownloadFileTypes` pour personnaliser les extensions de fichier que vous souhaitez compter comme liens de téléchargement.

> [!NOTE] Seuls les clics réels sont automatiquement suivis. Les types de liens suivants ne sont pas automatiquement suivis :
>
> * Téléchargements de fichiers qui  automatiquement au chargement d’une page
> * Téléchargements qui se déclenchent après une redirection
> * Cliquez avec le bouton droit de la souris et sélectionnez &quot;Enregistrer  sous...&quot;.
> * Liens qui utilisent JavaScript, tels que `javascript:openLink()`
>
> 
Pour ces types de téléchargement, vous pouvez appeler manuellement la [`tl()`](../functions/tl-method.md) méthode.

Si un lien cliqué correspond à la fois aux critères de lien de sortie et de lien de téléchargement, le type de lien de téléchargement est prioritaire.

## Téléchargement d’extensions dans Adobe Experience Platform Launch

Download Extensions est un d’extensions de fichier avec un champ à ajouter sous l’ [!UICONTROL Link Tracking] accordéon lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants AdobeID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’ [!UICONTROL Extensions] onglet, puis cliquez sur le [!UICONTROL Configure] bouton sous Adobe Analytics.
4. Développez l’ [!UICONTROL Link Tracking] accordéon, ce qui révèle le [!UICONTROL Download Extensions] champ.

Ajouter des extensions de fichier au  en saisissant du texte dans le champ et en cliquant sur [!UICONTROL Add]. Supprimez les extensions de fichier du  en cliquant sur l’icône &quot;X&quot; correspondante.

## s.linkDownloadFileTypes dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.linkDownloadFileTypes` variable est une chaîne d’extensions de fichiers séparées par des virgules. N’utilisez pas d’espaces.

Si cette variable n’est pas définie, le suivi automatique des liens de téléchargement ne fonctionne pas (même s’il [`trackDownloadLinks`](trackdownloadlinks.md) l’est `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
