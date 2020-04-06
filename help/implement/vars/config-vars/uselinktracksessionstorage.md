---
title: useLinkTrackSessionStorage
description: Stocker les données de suivi des liens dans la session  le  au lieu d’un cookie.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# useLinkTrackSessionStorage

Si votre entreprise utilise le suivi des liens, AppMeasurement utilise le `s_sq` cookie pour transmettre des informations entre les accès. Certaines configurations de site Web entrent en conflit avec ce cookie. Si vous souhaitez utiliser la session de navigateur  le  pour le suivi des liens et les données de Carte de  de la  au lieu d’un cookie, activez cette variable.

L’utilisation d’un de session de navigateur  pour le suivi des liens présente plusieurs restrictions :

* Le de  de session ne fonctionne pas entre les protocoles. Par exemple, vous disposez d’une page diffusée sur HTTP et de la page suivante diffusée sur HTTPS. AppMeasurement ne peut pas accéder aux données de suivi des liens dans la session   en raison des différences de protocole.
* Le de  de session ne fonctionne pas sur les sous-domaines. Par exemple, un accède à `store.example.com`, puis accède à `toys.example.com`. AppMeasurement ne peut pas accéder aux données de suivi des liens dans  session  en raison de différents sous-domaines.

>[!TIP] L’implémentation la plus fiable à l’aide de l’ de session  pour le suivi des liens diffuse tout le contenu via HTTPS sur un seul sous-domaine.

AppMeasurement supprime les données de suivi des liens de la session  de l’ après l’envoi d’un accès à Adobe. Elle expire également automatiquement lorsque l’onglet du navigateur est fermé.

## Utiliser la session de suivi des liens   dans le lancement d’Adobe Experience Platform

Il n’existe pas de champ dédié dans Launch pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.useLinkTrackSessionStorage dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.useLinkTrackSessionStorage` variable est une valeur booléenne qui détermine si AppMeasurement utilise  session  pour les données de suivi des liens au lieu du `s_sq` cookie. Sa valeur par défaut est `false`. Définissez cette variable sur `true` si vous souhaitez qu’AppMeasurement utilise le  de session   au lieu du `s_sq` cookie pour le suivi des liens et la carte de .

```js
s.useLinkTrackSessionStorage = true;
```
