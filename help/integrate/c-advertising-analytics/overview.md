---
description: Découvrez tout ce que vous pouvez faire avec Advertising Analytics, y compris les autorisations requises, ainsi que les dimensions et mesures disponibles.
title: Advertising Analytics
feature: Advertising Analytics
exl-id: bc18b74a-0317-4871-b2e0-ec0977ef1731
source-git-commit: 6bedfb9b1333a442bf17cf71dad1e0883b97fd45
workflow-type: tm+mt
source-wordcount: '1112'
ht-degree: 71%

---

# Advertising Analytics

Advertising Analytics vous permet de voir toutes vos données de référencement payant Google Ads et Microsoft Advertising côte à côte dans Adobe Analytics. Auparavant, toutes les publicités Google ou données Microsoft Advertising devaient être affichées dans Adobe Advertising Cloud (AMO) ou dans chaque interface publicitaire respective. Vous pouvez désormais obtenir des données sur les impressions, les clics et les coûts directement à partir des moteurs de recherche ainsi que des instances AMO ID (instances de clics).

En réunissant les données des moteurs de recherche dans Adobe Analytics, vous pouvez analyser les mêmes données en utilisant la puissance d’Analysis Workspace. Le nouveau modèle [Performance de référencement payant](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md) dans Workspace facilite cette analyse.

![](assets/aa_aw.png)

Cette intégration est destinée aux audiences ci-dessous :

* Les **analystes** qui doivent collecter des rapports de performance pour les spécialistes marketing du référencement payant.
* Les **spécialistes marketing du référencement payant** qui souhaitent répondre à ces questions : quelle est la quantité de trafic que j’envoie vers notre site et que les clients convertissent ? Quelles sont mes campagnes publicitaires rentables ?


## Conditions préalables {#prerequisites}

* Advertising Analytics est disponible pour les SKU [Select](https://www.adobe.com/fr/data-analytics-cloud/analytics/select.html), [Prime](https://www.adobe.com/fr/data-analytics-cloud/analytics/prime.html) ou [Ultimate](https://www.adobe.com/fr/data-analytics-cloud/analytics/ultimate.html) d’Adobe Analytics.
* Cette fonctionnalité est disponible pour les clients ne bénéficiant pas d’Advertising Cloud ni d’AMO.
* Vous devez être administrateur Adobe Analytics pour avoir accès à Advertising Analytics ou appartenir à un profil de produit auquel un [accès](/help/integrate/c-advertising-analytics/overview.md#permissions) a été accordé à Advertising Analytics.
* Pour toute suite de rapports dans laquelle vous souhaitez afficher les publicités Google ou les données de recherche Microsoft Advertising, vous devez [activer ces suites de rapports pour Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md) ( **[!UICONTROL Admin]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Configuration Advertising Analytics]**).
* Vous avez besoin des informations de connexion pour un utilisateur autorisé à modifier le ou les comptes de recherche que vous souhaitez intégrer à Adobe Analytics, telles qu’un ID de compte Google et un mot de passe.
* Dans le cas de Microsoft Advertising, vous avez également besoin des [[!UICONTROL Identifiant de compte] et [!UICONTROL Identifiant de compte Manager]](c-adanalytics-workflow/aa-locate-account-id.md).

## Autorisations Advertising Analytics  {#permissions}

Analytics dispose de deux autorisations qui sont automatiquement accordées aux administrateurs Analytics. Ceux-ci peuvent ensuite choisir d’accorder ces autorisations à des non-administrateurs.

| Autorisation | Définition | Accorder une autorisation si vous êtes connecté à Adobe Experience Cloud |
| --- | --- | --- |
| Gestion Advertising Analytics | Permet aux utilisateurs de configurer, modifier ou afficher des comptes de recherche publicitaire. | Connectez-vous à [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Products] > [!UICONTROL Adobe Analytics] > [!UICONTROL Product Profile] > [!UICONTROL Permissions] onglet > [!UICONTROL Analytics Tools] > [!UICONTROL Advertising Analytics Management] |
| Configuration Advertising Analytics | Permet aux utilisateurs de configurer des suites de rapports à configurer pour Advertising Analytics. | Connectez-vous à [adminconsole.adobe.com](https://adminconsole.adobe.com) > [!UICONTROL Products] > [!UICONTROL Adobe Analytics] > [!UICONTROL Product Profile] > [!UICONTROL Permissions] onglet > [!UICONTROL Analytics Tools] > [!UICONTROL Advertising Analytics Configuration] |

## Dimensions et mesures Advertising Analytics {#dimensions-metrics}

Advertising Analytics ajoute les dimensions et mesures suivantes à Analysis Workspace, Report Builder et à l’API de création de rapports d’Analytics.

### Dimensions

>[!IMPORTANT]
>
>Cette intégration crée un ensemble de dimensions à travers les classifications de la variable AMO ID. Ces nouvelles dimensions n’ont pas d’incidence ni ne modifient les canaux marketing existants ou les dimensions des variables de suivi de campagne. AMO ID est connectée à un profil visiteur lorsque le visiteur parvient sur un site à partir d’une annonce de référencement payant. Par conséquent, les dimensions AMO peuvent être utilisées pour ventiler les deux mesures AMO fournies par l’intégration, ainsi que toutes les données saisies en aval par le visiteur (visites, visiteurs, pages vues, taux de rebond, commandes, recettes, événements personnalisés, etc.). Elles peuvent également être ventilées par d’autres dimensions lors de la création de rapports sur d’autres mesures sur site.
>
>Les classifications pour ces mesures sont mises à jour quotidiennement. Par conséquent, si vous modifiez les métadonnées dans le moteur de recherche, il est possible que ces changements ne soient reflétés que le jour suivant la mise à jour des classifications.

| Nom de la classification (dimension) | Définition |
| --- | --- |
| **[!UICONTROL Type de correspondance de mots-clés (AMO ID)]** | Le type de correspondance de mot-clé. Les valeurs seront généralement Large, Expression, Exact ou Aucune valeur si le type d’annonce n’a aucune correspondance. |
| **[!UICONTROL Plateforme publicitaire (AMO ID)]** | Le nom du moteur de recherche. Les valeurs peuvent inclure « Google AdWords » ou « Microsoft Bing Ads ». |
| **[!UICONTROL Compte (AMO ID)]** | Le nom du compte de moteur de recherche qui est suivi. |
| **[!UICONTROL Campaign (AMO ID)]** | Le nom de la campagne dans votre compte de moteur de recherche. |
| **[!UICONTROL Groupe publicitaire (AMO ID)]** | Le nom du groupe d’annonces dans vos campagnes de moteur de recherche. |
| **[!UICONTROL Annonce publicitaire (AMO ID)]** | Le titre de l’annonce + la description de l’annonce utilisés dans votre annonce. |
| **[!UICONTROL Mot-clé (AMO ID)]** | Valeur du mot-clé de votre compte de moteur de recherche. |
| **[!UICONTROL Type de correspondance (AMO ID)]** | Le type de correspondance de mot-clé attribué à votre mot-clé. Les valeurs seront généralement Large, Expression, Exact ou Aucune valeur si le type d’annonce n’a aucune correspondance. |
| **[!UICONTROL Type d’annonce publicitaire (AMO ID)]** | Le type de publicité diffusée, en général « Publicité textuelle ». |
| **[!UICONTROL Titre de l’annonce publicitaire (AMO ID)]** | L’objet Titre utilisé dans votre annonce. |
| **[!UICONTROL Description de l’annonce publicitaire (AMO ID)]** | L’objet Description de l’annonce utilisé dans votre annonce. |
| **[!UICONTROL URL d’affichage des publicités (AMO ID)]** | L’objet URL d’affichage de l’annonce utilisé dans votre annonce. |
| **[!UICONTROL URL de destination de l’annonce publicitaire (AMO ID)]** | L’URL de la page de destination ou l’URL finale de votre annonce. |
| **[!UICONTROL Réseau (AMO ID)]** | Le réseau sur lequel l’annonce est hébergée. Pour Advertising Analytics, cette valeur est toujours « Recherche ». |
| **[!UICONTROL Emplacement (AMO ID)]** | Le site Web du placement géré (pour les réseaux de contenu). Seuls les placements gérés utilisent cette dimension. |
| **[!UICONTROL Cible du produit (AMO ID)]** | Le nom de la cible du produit utilisé sur les annonces PLA (il ne s’agit pas du produit réellement acheté). |
| **[!UICONTROL Optimisation (AMO ID)]** | Cette dimension n’est pas utilisée par Advertising Analytics. Elle n’est utilisée que par les clients bénéficiant d’Advertising Cloud. |
| **[!UICONTROL Appareil (AMO ID)]** | Non utilisé aujourd’hui. Espace réservé à l’éventuelle amélioration future du produit pour le type d’appareil cible indiqué (p. ex. mobile, bureau) de l’annonce (et non l’appareil réel du visiteur). |

### Mesures

>[!IMPORTANT]
>
>Les mesures fournies par Advertising Analytics (répertoriées ci-dessous) sont des données synthétiques provenant des moteurs de recherche. Elles ne sont pas connectées aux profils de visiteur Analytics. Elles sont connectées uniquement à la variable AMO ID et à ses dimensions de classifications associées. Par conséquent, elles ne doivent pas faire l’objet d’un rapport par d’autres segments/dimensions que ceux basés sur les dimensions AMO ID. Si vous tentez de générer ce rapport, Analytics affichera des zéros à la place des données. Vous pouvez les inclure dans les mesures calculées, avec d’autres mesures, mais celles-ci doivent également être ventilées selon les dimensions AMO ID uniquement.
>
>Ces mesures proviennent des données d’une base journalière. Aucune donnée ne sera donc disponible pour la journée en cours. Elles ne doivent pas non plus être reportées sur une granularité inférieure à la granularité journalière.
>
>Il existe une mesure d’Instances AMO ID qui est configurée lorsqu’AMO ID est configurée sur la page de destination (c.-à-d. un clic publicitaire). Cette mesure est saisie en temps réel lors de l’accès à la page de destination et est disponible pour les ventilations avec d’autres dimensions également configurées sur la page de destination.

| Nom de la mesure | Définition |
| --- | --- |
| **[!UICONTROL AMO - Impressions]** | Le nombre d’impressions d’annonces comme indiqué par le moteur de recherche. |
| **[!UICONTROL AMO - Clics]** | Le nombre de clics sur les annonces comme indiqué par le moteur de recherche. |
| **[!UICONTROL AMO - Coût]** | Le coût payé pour chaque mot-clé/annonce comme indiqué par le moteur de recherche. |
