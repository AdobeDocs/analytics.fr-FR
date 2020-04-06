---
title: linkDownloadFileTypes
description: Permet de déterminer les extensions de fichier qui sont automatiquement suivies comme liens de téléchargement.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkDownloadFileTypes

When [`trackDownloadLinks`](trackdownloadlinks.md) is enabled and a visitor clicks on a link, AppMeasurement checks the URL of the link for filetype extensions. Si l’URL du lien contient un type de fichier trouvé dans `linkDownloadFileTypes`, une demande d’image de lien de téléchargement est automatiquement envoyée.

Utilisez `linkDownloadFileTypes` pour personnaliser les extensions de fichier que vous souhaitez compter comme liens de téléchargement.

>[!NOTE] Seuls les clics réels sont automatiquement suivis. Les types de liens suivants ne sont pas automatiquement suivis :
>
> * Téléchargements de fichiers qui démarrent automatiquement lors du chargement d’une page
> * Téléchargements déclenchés à la suite d’une redirection
> * Clic droit et sélection de l’option « Enregistrer la cible sous... »
> * Liens utilisant JavaScript, tels que `javascript:openLink()`
>
> 
For these download types, you can manually call the [`tl()`](../functions/tl-method.md) method.

Si un lien cliqué correspond à la fois aux critères de lien de sortie et de lien de téléchargement, le type de lien de téléchargement est prioritaire.

## Extensions de téléchargement dans Adobe Experience Platform Launch

Download Extensions is a list of file extensions with a field to add more under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Développez l’ [!UICONTROL Link Tracking] accordéon, ce qui révèle le [!UICONTROL Download Extensions] champ.

Add file extensions to the list by entering text in the field and clicking [!UICONTROL Add]. Supprimez les extensions de fichier du  en cliquant sur l’icône &quot;X&quot; correspondante.

## s.linkDownloadFileTypes dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.linkDownloadFileTypes` est une chaîne d’extensions de fichiers séparées par des virgules. N’utilisez pas d’espaces.

Si cette variable n’est pas définie, le suivi automatique des liens de téléchargement ne fonctionne pas (même si [`trackDownloadLinks`](trackdownloadlinks.md) correspond à `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
