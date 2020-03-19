---
title: Présentation de la mise en œuvre JavaScript du code H
description: Découvrez le flux de travail pour mettre en œuvre le code H sur votre site.
translation-type: ht
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# Présentation de la mise en œuvre JavaScript du code H

> [!IMPORTANT] Cette version de la collecte de données n’est plus prise en charge. Effectuez la mise à niveau vers [Adobe Experience Platform Launch](../../launch/overview.md) ou [AppMeasurement pour JavaScript](../overview.md).

Vous devez avoir accès à vos serveurs d’hébergement pour mettre en œuvre correctement une page avec du code pour collecter des données. Les étapes suivantes vous invitent à parcourir une mise en œuvre de base du code H d’Analytics.

> [!NOTE] Vous devez déjà disposer d’une copie existante de `s_code.js` pour suivre ces instructions. Adobe ne propose plus d’option pour télécharger le code H dans le Gestionnaire de code.

1. **Mettez à jour les variables de fichier JS principal** : modifiez le fichier `s_code.js` et assurez-vous que les variables suivantes sont mises à jour :
   * `s_account` contient l’identifiant de suite de rapports auquel vous souhaitez envoyer des données. Voir
   * `s.trackingServer` contient l’emplacement où les cookies sont stockés. Voir [trackingServer](../../vars/config-vars/trackingserver.md).
2. **Hébergez le fichier`s_code.js`sur votre site** : ce fichier réside généralement avec d’autres scripts sur votre serveur web.
3. **Référence`s_code.js`sur toutes les pages** : assurez-vous que toutes les pages individuelles appellent le fichier JavaScript principal, et faites-le dans la balise HTML `<body>` (et non dans la balise `<head>`).
   > [!TIP] Le code H exige que le script `s_code.js` soit appelé dans la balise `<body>`. Il s’agit d’une méthode différente des autres méthodes de mise en œuvre, dont la plupart nécessitent des références de script dans la balise `<head>`.
4. **Définissez des variables spécifiques à chaque page** : des variables individuelles doivent être définies pour chaque page, telles que le nom de page ou les eVars. Les variables individuelles sont généralement définies avec une balise `<script>` intégrée sur chaque page.
5. **Utilisez le débogueur pour vérifier la collecte des données** : téléchargez et installez le [débogueur Experience Cloud](../../validate/debugger.md) pour vous assurer que les données sont envoyées à Adobe et que les variables de page sont correctement définies.

## Mise en cache

Le fichier JavaScript est mis en cache dans le navigateur du visiteur après son chargement initial. En règle générale, il n’est pas téléchargé plus d’une fois par session. Il n’est pas téléchargé sur chaque page, même s’il est utilisé par toutes les pages du site. Sur la plupart des sites Web, les utilisateurs visualisent, en moyenne, plus de quelques pages par session. Dès lors, le transfert de code JavaScript utilisé plusieurs fois dans ce fichier peut générer un nombre moins important de données téléchargées globales.

## Compression du code H

Si la taille du téléchargement du fichier `s_code.js` vous préoccupe, Adobe conseille de compresser le fichier `s_code.js` à l’aide de GZIP. GZIP est pris en charge par tous les principaux navigateurs et offre de meilleures performances que la compression JavaScript. Voir [Module Apache mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html) dans la documentation Apache.
