---
description: Vous devez répondre à ces exigences de solution, de service et de code CX Enterprise pour implémenter le transfert côté serveur. Ces conditions requises incluent également des instructions sur la façon de vérifier les versions du code et d’obtenir les dernières bibliothèques de codes.
solution: Analytics
title: Conditions requises pour le transfert côté serveur
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
TQID: 'https://experienceleague.adobe.com/1GCflxlY4IpT-pPTr93FuOmxkJLC4baJe3Z2SGjj1So'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 325
ht-degree: 84%

---

# Conditions requises pour le transfert côté serveur

Vous devez répondre à ces exigences de solution, de service et de code CX Enterprise pour implémenter le transfert côté serveur. Ces conditions requises incluent également des instructions sur la façon de vérifier les versions du code et d’obtenir les dernières bibliothèques de codes.

## Conditions requises de la solution

Le transfert côté serveur fonctionne avec [Analytics](https://www.adobe.com/fr/analytics/adobe-analytics.html) et [Audience Manager](https://www.adobe.com/fr/analytics/audience-manager.html) et/ou [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr).

## Conditions requises du service

Le transfert côté serveur nécessite le [service d’identité](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr). Identity Service fournit un identifiant universel qui identifie les visiteurs du site dans toutes les solutions d’entreprise CX. Vous devez implémenter le service d’identification pour que le transfert côté serveur fonctionne.

## Versions du code

Le transfert côté serveur requiert la version 1.5 (ou plus récente) des bibliothèques de codes répertoriées ci-dessous. Pour respecter les bonnes pratiques, il est recommandé d’utiliser les dernières versions plutôt que les minimums requis.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Déterminer la version de votre bibliothèque de codes

Tout outil qui surveille les requêtes HTTP émises par un navigateur peut afficher le numéro de version de votre code AppMeasurement et VisitorAPI. La bibliothèque `AppMeasurement_Module_AudienceManagement.js` ne contient ni ne renvoie un ID de version. Les exemples suivants montrent à quoi ressemblent les ID de version pour les codes `AppMeasurement.js` et `VisitorAPI.js`.

* `AppMeasurement.js` : l’[outil de débogage Adobe](/help/implement/validate/debugger.md) renvoie la version d’AppMeasurement de la façon suivante : `Version of Code | JS-1.5.1`. D’autres outils peuvent utiliser un libellé différent, mais la valeur suit toujours le modèle `JS-X.X.X`, où `X` est un numéro de version.
* `VisitorAPI.js` : recherchez le paramètre `d_visid_ver`. Il vous montrera le service d’ID de visiteur comme ceci : `d_visid_ver: 1.5.5`. Le code VisitorAPI antérieur à la version 1.5.2 n’incluait pas de numéro de version. Vous utilisez probablement une bibliothèque de codes plus ancienne (et devez mettre à niveau) si les résultats de la surveillance ne renvoient pas de numéro de version.
