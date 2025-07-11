---
title: Variables de configuration
description: Utilisez les variables de configuration pour déterminer le mode de collecte des données.
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 65%

---

# Présentation des variables de configuration

Les variables de configuration contrôlent le mode de collecte et de traitement des données dans les rapports. Elles ne contiennent généralement pas de valeurs de dimension ou de mesure.

## Définition des variables de configuration

Dans les implémentations utilisant l’extension Web SDK ou l’extension Analytics, les variables de configuration se trouvent généralement dans les paramètres de l’extension :

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur la propriété de balise de votre choix.
1. Cliquez sur l’onglet [!UICONTROL Extensions], puis sur [!UICONTROL Configurer] sous l’extension.

Dans les mises en œuvre JavaScript utilisant `AppMeasurement.js` ; les variables de configuration sont généralement définies en haut du fichier JS.

>[!IMPORTANT]
>
>Assurez-vous que toutes les variables de configuration sont définies avant d’appeler une méthode de suivi ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)). Évitez de définir des variables de configuration dans la fonction [`doPlugins()`](../functions/doplugins.md).
