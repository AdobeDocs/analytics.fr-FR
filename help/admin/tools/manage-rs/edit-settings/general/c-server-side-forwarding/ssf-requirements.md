---
description: Vous devez respecter les conditions requises de la solution, du service et du code Experience Cloud pour implémenter le transfert côté serveur. Ces conditions requises incluent également des instructions sur la façon de vérifier les versions du code et d’obtenir les dernières bibliothèques de codes.
solution: Analytics
title: Conditions requises pour le transfert côté serveur
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 100%

---

# Conditions requises pour le transfert côté serveur

Vous devez respecter les conditions requises de la solution, du service et du code Experience Cloud pour implémenter le transfert côté serveur. Ces conditions requises incluent également des instructions sur la façon de vérifier les versions du code et d’obtenir les dernières bibliothèques de codes.

## Conditions requises de la solution

Le transfert côté serveur fonctionne avec [Analytics](https://www.adobe.com/fr/analytics/adobe-analytics.html) et [Audience Manager](https://www.adobe.com/fr/analytics/audience-manager.html) et/ou [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr).

## Conditions requises du service

Le transfert côté serveur nécessite le [service d’identité](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr). Le service d’identité fournit un identifiant universel qui identifie les visiteurs du site à l’échelle de toutes les solutions Experience Cloud. Vous devez implémenter le service d’identification pour que le transfert côté serveur fonctionne.

## Versions du code

Le transfert côté serveur requiert la version 1.5 (ou plus récente) des bibliothèques de codes répertoriées ci-dessous. Pour respecter les bonnes pratiques, il est recommandé d’utiliser les dernières versions plutôt que les minimums requis.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Déterminer la version de votre bibliothèque de codes

Tout outil qui surveille les requêtes HTTP émises par un navigateur peut afficher le numéro de version de votre code AppMeasurement et VisitorAPI. La bibliothèque `AppMeasurement_Module_AudienceManagement.js` ne contient ni ne renvoie un ID de version. Les exemples suivants montrent à quoi ressemblent les ID de version pour les codes `AppMeasurement.js` et `VisitorAPI.js`.

* `AppMeasurement.js` : l’[outil de débogage Adobe](/help/implement/validate/debugger.md) renvoie la version d’AppMeasurement de la façon suivante : `Version of Code | JS-1.5.1`. D’autres outils peuvent utiliser un libellé différent, mais la valeur suit toujours le modèle `JS-X.X.X`, où `X` est un numéro de version.
* `VisitorAPI.js` : recherchez le paramètre `d_visid_ver`. Il vous montrera le service d’ID de visiteur comme ceci : `d_visid_ver: 1.5.5`. Le code VisitorAPI antérieur à la version 1.5.2 n’incluait pas de numéro de version. Vous utilisez probablement une bibliothèque de codes plus ancienne (et devez mettre à niveau) si les résultats de la surveillance ne renvoient pas de numéro de version.
