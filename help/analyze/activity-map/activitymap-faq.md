---
description: Questions fréquentes sur la configuration, la configuration et l’utilisation des fonctionnalités dans [!Carte d’activités DNL].
seo-description: Questions fréquentes sur la configuration, la configuration et l’utilisation des fonctionnalités dans [!Carte d’activités DNL].
seo-title: FAQ sur [!Carte d’activités DNL]
solution: Analytics
title: FAQ sur [!Carte d’activités DNL]
topic: Activity Map
uuid: e4f6d4e2-55d1-4e32-bf70-a334178af370
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# [!DNL Activity Map] FAQ

Questions fréquentes sur l’installation, la configuration et l’utilisation de fonctionnalités dans [!DNL Activity Map].

## Mise en œuvre et AppMeasurement {#section_FB46DD652E854C07AD339D7DD5CBCEC6}

**Q : Quelles sont les étapes de mise en oeuvre pour activer la nouvelle[!DNL Activity Map]?**

A : Veuillez consulter [Activer [!Carte d’activités DNL]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)

**Q : Tous les clients Analytics ont-ils accès à la page d’activation d’Activity Map dans les outils d’administration ?**

A: Adobe SiteCatalyst customers do not have access to the Admin Console’s [!DNL Activity Map] Enablement page. Seules les entreprises sous contrat Adobe Analytics Standard et Adobe Analytics Premium ont accès à cette page de configuration.

**Q : Le nouveau code AppMeasurement peut-il être configuré à l’aide de la Dynamic Tag Management ?**

R : Oui, vous pouvez [mettre en œuvre manuellement](https://marketing.adobe.com/resources/help/en_US/dtm/analytics_dtm.html) le nouveau code AppMeasurement.

**Q : Quels sont les principaux changements apportés à la bibliothèque AppMeasurement version 1.6 ?**

A: The only change in AppMeasurement v1.6 is in the [!DNL Activity Map] link tracking process methodology that requires the collection of Page name, Link ID and RegionID.

**Q : AppMeasurement sera-t-il déployé au niveau du domaine plutôt que sur des pages spécifiques ?**

R : AppMeasurement est déployé au niveau des suites de rapports. Celui-ci est généralement associé à un niveau de domaine, mais cela varie pour chaque mise en œuvre.

**[!DNL Activity Map]Q : La gestion dynamique des balises charge automatiquement une version (1.3.4) de l’API visiteur plus ancienne que celle requise par  (1.5.1). Est-ce un problème ?**

R : Non. [!DNL Activity Map] ne dépend pas de VisitorAPI.

## [!DNL Activity Map] application {#section_E4F2DAC09EBA4E3BA7BACB49A0A89F8D}

**[!DNL Activity Map]Q : Puis-je utiliser si je n’utilisais pas la carte des clics des visiteurs auparavant sur mon site web ?**

R : La version héritée (désormais simplement appelée ClickMap) n’a pas besoin d’être préalablement installée pour mettre en œuvre la nouvelle version. Adobe continuera à prendre en charge la version héritée pour une période limitée.

**Q : Quels navigateurs et versions sont pris en charge par[!DNL Activity Map]?**

R : Seule la dernière version des quatre navigateurs principaux (Chrome, Firefox, Safari et IE) est prise en charge.

**Q : Quels sont les paramètres de superposition par défaut ?**

A: By default, [!DNL Activity Map] shows ALL links that have collected data.

Lorsque des panneaux contextuels s’affichent au-dessus des pages web des clients, les superpositions appartenant aux liens situés en dessous du panneau contextuel peuvent s’afficher au-dessus de celui-ci.

**Q : Pourquoi manque-t-il les superpositions de certains éléments avec classement ?**

R : Certains liens avec classement peuvent être masqués sur la page (par exemple des liens de sous-menu). Par conséquent, les superpositions de lien correspondantes ne s’afficheront pas. Vous pouvez donc vous attendre à voir des classements de superpositions auxquels manquent certaines valeurs de classement spécifiques, car le classement est calculé pour tous les liens de la page (le lien visible + les liens masqués).

**Q : Comment le classement des liens est-il déterminé dans le rapport Tous les liens ?**

* En mode **dégradé** et **bulle**, le classement est déterminé par la colonne de mesures. Pour les liens disposant de la même valeur de mesure, le classement est déterminé selon l’ordre alphabétique des ID de lien.
* En mode **gagnant et perdant**, le classement est principalement déterminé par la colonne de % de gain. Pour les liens disposant du même gain, le classement est déterminé selon l’ordre alphabétique des ID de lien.

**Q : Pourquoi les données de clic sur les liens ne sont-elles pas collectées lors de l’[!DNL Activity Map]exécution ?**

A: While [!DNL Activity Map] is in use, link click data is not collected by the Analytics tag. Ce comportement est identique à celui du module Carte des clics.

**Q : Pourquoi le menu déroulant des mesures répertorie-t-il la même mesure plusieurs fois ?**

A: [!DNL Activity Map] lists metrics for all report suites. Par conséquent, vous pouvez vous attendre à voir des mesures en double si l’entreprise n’est pas passée par un [processus de consolidation des mesures](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_transition.html).

Le menu déroulant des mesures vous permet de limiter la liste des mesures calculées à celles qui sont affectées à la suite de rapports de la page visitée.

**Q : Comment le rapport[!DNL Activity Map]Tous les liens se compare-t-il aux[!DNL Activity Map]rapports Rapports et analyses ?**

A : Pour extraire le rapport Tous les liens dans [!DNL Activity Map], nous créons une demande de ventilation comme suit : [!DNL Activity Map] Page = "visitedpage", ventilée par [!DNL Activity Map] &amp;région dans `<list of link&regions present in the page at rendering time>`.

To get an equivalent report in Reports &amp; Analytics, you would need to first navigate to the [!DNL Activity Map] Page report. Vous pouvez appliquer un filtre pour le nom de la page visitée dans [!DNL Activity Map]. The visited Pagename is shown in the left column in the [!DNL Activity Map] Page Details Bottom Panel. Once the page has been found, you can break down from that page and choose [!DNL Activity Map] Links &amp; Regions as a secondary dimension.

Cependant, il est important de noter que le rapport obtenu dans Rapports et analyses répertoriera tous les liens et régions collectés pour cette page. But [!DNL Activity Map] only reports on Links&amp;Regions that are currently present in the webpage. Si vous possédez un site d’actualités, seules les données pour l’actualité figurant sur la page à ce moment-là s’afficheront, et non les actualités qui y figuraient plus tôt dans la journée.

**[!DNL Activity Map]Q : Comment fonctionne-t-elle avec les pages contenant plusieurs balises répertoriant plusieurs suites de rapports ?**

A: By default, [!DNL Activity Map] uses the report suite that is associated with the first tag that is sent by the page.

You can select a different tagged report suite through the [!DNL Activity Map] Settings &gt; Others tab.

**[!DNL Activity Map]Q : Pendant combien de temps analyse-t-elle la balise Analytics ?**

R : Nous analysons la balise Analytics jusqu’à 20 secondes après un événement de page.

**Q : Comment gère-t-on[!DNL Activity Map]le contenu dynamique ?**

A: [!DNL Activity Map] checks every 2 seconds to see if it has found changes in the state of the web page such as:

* le contenu HTML devenu visible ;
* le contenu HTML masqué ;
* le nouveau contenu HTML injecté.

Si le contenu est masqué ou visible, l’application modifie automatiquement l’état des liens affectés (et donc des superpositions) de masqué à visible ou de visible à masqué.

Si du nouveau contenu a été injecté, l’application récupère les liens associés et les données d’analyse correspondantes et ajoute des superpositions pour ces liens.

**Q : Sur quelle mesure se base le rapport Flux de page ?**

R : Toutes les données affichées se basent sur les pages vues.

**Q : Pouvez-vous expliquer[!DNL Activity Map]le comportement avec différents types de pages ?**

*Page web sans balise Analytics*

Un message d’avertissement s’affiche sous la barre d’outils et indique qu’aucune balise n’est présente.

*Page web avec balise Analytics incompatible (AppMeasurement version 1.5 ou antérieure)*

Un message d’avertissement s’affiche indiquant que vous devez (/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) mettre à niveau le code de page vers la version 1.6.

*Page Web avec balise Analytics compatible (AppMeasurement version 1.6 ou ultérieure), mais la création de[!DNL Activity Map]rapports n’était pas activée dans les outils d’administration*

Un message d'avertissement s'affiche, indiquant que vous devez demander à votre administrateur de \[Activer le [!DNL Activity Map] rapport\](/home/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md").

**Q : Puis-je exporter[!DNL Activity Map]des données (contextData) via le flux[de données](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html)Analytics ?**

R : Non.

## Segmentation dans [!DNL Activity Map]{#section_44D6C5F59B8542DC8A3AF38BD8078DCA}

**Q : Les segments sont-ils liés aux segments utilisateurs individuels ? Or are shared Admin-level segments available in[!DNL Activity Map]?**

A: [!DNL Activity Map] inherits your Admin-level segments (reporting segments) from Analytics.

**Q : Les segments fonctionnent-ils en mode réel ?**

R : Non, les segments ne fonctionnent pas en mode réel. La fonctionnalité est similaire à celle de la création de rapports en temps réel dans Reports &amp; Analytics.

## Suites de rapports virtuelles{#section_BDB0CA9E732F478EAC349A79753A78DB}

**Q : Est-il[!DNL Activity Map]compatible avec les suites de rapports virtuelles ?**

R : Oui. However, due to virtual report suite limitations, [!DNL Activity Map]'s Live Mode is not compatible with virtual report suites.
