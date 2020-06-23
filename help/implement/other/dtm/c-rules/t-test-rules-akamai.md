---
description: Testez les règles Annuler la publication depuis votre console si vous utilisez l’hébergement Akamai.
keywords: Dynamic Tag Management;rule;switcher plug-in;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Test des règles non publiées pour l’hébergement Akamai
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: ht
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Test des règles non publiées pour l’hébergement Akamai

Testez les règles Annuler la publication depuis votre console si vous utilisez l’hébergement Akamai.

Le plug-in Switcher est souvent le moyen le plus simple d’effectuer des tests. Pour plus d’informations, voir [Plug-ins Search Discovery](https://docs.adobe.com/content/help/fr-FR/dtm/using/resources/plugins/search-discovery-plugins.html) dans la documentation du produit Dynamic Tag Management.

Les étapes suivantes indiquent comment tester sans utiliser le plug-in de sélecteur :

1. Accédez à la console web sur votre site, puis tapez `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Appuyez sur **[!UICONTROL Entrée]**.
1. Saisissez `_satellite.setDebug(true)`, puis appuyez sur **[!UICONTROL Entrée]**.
1. Actualisez la page.

   Cette action permet de charger la bibliothèque d’évaluation et de définir le débogueur pour que vous puissiez afficher toutes les informations de toutes les règles (publiées / non publiées) se déclenchant sur la page.
1. Une fois terminé, exécutez `localStorage.setItem('sdsat_stagingLibrary', false)`, puis appuyez sur **[!UICONTROL Entrée]**.

   Résultat de l’étape
