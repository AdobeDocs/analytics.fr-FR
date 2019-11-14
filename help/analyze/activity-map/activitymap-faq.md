---
description: Questions fréquentes sur l’installation, la configuration et l’utilisation de fonctionnalités dans Activity Map.
solution: Analytics
title: Questions fréquentes sur Activity Map
topic: Activity map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Questions fréquentes sur Activity Map

Questions fréquentes sur l’installation, la configuration et l’utilisation de fonctionnalités dans Activity Map.

## Mise en œuvre et AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**Q : Quelles sont les étapes de mise en œuvre nécessaires pour activer la nouvelle version d’Activity Map ?**

R : Veuillez consulter [Activation d’Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**Q : Tous les clients Analytics ont-ils accès à la page d’activation d’Activity Map dans les outils d’administration ?**

R : Les clients Adobe SiteCatalyst n’ont pas accès à la page d’activation d’Activity Map dans Admin Console. Seules les entreprises sous contrat Adobe Analytics Standard et Adobe Analytics Premium ont accès à cette page de configuration.

**Q : Le nouveau code AppMeasurement peut-il être configuré à l’aide de la Dynamic Tag Management ?**

R : Oui, vous pouvez [mettre en œuvre manuellement](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) le nouveau code AppMeasurement.

**Q : Quels sont les principaux changements apportés à la bibliothèque AppMeasurement version 1.6 ?**

R : Le seul changement apporté à AppMeasurement version 1.6 est la méthodologie du processus de suivi des liens d’Activity Map qui nécessite la collecte du nom de la page, de l’ID de lien et de l’ID de région.

**Q : AppMeasurement sera-t-il déployé au niveau du domaine plutôt que sur des pages spécifiques ?**

R : AppMeasurement est déployé au niveau des suites de rapports. Celui-ci est généralement associé à un niveau de domaine, mais cela varie pour chaque mise en œuvre.

**Q : La gestion dynamique des balises charge automatiquement une version (1.3.4) de l’API visiteur plus ancienne que celle requise par Activity Map (1.5.1). Est-ce un problème ?**

R : Non. La fonctionnalité d’Activity Map ne dépend pas de l’API visiteur.

## Application Activity Map {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**Q : Puis-je utiliser Activity Map si je n’utilisais pas la carte des clics des visiteurs auparavant sur mon site web ?**

R : La version héritée (désormais simplement appelée ClickMap) n’a pas besoin d’être préalablement installée pour mettre en œuvre la nouvelle version. Adobe continuera à prendre en charge la version héritée pour une période limitée.

**Q : Quels navigateurs et versions sont pris en charge par Activity Map ?**

R : Seule la dernière version des quatre navigateurs principaux (Chrome, Firefox, Safari et IE) est prise en charge.

**Q : Quels sont les paramètres de superposition par défaut ?**

R : Par défaut, Activity Map affiche TOUS les liens qui ont collecté des données.

Lorsque des panneaux contextuels s’affichent au-dessus des pages web des clients, les superpositions appartenant aux liens situés en dessous du panneau contextuel peuvent s’afficher au-dessus de celui-ci.

**Q : Pourquoi manque-t-il les superpositions de certains éléments avec classement ?**

R : Certains liens avec classement peuvent être masqués sur la page (par exemple des liens de sous-menu). Par conséquent, les superpositions de lien correspondantes ne s’afficheront pas. Vous pouvez donc vous attendre à voir des classements de superpositions auxquels manquent certaines valeurs de classement spécifiques, car le classement est calculé pour tous les liens de la page (le lien visible + les liens masqués).

**Q : Comment le classement des liens est-il déterminé dans le rapport Tous les liens ?**

* En mode **dégradé** et **bulle**, le classement est déterminé par la colonne de mesures. Pour les liens disposant de la même valeur de mesure, le classement est déterminé selon l’ordre alphabétique des ID de lien.
* En mode **gagnant et perdant**, le classement est principalement déterminé par la colonne de % de gain. Pour les liens disposant du même gain, le classement est déterminé selon l’ordre alphabétique des ID de lien.

**Q : Pourquoi les données de clic sur les liens ne sont-elles pas collectées lors de l’exécution d’Activity Map ?**

R : Lors de l’utilisation d’Activity Map, les données de clic sur les liens ne sont pas collectées par la balise Analytics. Ce comportement est identique à celui du module Carte des clics.

**Q : Pourquoi le menu déroulant des mesures répertorie-t-il la même mesure plusieurs fois ?**

R : Activity Map répertorie les mesures pour toutes les suites de rapports. Par conséquent, vous pouvez vous attendre à voir des mesures en double si l’entreprise n’est pas passée par un [processus de consolidation des mesures](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html).

Le menu déroulant des mesures vous permet de limiter la liste des mesures calculées à celles qui sont affectées à la suite de rapports de la page visitée.

**Q : Comment le rapport Tous les liens d’Activity Map se compare-t-il à la création de rapports d’Activity Map de Reports &amp; Analytics ?**

R : Pour récupérer le rapport Tous les liens dans Activity Map, nous créons une demande de ventilation telle que la suivante : Page Activity Map = « visitedpage », ventilée par lien et région d’Activity Map dans `<list of link&regions present in the page at rendering time>`.

Pour obtenir un rapport équivalent dans Reports &amp; Analytics, vous devez d’abord naviguer vers le rapport Page d’Activity Map. Vous pouvez appliquer un filtre pour le nom de la page visitée dans Activity Map. Celui-ci s’affiche dans la colonne gauche du panneau inférieur des détails de la page d’Activity Map. Une fois la page trouvée, vous pouvez ventiler à partir de cette page et choisir les liens et régions d’Activity Map comme dimension secondaire.

Cependant, il est important de noter que le rapport obtenu dans Rapports et analyses répertoriera tous les liens et régions collectés pour cette page. Les rapports d’Activity Map tiennent uniquement compte des liens et régions figurant actuellement sur la page web. Si vous possédez un site d’actualités, seules les données pour l’actualité figurant sur la page à ce moment-là s’afficheront, et non les actualités qui y figuraient plus tôt dans la journée.

**Q : Comment Activity Map fonctionne-t-elle avec les pages contenant plusieurs balises répertoriant plusieurs suites de rapports ?**

R : Par défaut, Activity Map utilise la suite de rapports associée à la première balise envoyée par la page.

Vous pouvez sélectionner une suite de rapports balisée différente dans l’onglet Paramètres d’Activity Map &gt; Autres.

**Q : Pendant combien de temps Activity Map analyse-t-elle la balise Analytics ?**

R : Nous analysons la balise Analytics jusqu’à 20 secondes après un événement de page.

**Q : Comment Activity Map gère-t-elle le contenu dynamique ?**

R : Activity Map vérifie toutes les 2 secondes si des changements ont été apportés à l’état de la page web, par exemple :

* le contenu HTML devenu visible ;
* le contenu HTML masqué ;
* le nouveau contenu HTML injecté.

Si le contenu est masqué ou visible, l’application modifie automatiquement l’état des liens affectés (et donc des superpositions) de masqué à visible ou de visible à masqué.

Si du nouveau contenu a été injecté, l’application récupère les liens associés et les données d’analyse correspondantes et ajoute des superpositions pour ces liens.

**Q : Sur quelle mesure se base le rapport Flux de page ?**

R : Toutes les données affichées se basent sur les pages vues.

**Q : Pouvez-vous décrire le comportement d’Activity Map avec différents types de pages ?**

*Page web sans balise Analytics*

Un message d’avertissement s’affiche sous la barre d’outils et indique qu’aucune balise n’est présente.

*Page web avec balise Analytics incompatible (AppMeasurement version 1.5 ou antérieure)*

Un message d’avertissement s’affiche et indique que vous devez (/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) mettre à niveau le code de page vers la version 1.6.

*Page web avec balise Analytics compatible (AppMeasurement version 1.6 ou ultérieure), mais la création de rapports d’Activity Map n’a pas été activée dans les outils d’administration*

Un message d’avertissement s’affiche et indique que vous devez demander à votre administrateur d’\[Activer les rapports d’Activity Map\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md").

**Q : Puis-je exporter les données d’Activity Map (contextData) par l’intermédiaire du[flux de données Analytics](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) ?**

R : Non.

## Segmentation dans Activity Map {#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**Q : Les segments sont-ils liés aux segments utilisateurs individuels ? Les segments partagés au niveau administrateur sont-ils disponibles dans Activity Map ?**

R : Activity Map hérite de vos segments au niveau administrateur (segments de création de rapports) à partir d’Analytics.

**Q : Les segments fonctionnent-ils en mode réel ?**

R : Non, les segments ne fonctionnent pas en mode réel. La fonctionnalité est similaire à celle de la création de rapports en temps réel dans Reports &amp; Analytics.

## Suites de rapports virtuelles{#section_BDB0CA9E732F478EAC349A79753A78DB}

**Q : Activity Map est-elle compatible avec les suites de rapports virtuelles ?**

R : Oui. Cependant, en raison des limitations des suites de rapports virtuelles, le mode réel d’Activity Map n’est pas compatible avec celles-ci.
