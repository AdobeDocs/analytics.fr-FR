---
description: Testez les règles Annuler la publication depuis votre console si vous utilisez l’hébergement Akamai.
keywords: Gestion dynamique des balises;règle;module externe de commutation;akamai;test akamai;règles non publiées;test des règles non publiées;règle de débogage
seo-description: Testez les règles Annuler la publication depuis votre console si vous utilisez l’hébergement Akamai.
seo-title: Test des règles non publiées pour l’hébergement Akamai
solution: Experience Cloud,Analytics,Target,Gestion dynamique des balises
title: Test des règles non publiées pour l’hébergement Akamai
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Test des règles non publiées pour l’hébergement Akamai

Testez les règles Annuler la publication depuis votre console si vous utilisez l’hébergement Akamai.

Le module externe Switcher est souvent le moyen le plus simple pour effectuer des tests. Pour plus d’informations, voir [Modules externes Search Discovery](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html) dans la documentation du produit Dynamic Tag Management.

Les étapes suivantes indiquent comment tester sans utiliser le module externe de sélecteur :

1. Accédez à la console web sur votre site, puis tapez `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Press **[!UICONTROL Enter]**.
1. Saisissez `_satellite.setDebug(true)`, puis appuyez sur **[!UICONTROL Entrée]**.
1. Actualisez la page.

   Cette action permet de charger la bibliothèque d’évaluation et de définir le débogueur pour que vous puissiez afficher toutes les informations de toutes les règles (publiées / non publiées) se déclenchant sur la page.
1. Une fois terminé, exécutez `localStorage.setItem('sdsat_stagingLibrary', false)`, puis appuyez sur **[!UICONTROL Entrée]**.

   Résultat de l’étape