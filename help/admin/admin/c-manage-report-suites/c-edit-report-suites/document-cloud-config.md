---
description: Vous pouvez afficher les données de Document Cloud dans Adobe Analytics
title: Configuration des rapports de Document Cloud
feature: Admin Tools
source-git-commit: 01aa0959a7ddd8d5a29c838bdbc771435784c9e6
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 1%

---


# Configuration des rapports de Document Cloud

Vous pouvez configurer des dimensions et des mesures spécifiques au PDF pour qu’elles soient disponibles dans Adobe Analytics.

## Composants ajoutés lors de l’activation de la création de rapports de PDF

Lorsque les rapports PDF sont correctement configurés, les dimensions et mesures suivantes sont disponibles dans Adobe Analytics :

**Dimensions :**

* Terme de recherche du PDF

* Niveau de zoom du PDF

* Action du PDF

* Numéro de page du PDF

* Nom de fichier du PDF

**Mesures :**

* Vues PDF

* Pages vues du PDF

* Téléchargements de PDF

* Recherche de PDF

* Signets de PDF utilisés

* PDF Copy Text

* PDF Print

## Activation de la création de rapports de PDF dans Adobe Analytics

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Administration]** > **[!UICONTROL Suites de rapports]** > **`<select report suite>`** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Gestion des Documents Cloud]** > [!UICONTROL **Rapports sur les Documents Cloud**].

1. Sur la page Gestion de Adobe Document Cloud , sélectionnez [!UICONTROL **Activation des rapports PDF**].

1. Pour configurer Adobe Document Cloud afin de transmettre des données à Adobe Analytics, utilisez la variable [SDK JavaScript Adobe Document Cloud](https://www.adobe.io/apis/documentcloud/dcsdk.html).


