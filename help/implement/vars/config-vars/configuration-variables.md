---
title: Variables de configuration
description: Utilisez les variables de configuration pour déterminer le mode de collecte des données.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Présentation des variables de configuration

Les variables de configuration contrôlent le mode de collecte et de traitement des données dans les rapports. Elles ne contiennent généralement pas de valeurs de dimension ou de mesure.

## Définition des variables de configuration

Dans les implémentations JavaScript utilisant `AppMeasurement.js`, les variables de configuration sont généralement définies en haut du fichier JS.

Dans les implémentations à l’aide d’Adobe Experience Platform Launch, les variables de configuration sont généralement trouvées en configurant l’extension Adobe Analytics :

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété à modifier.
3. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

> [!IMPORTANT] Assurez-vous que toutes les variables de configuration sont définies avant d’appeler une méthode de suivi ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)). Evitez de définir des variables de configuration dans la [`doPlugins()`](../functions/doplugins.md) fonction.
