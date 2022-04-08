---
title: useLinkTrackSessionStorage
description: Stockez les données de suivi des liens dans l’enregistrement de session plutôt que dans un cookie.
feature: Variables
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '264'
ht-degree: 100%

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

## Utilisation de l’enregistrement de session de suivi de lien à l’aide de balises dans Adobe Experience Platform

Il n’existe pas de champ dédié dans l’interface utilisateur de la collecte de données pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.useLinkTrackSessionStorage dans AppMeasurement et l’éditeur de code personnalisé 

La variable `s.useLinkTrackSessionStorage` est une valeur booléenne qui détermine si AppMeasurement utilise l’enregistrement de session pour les données de suivi des liens au lieu du cookie `s_sq`. Sa valeur par défaut est `false`. Définissez cette variable sur `true` si vous souhaitez qu’AppMeasurement utilise l’enregistrement de session au lieu du cookie `s_sq` pour le suivi des liens et Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
