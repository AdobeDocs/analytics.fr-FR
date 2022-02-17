---
title: Variables de configuration
description: Utilisez les variables de configuration pour déterminer le mode de collecte des données.
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 100%

---

# Présentation des variables de configuration

Les variables de configuration contrôlent le mode de collecte et de traitement des données dans les rapports. Elles ne contiennent généralement pas de valeurs de dimension ou de mesure.

## Définition des variables de configuration

Dans les mises en œuvre JavaScript utilisant `AppMeasurement.js` ; les variables de configuration sont généralement définies en haut du fichier JS.

Dans les implémentations à l’aide de balises Adobe Experience Platform, les variables de configuration sont généralement trouvées en configurant l’extension Adobe Analytics :

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété que vous souhaitez modifier.
1. Cliquez sur l’onglet [!UICONTROL Extensions], puis sur [!UICONTROL Configurer] sous Adobe Analytics.

>[!IMPORTANT]
>
>Assurez-vous que toutes les variables de configuration sont définies avant d’appeler une méthode de suivi ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)). Évitez de définir des variables de configuration dans la fonction [`doPlugins()`](../functions/doplugins.md).
