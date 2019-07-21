---
description: Testez les règles Annuler la publication depuis votre console si vous utilisez l’hébergement Akamai.
keywords: Gestion dynamique des balises ; rule ; switcher plugin ; akamai ; test akamai ; règles non publiées ; tester les règles non publiées ; règle de débogage
seo-description: Testez les règles Annuler la publication depuis votre console si vous utilisez l’hébergement Akamai.
seo-title: Test des règles non publiées pour l’hébergement Akamai
solution: Marketing Cloud, Analytics, Target, gestion dynamique des balises
title: Test des règles non publiées pour l’hébergement Akamai
uuid: 979 e 3 d 74-8 d 96-47 d 0-b 581-cf 5371248434
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Test des règles non publiées pour l’hébergement Akamai

Testez les règles Annuler la publication depuis votre console si vous utilisez l’hébergement Akamai.

Le module externe Switcher est souvent le moyen le plus simple pour effectuer des tests. Pour plus d’informations, voir [Modules externes Search Discovery](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html) dans la documentation du produit Dynamic Tag Management.

Les étapes suivantes indiquent comment tester sans utiliser le module externe de sélecteur :

1. Accédez à la console web sur votre site, puis tapez `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Press **[!UICONTROL Enter]**.
1. Type `_satellite.setDebug(true)`, then press **[!UICONTROL Enter]**.
1. Actualisez la page.

   Cette action permet de charger la bibliothèque d’évaluation et de définir le débogueur pour que vous puissiez afficher toutes les informations de toutes les règles (publiées / non publiées) se déclenchant sur la page.
1. When finished, run `localStorage.setItem('sdsat_stagingLibrary', false)`, then press **[!UICONTROL Enter]**.

   Résultat de l’étape