---
title: useLinkTrackSessionStorage
description: Stockez les données de suivi des liens dans l’enregistrement de session plutôt que dans un cookie.
feature: Appmeasurement Implementation
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/JQc7Ii-LrL8k0KIttWFuowJCASGK2e75exSbjhG347s'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 283
ht-degree: 86%

---

# useLinkTrackSessionStorage

Si votre organisation utilise le suivi des liens, AppMeasurement utilise le cookie `s_sq` pour transmettre des informations entre accès. Certaines configurations de site Web entrent en conflit avec ce cookie. Si vous souhaitez utiliser l’enregistrement de session du navigateur pour le suivi des liens et les données Activity Map au lieu d’un cookie, activez cette variable.

L’utilisation de l’enregistrement de session d’un navigateur pour le suivi des liens présente plusieurs limitations :

* L’enregistrement de session ne fonctionne pas entre protocoles. Par exemple, une page est diffusée sur HTTP et la page suivante sur HTTPS. AppMeasurement ne peut pas accéder aux données de suivi des liens dans l’enregistrement de session car les protocoles sont différents.
* L’enregistrement de session ne fonctionne pas entre plusieurs sous-domaines. Par exemple, un visiteur accède à `store.example.com`, puis à `toys.example.com`. AppMeasurement ne peut pas accéder aux données de suivi des liens dans l’enregistrement de session car les sous-domaines sont différents.

>[!TIP]
>
>L’implémentation la plus fiable utilisant l’enregistrement de session pour le suivi des liens diffuse tout le contenu via HTTPS sur un seul sous-domaine.

AppMeasurement supprime les données de suivi des liens d’enregistrement de session après l’envoi d’un accès à Adobe. Il expire également automatiquement lorsque l’onglet du navigateur est fermé.

## Utiliser le stockage de session de suivi des liens à l’aide de Web SDK

Web SDK ne prend pas en charge cette fonctionnalité.

## Utiliser le stockage de session de suivi des liens à l’aide de l’extension Adobe Analytics

Il n’existe pas de champ dédié dans l’extension Adobe Analytics pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.useLinkTrackSessionStorage dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.useLinkTrackSessionStorage` est une valeur booléenne qui détermine si AppMeasurement utilise l’enregistrement de session pour les données de suivi des liens au lieu du cookie `s_sq`. Sa valeur par défaut est `false`. Définissez cette variable sur `true` si vous souhaitez qu’AppMeasurement utilise l’enregistrement de session au lieu du cookie `s_sq` pour le suivi des liens et Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
