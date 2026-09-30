---
description: Vous devez répondre à ces exigences de solution, de service et de code CX Enterprise pour implémenter le transfert côté serveur. Ces conditions requises incluent également des instructions sur la façon de vérifier les versions du code et d’obtenir les dernières bibliothèques de code.
solution: Analytics
title: Conditions requises pour le transfert côté serveur
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
TQID: 'https://experienceleague.adobe.com/1GCflxlY4IpT-pPTr93FuOmxkJLC4baJe3Z2SGjj1So'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
    internal-label: Server side forwarding
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 84%
---
# Conditions requises pour le transfert côté serveur

Vous devez répondre à ces exigences de solution, de service et de code CX Enterprise pour implémenter le transfert côté serveur. Ces conditions requises incluent également des instructions sur la façon de vérifier les versions du code et d’obtenir les dernières bibliothèques de code.

## Conditions requises de la solution

Le transfert côté serveur fonctionne avec [Analytics](https://www.adobe.com/fr/analytics/adobe-analytics.html) et [Audience Manager](https://www.adobe.com/fr/analytics/audience-manager.html) et/ou [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr).

## Conditions requises du service

Le transfert côté serveur nécessite le [service d’identité](https://experienceleague.adobe.com/fr/docs/id-service/using/home). Identity Service fournit un identifiant universel qui identifie les visiteurs du site dans toutes les solutions de CX Enterprise. Vous devez mettre en œuvre le service d’identités pour que le transfert côté serveur fonctionne.

## Versions du code

Le transfert côté serveur requiert la version 1.5 (ou plus récente) des bibliothèques de code répertoriées ci-dessous. Pour respecter les bonnes pratiques, il est recommandé d’utiliser les dernières versions plutôt que les minimums requis.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Déterminer la version de votre bibliothèque de code

Tout outil qui surveille les requêtes HTTP émises par un navigateur peut afficher le numéro de version de votre code AppMeasurement et d’API Visiteur. La bibliothèque `AppMeasurement_Module_AudienceManagement.js` ne contient ni ne renvoie un ID de version. Les exemples suivants montrent à quoi ressemblent les ID de version pour les codes `AppMeasurement.js` et `VisitorAPI.js`.

* `AppMeasurement.js` : l’[outil de débogage Adobe](/help/implement/validate/debugger.md) renvoie la version d’AppMeasurement de la façon suivante : `Version of Code | JS-1.5.1`. D’autres outils peuvent utiliser un libellé différent, mais la valeur suit toujours le modèle `JS-X.X.X`, où `X` est un numéro de version.
* `VisitorAPI.js` : recherchez le paramètre `d_visid_ver`. Il vous montrera le service d’ID de visiteur comme ceci : `d_visid_ver: 1.5.5`. Le code VisitorAPI antérieur à la version 1.5.2 n’incluait pas de numéro de version. Vous utilisez probablement une bibliothèque de code plus ancienne (et devez la mettre à niveau) si les résultats de la surveillance ne renvoient pas de numéro de version.
