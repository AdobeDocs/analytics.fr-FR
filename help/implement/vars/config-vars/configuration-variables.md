---
title: Variables de configuration
description: Utilisez les variables de configuration pour déterminer le mode de collecte des données.
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '123'
ht-degree: 100%

---

# Présentation des variables de configuration

Les variables de configuration contrôlent le mode de collecte et de traitement des données dans les rapports. Elles ne contiennent généralement pas de valeurs de dimension ou de mesure.

## Définition des variables de configuration

Dans les mises en œuvre JavaScript utilisant `AppMeasurement.js` ; les variables de configuration sont généralement définies en haut du fichier JS.

Dans les mises en œuvre à l’aide d’Adobe Experience Platform Launch, les variables de configuration sont généralement trouvées en configurant l’extension Adobe Analytics :

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété à modifier.
3. Cliquez sur l’onglet [!UICONTROL Extensions], puis sur [!UICONTROL Configurer] sous Adobe Analytics.

>[!IMPORTANT]
>
>Assurez-vous que toutes les variables de configuration sont définies avant d’appeler une méthode de suivi ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)). Évitez de définir des variables de configuration dans la fonction [`doPlugins()`](../functions/doplugins.md).
