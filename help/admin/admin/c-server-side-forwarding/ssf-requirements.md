---
description: Vous devez respecter les conditions requises de la solution, du service et du code Experience Cloud pour implémenter le transfert côté serveur. Ces conditions requises incluent également des instructions sur la façon de vérifier les versions du code et d’obtenir les dernières bibliothèques de codes.
seo-description: Vous devez respecter les conditions requises de la solution, du service et du code Experience Cloud pour implémenter le transfert côté serveur. Ces conditions requises incluent également des instructions sur la façon de vérifier les versions du code et d’obtenir les dernières bibliothèques de codes.
seo-title: Conditions requises pour le transfert côté serveur
solution: Audience Manager
title: Conditions requises pour le transfert côté serveur
uuid: e52c9292-b2ed-4782-9594-c813e4f894e1
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# Conditions requises pour le transfert côté serveur

Vous devez respecter les conditions requises de la solution, du service et du code Experience Cloud pour implémenter le transfert côté serveur. Ces conditions requises incluent également des instructions sur la façon de vérifier les versions du code et d’obtenir les dernières bibliothèques de codes.

## Conditions requises de la solution

Le transfert côté serveur fonctionne avec [Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html) et [Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) et/ou [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html).

## Conditions requises du service

Le transfert côté serveur nécessite le service [d’identité](https://marketing.adobe.com/resources/help/en_US/mcvid/). Le service Identity Service fournit un ID universel qui identifie les visiteurs du site dans toutes les solutions d’Experience Cloud. Vous devez implémenter le service d’identification pour que le transfert côté serveur fonctionne.

## Versions du code

Le transfert côté serveur requiert la version 1.5 (ou plus récente) des bibliothèques de codes répertoriées ci-dessous. Pour respecter les bonnes pratiques, il est recommandé d’utiliser les dernières versions plutôt que les minimums requis.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Déterminer la version de votre bibliothèque de codes

Tout outil qui surveille les requêtes HTTP émises par un navigateur peut afficher le numéro de version de votre code AppMeasurement et VisitorAPI. The `AppMeasurement_Module_AudienceManagement.js` does not contain or return a version ID. Les exemples suivants montrent à quoi ressemblent les ID de version pour les codes `AppMeasurement.js` et `VisitorAPI.js`.

* `AppMeasurement.js`: Le débogueur [Adobe](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html) renvoie la version AppMeasurement comme suit : `Version of Code | JS-1.5.1`. D’autres outils peuvent utiliser un libellé différent, mais la valeur suit toujours le modèle `JS-X.X.X`, où `X` est un numéro de version.
* `VisitorAPI.js`: Recherchez le `d_visid_ver` paramètre. It will show you the Visitor ID service like this: `d_visid_ver: 1.5.5`. Le code VisitorAPI antérieur à la version 1.5.2 n’incluait pas de numéro de version. Vous utilisez probablement une bibliothèque de codes plus ancienne (et devez mettre à niveau) si les résultats de la surveillance ne renvoient pas de numéro de version.
