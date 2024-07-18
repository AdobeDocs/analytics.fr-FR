---
description: Vous pouvez afficher les données de Document Cloud dans Adobe Analytics
title: Configurer les rapports de Document Cloud
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
source-git-commit: bdd9473b0ac3bd77ffeff53a095876e21ca2f4d4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%

---

# Configurer les rapports de Document Cloud

Vous pouvez configurer des dimensions et des mesures spécifiques au PDF pour qu’elles soient disponibles dans Adobe Analytics.

## Composants ajoutés lorsque vous activez la création de rapports de PDF

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

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **`<select report suite>`** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Gestion des Documents Cloud]** > [!UICONTROL **Création de rapports de Document Cloud**].

1. Sur la page Gestion de Adobe Document Cloud, sélectionnez [!UICONTROL **Activer les rapports du PDF**].

1. Pour configurer Adobe Document Cloud afin de transmettre des données à Adobe Analytics, utilisez le [SDK JavaScript Adobe Document Cloud](https://www.adobe.io/apis/documentcloud/dcsdk.html).
