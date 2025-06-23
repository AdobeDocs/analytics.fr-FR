---
title: linkDownloadFileTypes
description: Permet de déterminer les extensions de fichier qui sont automatiquement suivies comme liens de téléchargement.
feature: Appmeasurement Implementation
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 55%

---

# linkDownloadFileTypes

Lorsque [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement) ou [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) est activé et qu’un visiteur clique sur un lien, AppMeasurement recherche des extensions de type fichier dans l’URL du lien. Si l’URL du lien contient un type de fichier correspondant, une demande d’image de lien de téléchargement est automatiquement envoyée.

Utilisez `linkDownloadFileTypes` pour personnaliser les extensions de fichier que vous souhaitez compter comme liens de téléchargement.

>[!NOTE]
>
>Seuls les clics réels sont automatiquement suivis. Les types de liens suivants ne sont pas automatiquement suivis :
>
>* Téléchargements de fichiers qui démarrent automatiquement lors du chargement d’une page
>* Téléchargements déclenchés à la suite d’une redirection
>* Clic droit et sélection de l’option « Enregistrer la cible sous... »
>* Liens utilisant JavaScript, tels que `javascript:openLink()`
>
>Pour ces types de téléchargement, vous pouvez envoyer manuellement un appel [`link tracking`](../functions/tl-method.md).

Si un lien cliqué correspond à la fois aux critères de lien de sortie et de lien de téléchargement, le type de lien de téléchargement est prioritaire.

## Télécharger le qualificateur de lien à l’aide de l’extension Web SDK

Le champ de texte [!UICONTROL Qualificateur du lien de téléchargement] utilise une expression régulière pour déterminer si un lien cliqué est qualifié pour être un lien de téléchargement.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous [!UICONTROL Adobe Experience Platform Web SDK].
1. Sous [!UICONTROL Collecte de données], définissez la valeur souhaitée dans le champ de texte **[!UICONTROL Qualificateur de lien de téléchargement]**.

## Télécharger le qualificateur de lien implémentant manuellement le Web SDK

[Configurer](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr) le SDK à l’aide de [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=fr#automaticLinkTracking). Le champ utilise une expression regex sur l’URL sur laquelle l’utilisateur a cliqué pour déterminer s’il s’agit d’un lien de téléchargement valide. Si `downloadLinkQualifier` n’est pas défini, la valeur par défaut est définie sur `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## Téléchargement d’extensions à l’aide de l’extension Adobe Analytics

Les extensions de téléchargement désignent une liste d’extensions de fichier avec un champ à ajouter sous l’accordéon [!UICONTROL Suivi des liens] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Suivi des liens], qui affiche le champ **[!UICONTROL Télécharger les extensions]**.

Ajoutez des extensions de fichier à la liste en saisissant du texte dans le champ et en cliquant sur **[!UICONTROL Ajouter]**. Supprimez des extensions de fichier de la liste en cliquant sur l’icône **leur** respectif.

## s.linkDownloadFileTypes dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.linkDownloadFileTypes` est une chaîne d’extensions de fichiers séparées par des virgules. N’utilisez pas d’espaces.

Si cette variable n’est pas définie, le suivi automatique des liens de téléchargement ne fonctionne pas (même si [`trackDownloadLinks`](trackdownloadlinks.md) correspond à `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
