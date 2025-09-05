---
description: Vous pouvez afficher les données Document Cloud dans Adobe Analytics
title: Configurer les rapports de Document Cloud
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%

---

# Configurer les rapports de Document Cloud

Vous pouvez configurer des dimensions et des mesures spécifiques à PDF qui seront disponibles dans Adobe Analytics.

## Composants ajoutés lors de l’activation du reporting PDF

Lorsque la création de rapports PDF est correctement configurée, les dimensions et mesures suivantes sont disponibles dans Adobe Analytics :

**Dimensions :**

* Terme de recherche PDF

* Niveau de zoom PDF

* Action PDF

* Numéro de page PDF

* Nom de fichier PDF

**Mesures :**

* Vues PDF

* Pages vues PDF

* Téléchargements PDF

* Recherche PDF

* PDF Bookmarks Used

* PDF Copy Text

* PDF Print

## Activation de la création de rapports PDF dans Adobe Analytics

1. Accédez à **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **`<select report suite>`** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Gestion des Document Cloud]** > [!UICONTROL **Rapports Document Cloud**].

1. Sur la page de gestion de Adobe Document Cloud, sélectionnez [!UICONTROL **Activer les rapports PDF**].

1. Pour configurer Adobe Document Cloud afin de transmettre des données à Adobe Analytics, utilisez la [SDK JavaScript Adobe Document Cloud](https://www.adobe.io/apis/documentcloud/dcsdk.html).
