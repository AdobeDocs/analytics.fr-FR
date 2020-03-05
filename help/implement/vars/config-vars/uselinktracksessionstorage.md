---
title: useLinkTrackSessionStorage
description: Stockez les données de suivi des liens dans le stockage de la session au lieu d’un cookie.
translation-type: tm+mt
source-git-commit: 1b8de7489be8461707307dfe99d86f46557c7b8b

---


# useLinkTrackSessionStorage

Si votre entreprise utilise le suivi des liens, AppMeasurement utilise le `s_sq` cookie pour transmettre des informations entre les accès. Certaines configurations de site Web entrent en conflit avec ce cookie. Si vous souhaitez utiliser le stockage de session du navigateur pour le suivi des liens et les données de Carte d’activités au lieu d’un cookie, activez cette variable.

L’utilisation du stockage de session d’un navigateur pour le suivi des liens présente plusieurs restrictions :

* Le stockage de session ne fonctionne pas entre les protocoles. Par exemple, vous disposez d’une page diffusée sur HTTP et de la page suivante diffusée sur HTTPS. AppMeasurement ne peut pas accéder aux données de suivi des liens dans le stockage de session en raison de différences de protocole.
* Le stockage de session ne fonctionne pas sur plusieurs sous-domaines. Par exemple, un visiteur navigue vers `store.example.com`, puis `toys.example.com`. AppMeasurement ne peut pas accéder aux données de suivi des liens dans le stockage de session en raison de différents sous-domaines.

> [!TIP] L’implémentation la plus fiable à l’aide du stockage de session pour le suivi des liens diffuse tout le contenu via HTTPS sur un seul sous-domaine.

AppMeasurement supprime les données de suivi des liens de stockage de session après l’envoi d’un accès à Adobe. Elle expire également automatiquement lorsque l’onglet du navigateur est fermé.

## Utiliser le stockage de session de suivi des liens dans Adobe Experience Platform Launch

Il n’existe pas de champ dédié dans Lancer pour utiliser cette variable. Utilisez l’éditeur de code personnalisé, en respectant la syntaxe AppMeasurement.

## s.useLinkTrackSessionStorage dans AppMeasurement et lancement de l’éditeur de code personnalisé

La `s.useLinkTrackSessionStorage` variable est une valeur booléenne qui détermine si AppMeasurement utilise le stockage de session pour les données de suivi des liens au lieu du `s_sq` cookie. Its default value is `false`. Définissez cette variable sur `true` si vous souhaitez qu’AppMeasurement utilise le stockage de session au lieu du `s_sq` cookie pour le suivi des liens et Carte d’activités.

```js
s.useLinkTrackSessionStorage = true;
```
