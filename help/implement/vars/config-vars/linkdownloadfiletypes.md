---
title: linkDownloadFileTypes
description: Permet de déterminer les extensions de fichier qui sont automatiquement suivies comme liens de téléchargement.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkDownloadFileTypes

Lorsque [`trackDownloadLinks`](trackdownloadlinks.md) est activé et qu’un visiteur clique sur un lien, AppMeasurement vérifie que l’URL du lien contient des extensions de type de fichier. Si l’URL du lien contient un type de fichier trouvé dans `linkDownloadFileTypes`, une demande d’image de lien de téléchargement est automatiquement envoyée.

Utilisez `linkDownloadFileTypes` pour personnaliser les extensions de fichier que vous souhaitez compter comme liens de téléchargement.

>[!NOTE] Seuls les clics réels sont automatiquement suivis. Les types de liens suivants ne sont pas automatiquement suivis :
>
> * Téléchargements de fichiers qui démarrent automatiquement lors du chargement d’une page
> * Téléchargements déclenchés à la suite d’une redirection
> * Clic droit et sélection de l’option « Enregistrer la cible sous... »
> * Liens utilisant JavaScript, tels que `javascript:openLink()`
>
> 
Pour ces types de téléchargement, vous pouvez appeler manuellement la méthode [`tl()`](../functions/tl-method.md).

Si un lien cliqué correspond à la fois aux critères de lien de sortie et de lien de téléchargement, le type de lien de téléchargement est prioritaire.

## Extensions de téléchargement dans Adobe Experience Platform Launch

Les extensions de téléchargement désignent une liste d’extensions de fichier avec un champ à ajouter sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche le champ [!UICONTROL Télécharger les extensions].

Ajoutez des extensions de fichier à la liste en saisissant du texte dans le champ et en cliquant sur [!UICONTROL Ajouter]. Supprimez les extensions de fichier de la liste en cliquant sur leur icône « X » respective.

## s.linkDownloadFileTypes dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.linkDownloadFileTypes` est une chaîne d’extensions de fichiers séparées par des virgules. N’utilisez pas d’espaces.

Si cette variable n’est pas définie, le suivi automatique des liens de téléchargement ne fonctionne pas (même si [`trackDownloadLinks`](trackdownloadlinks.md) correspond à `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
