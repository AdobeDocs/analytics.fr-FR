---
description: Questions fréquentes sur l’installation, la configuration et l’utilisation de fonctionnalités dans Activity Map.
title: Questions fréquentes sur Activity Map
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: 5a8ff1c81644c12f7d00ef147db197f54c48f60c

---


# Questions fréquentes sur Activity Map

Questions fréquentes sur l’installation, la configuration et l’utilisation de fonctionnalités dans Activity Map.

## Mise en œuvre et AppMeasurement

**Q : Quelles sont les étapes de mise en œuvre nécessaires pour activer la nouvelle version d’Activity Map ?**

R : Veuillez consulter [Activation d’Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**Q : Tous les clients Analytics ont-ils accès à la page d’activation d’Activity Map dans les outils d’administration ?**

R : Les clients Adobe SiteCatalyst n’ont pas accès à la page d’activation d’Activity Map dans Admin Console. Seuls les sous contrat Adobe Analytics Standard et Adobe Analytics Premium ont accès à cette page de configuration.

**Q : Le nouveau code AppMeasurement peut-il être configuré via la gestion dynamique des balises (DTM) ?**

A : Oui, vous pouvez implémenter [](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) manuellement le nouveau code AppMeasurement.

**Q : Quels sont les grands changements dans la bibliothèque AppMeasurement v1.6 ?**

A : La seule modification dans AppMeasurement v1.6 se trouve dans la méthodologie de processus de suivi des liens de  Carte de qui nécessite la collecte du nom de page, de l’ID de lien et de l’ID de région.

**Q : AppMeasurement sera-t-il déployé au niveau du domaine plutôt que sur des pages spécifiques ?**

A : AppMeasurement est déployé au niveau de la suite de rapports. Le niveau de la suite de rapports est généralement associé à un niveau de domaine, mais cela diffère pour chaque implémentation.

**Q : La gestion dynamique des balises charge automatiquement une version plus ancienne (1.3.4) de l’API du que  Carte  ne le souhaite (1.5.1). Est-ce un problème ?**

R : Non.  fonctionnalité de  de carte de ne dépend pas de l’API visiteur.

## Application Activity Map

<!--**Q: How does Activity Map support Single-Page Applications (SPA)?**

A: 

* Every few seconds, Activity Map scans the web page, looking for changes to the page. ActivityMap finds new content on the page without needing a new page load, but this new content is always attributed to the first pageName found when the page loaded.

* Activity Map checks to see if the visibility of links that it knows about has changed. If a change in visibility is found, then the [Links On Page](/help/analyze/activity-map/activitymap-links-report.md) table's Present column for that link updates with **[!UICONTROL Displayed]** or **[!UICONTROL Hidden]**.

* When user interaction creates new content, any new elements that are found by AppMeasurement to be a link will be added to the **[!UICONTROL Links On Page]** table. Activity Map sends a new data request that includes these new links. The new links should appear in the **[!UICONTROL Links On Page]** table when the data request is handled by the UI.-->

**Q :  carte  de l&#39;fournit-elle des données sur &quot;&quot; ?**

A : Non, Adobe ne suit pas les liens affichés.

**Q : Puis-je utiliser  Carte  si je n&#39;utilisais pas auparavant Carte des clics sur mon site Web ?**

A : L&#39;installation de la version héritée (désormais simplement appelée ClickMap) n&#39;est pas une condition préalable à la mise en oeuvre de la nouvelle version. Adobe continuera de prendre en charge la version héritée pendant une période limitée.

**Q : Quels sont les navigateurs et versions pris en charge par   Map ?**

A : Nous prenons en charge la dernière version des quatre principaux navigateurs (Chrome, Firefox, Safari et IE).

**Q : Quels sont les paramètres d’incrustation par défaut ?**

A : Par défaut,   Map affiche TOUS les liens qui ont collecté des données.

Lorsque des panneaux contextuels s’affichent au-dessus des pages Web des clients, des incrustations appartenant aux liens situés sous le panneau contextuel peuvent s’afficher au-dessus du panneau contextuel.

**Q : Pourquoi certaines incrustations d’éléments de classement sont-elles manquantes ?**

A : Certains liens avec classement peuvent être masqués dans la page (liens de sous-menu, par exemple). Par conséquent, les incrustations de lien correspondantes ne s’afficheront pas. Vous pouvez donc vous attendre à voir des classements d’incrustation qui ne contiennent pas certaines valeurs de classement spécifiques, car le classement est calculé pour tous les liens de la page (le lien actuel + les liens masqués).

**Q : Comment le classement des liens est-il déterminé dans le rapport Tous les liens ?**

* En mode **Dégradé** et **Bulle** : Le classement est déterminé par la colonne de mesures. Pour les liens avec la même valeur de mesure, le classement est basé davantage sur l’ordre alphabétique des ID de lien.
* En mode **gagnant et perdant** , le classement est principalement déterminé par la colonne % gain. Pour les liens avec le même gain, le classement est basé davantage sur l’ordre alphabétique de l’ID de lien.

**Q : Pourquoi les données de clic sur les liens ne sont-elles pas collectées lorsque  Carte  est en cours d’exécution ?**

A :  carte  de est en cours d’utilisation, mais les données de clic sur les liens ne sont pas collectées par la balise Analytics. Ce comportement est conforme au comportement du module ClickMap.

**Q : Comment le rapport de mise en  de tous les liens de  est-il comparé aude mise en correspondance de  de rapports et analyses avec les rapports et analyses ?**

R : Pour récupérer le rapport Tous les liens dans Activity Map, nous créons une demande de ventilation telle que la suivante : Page Activity Map = « visitedpage », ventilée par lien et région d’Activity Map dans `<list of link&regions present in the page at rendering time>`.

Pour obtenir un rapport équivalent dans les rapports et analyses, vous devez d’abord accéder au rapport de page de  de carte du. Vous pouvez alors filtrer le nom de la page visitée dans   Map. Le nom de la page visitée est indiqué dans la colonne de gauche du panneau inférieur des détails de la page de  de mise en correspondance . Une fois la page trouvée, vous pouvez la ventiler à partir de cette page et choisir   mettre en correspondance les liens et les régions comme dimension secondaire.

Toutefois, il est important de noter que le rapport obtenu dans R&amp;A tous les liens et régions collectés pour cette page. Mais  Carte des  de ne rapporte que les liens et les régions qui sont actuellement présents dans la page Web. Donc si vous avez un site d&#39;informations, il ne montrera que les données pour l&#39;actualité présente à ce moment-là, et non les nouvelles qui étaient présentes plus tôt dans la journée.

**Q : Comment   Map fonctionne-t-il avec les pages contenant plusieurs balises répertoriant plusieurs suites de rapports ?**

A : Par défaut,   Map utilise la suite de rapports associée à la première balise envoyée par la page. Vous pouvez sélectionner une suite de rapports balisée différente dans l’onglet Paramètres d’Activity Map > Autres.

**Q : Pendant combien de temps   Map analyse-t-il la balise Analytics ?**

A : Nous analysons la balise Analytics pendant 20 secondes au maximum après la fin d’un  de page.

**Q : Comment  Carte  gère-t-elle le contenu dynamique ?**

A :  Carte  vérifie toutes les 2 secondes si des modifications ont été apportées à l’état de la page Web, telles que :

* Contenu HTML devenu visible
* Contenu HTML masqué
* Nouveau contenu HTML injecté

Si le contenu est masqué ou affiché, l’application modifie automatiquement l’état des liens affectés (et donc des recouvrements) de masqué à affiché ou de affiché à masqué.

Si du nouveau contenu est injecté, l’application récupère les liens associés, extrait les données d’analyse pour eux et ajoute des superpositions pour ces liens.

**Q : Sur quelle mesure le rapport Flux de page repose-t-il ?**

A : Toutes les données affichées sont basées sur les  de page.

**Q : Pouvez-vous expliquer  comportement de Carte  avec différents types de pages ?**

*Page Web sans balise Analytics*

Un message d’avertissement s’affiche sous la barre d’outils pour indiquer qu’aucune balise n’est présente.

*Page Web avec balise Analytics incompatible (AppMeasurement version 1.5 ou antérieure)*

Un message d’avertissement s’affiche, indiquant que vous devez mettre à niveau le code de page vers la version 1.6 ou plus.

*Page web avec balise Analytics compatible (AppMeasurement version 1.6 ou ultérieure), mais la création de rapports d’Activity Map n’a pas été activée dans les outils d’administration*

Un message d’avertissement s’affiche et indique que vous devez demander à votre administrateur d’\[Activer les rapports d’Activity Map\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md&quot;).

**Q : Puis-je exporter les données d’Activity Map (contextData) par l’intermédiaire du [flux de données Analytics](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-overview.html) ?**

R : Non.

## Segmentation dans Activity Map

**Q : Les segments sont-ils liés aux segments d’utilisateurs individuels ? Les segments partagés sont-ils disponibles dans   Map ?**

A :   Carte de hérite de vos segments de  d’Analytics.

**Q : Les segments fonctionnent-ils en mode réel ?**

A : Non, les segments ne fonctionnent pas en mode réel. Cette fonctionnalité est équivalente à celle des  en temps réel dans les rapports et analyses.

## Suites de rapports virtuelles

**Q :  carte  est-elle compatible avec les suites de rapports virtuelles ?**

R : Oui. Toutefois, en raison des limitations des suites de rapports virtuelles,  mode en direct de  Carte d’n’est pas compatible avec les suites de rapports virtuelles.
