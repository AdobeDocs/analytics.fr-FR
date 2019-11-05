---
description: Testez les règles Annuler la publication depuis votre console si vous utilisez l’hébergement Akamai.
keywords: Dynamic Tag Management;règle, module externe de sélecteur;akamai;test akamai;règles annuler la publication;test des règles annuler la publication;déboguer une règle
seo-description: Testez les règles Annuler la publication depuis votre console si vous utilisez l’hébergement Akamai.
seo-title: Test des règles non publiées pour l’hébergement Akamai
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Test des règles non publiées pour l’hébergement Akamai
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Test des règles non publiées pour l’hébergement Akamai

Testez les règles Annuler la publication depuis votre console si vous utilisez l’hébergement Akamai.

Le module externe Switcher est souvent le moyen le plus simple pour effectuer des tests. Pour plus d’informations, voir [Modules externes Search Discovery](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html) dans la documentation du produit Dynamic Tag Management.

Les étapes suivantes indiquent comment tester sans utiliser le module externe de sélecteur :

1. Accédez à la console web sur votre site, puis tapez `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Appuyez sur **[!UICONTROL Entrée]**.
1. Saisissez `_satellite.setDebug(true)`, puis appuyez sur **[!UICONTROL Entrée]**.
1. Actualisez la page.

   Cette action permet de charger la bibliothèque d’évaluation et de définir le débogueur pour que vous puissiez afficher toutes les informations de toutes les règles (publiées / non publiées) se déclenchant sur la page.
1. Une fois terminé, exécutez `localStorage.setItem('sdsat_stagingLibrary', false)`, puis appuyez sur **[!UICONTROL Entrée]**.

   Résultat de l’étape
