---
description: Utilisation de l’inventaire Analytics
title: Inventaire Analytics
feature: Admin Tools
role: Admin
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 22%

---

# Inventaire Analytics {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Inventaire Analytics"
>abstract="Cette page présente une vue d’ensemble complète de votre environnement Adobe Analytics, y compris le nombre de projets et de composants, les suites de rapports, les utilisateurs et utilisatrices, etc. Ces informations sont particulièrement utiles lorsque vous commencez à vous préparer à la mise à niveau vers Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

L’inventaire Analytics fournit une vue d’ensemble complète de votre environnement Adobe Analytics, y compris le nombre de projets et de composants, les suites de rapports, les utilisateurs, etc. Ces informations sont particulièrement utiles lorsque vous commencez à vous préparer à la mise à niveau vers Customer Journey Analytics.

L’objectif de l’inventaire Analytics est de vous aider à répondre aux questions suivantes :

* Pour votre organisation, de quelles ressources (telles que les suites de rapports, les segments, les utilisateurs, les projets d’espace de travail, etc.) avez-vous besoin pour migrer et quelles ressources pouvez-vous laisser ?

* Une fois que vous avez déterminé la ressource à migrer :

   * Devriez-vous effectuer un nettoyage des ressources avant cette mise à niveau ?

   * Devriez-vous procéder à une consolidation des actifs dans le cadre du processus ?

   * Quelle doit être la séquence de mise à niveau de vos ressources ?

   * Quelles suites de rapports devriez-vous mettre à niveau en premier ou en dernier ?

## Autorisations

Analytics Inventory est disponible pour les utilisateurs disposant de privilèges d&#39;administrateur de produit Adobe Analytics dans [Adobe Admin Console](/help/admin/admin-console/admin-roles-in-analytics.md).

## Accéder à l’inventaire Analytics

1. Cliquez sur **[!UICONTROL Inventaire Analytics]** dans le menu **[!UICONTROL Admin]**. Ou accédez à **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Inventaire Analytics]**.

![Analytics-Inventory-menu](assets/an-inventory-menu.png)

1. L’écran principal affiche un inventaire complet de votre environnement Adobe Analytics :

   ![Écran d’inventaire principal](assets/an_inventory.png)

   Plus précisément, cet écran affiche :

   * Nombre total de projets Analysis Workspace et Carte de performance mobile qui sont actifs sous cette organisation, pour tous les utilisateurs.
   * Nombre total de segments et de mesures calculées actifs dans cette organisation, pour tous les utilisateurs et utilisatrices.
   * Nombre total de suites de rapports de base qui ont été définies. Les suites de rapports virtuelles ne sont pas incluses.
   * Si la fonctionnalité Media Analytics est active et, le cas échéant, dans quel mode.
   * Nombre total d’utilisateurs définis dans cette organisation.


## Composants {#components}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-components"
>title="Composants"
>abstract="Cette section indique le nombre de projets, de segments et de mesures calculées qui existent dans votre environnement Adobe Analytics. Les projets et composants peuvent être migrés vers Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

Dans cette version initiale, vous pouvez voir des chiffres d’inventaire récapitulatifs pour les projets, les segments et les mesures calculées Workspace. Les versions suivantes vous permettront d’analyser ces composants.

## Configuration et collecte de données {#data-config}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-data-config"
>title="Configuration et collecte de données"
>abstract="Cette section indique le nombre de suites de rapports dans votre environnement Adobe Analytics, ainsi que votre accès aux services de médias en streaming."

<!-- markdownlint-enable MD034 -->

### Suites de rapports

La vue Suites de rapports affiche toutes les suites de rapports définies sous une organisation. Il permet de répondre aux questions suivantes :

* Quelles suites de rapports ont reçu le plus d’accès au cours des 90 derniers jours ?
* Quelles suites de rapports n’ont reçu aucun accès au cours des 90 derniers jours ?
* Quelles suites de rapports ont le plus grand nombre de dimensions définies ?
* Quelles suites de rapports ont le plus grand nombre de mesures définies ?

Les réponses à ces questions vous donneront une idée précise des suites de rapports les mieux adaptées à la migration.

>[!NOTE]
>
>Ce tableau se remplit lentement, une valeur de cellule à la fois.


1. Pour analyser les suites de rapports, accédez à **[!UICONTROL Configuration et collecte des données]** > **[!UICONTROL Suites de rapports]** et cliquez sur **[!UICONTROL Analyser]**.

   ![Liste des suites de rapports](assets/an_inv_rs.png)

   | Élément | Description |
   | --- | --- |
   | Nom | Nom de la suite de rapports |
   | ID | Identifiant de suite de rapports (rsid). Indique un ID unique pouvant uniquement contenir des caractères alphanumériques. Une fois créé, il ne peut plus être modifié. Adobe définit le préfixe d’ID requis qui lui aussi ne peut pas être modifié. |
   | Occurrences (90 derniers jours) | La mesure « Occurrences » indique le nombre d’accès pour lesquels une dimension donnée a été définie ou conservée. Combien d’accès cette suite de rapports a-t-elle reçus au cours des 90 derniers jours ? |
   | Mesures | Combien de mesures sont définies dans cette suite de rapports ? |
   | Dimensions | Combien de dimensions sont définies dans cette suite de rapports ? |
   | Analytics for Target (A4T) activé | [Masqué par défaut] Cette suite de rapports est-elle activée pour [Analytics for Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/a4t/a4t) ? |
   | Canaux marketing activés | [Masqué par défaut] Cette suite de rapports est-elle activée pour [Canaux marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) ? |
   | Connecteur source activé | Cette suite de rapports est-elle activée pour le connecteur Adobe Analytics Source [pour les données de suite de rapports](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/adobe-applications/analytics) dans Adobe Experience Platform ? En d’autres termes, cette suite de rapports peut-elle être migrée vers Customer Journey Analytics à l’aide du connecteur Source Analytics ? |
   | Type de calendrier | [Masqué par défaut] Pour plus d&#39;informations, consultez la section [Calendriers personnalisés](/help/admin/tools/manage-rs/edit-settings/general/custom-calendar.md) |

#### Analyse des dimensions

Cet écran fournit une vue détaillée de toutes les dimensions définies pour une suite de rapports spécifique. Dans cette vue, vous pouvez répondre aux questions suivantes :

* Quelles dimensions sont activées pour cette suite de rapports ?
* Quels sont les dix principaux éléments de dimension pour les 90 derniers jours pour cette dimension ?

1. Cliquez sur le lien **[!UICONTROL Dimensions]** sur la page Suite de rapports .

   | Élément | Description |
   | --- | --- |
   | Nom | Nom de la dimension |
   | ID | Identifiant de la dimension. |
   | Type | Type de dimension. Les valeurs possibles sont les suivantes : Conversion, Trafic, Navigation, Sources de trafic, Clients, Date ou des dimensions spécifiques au produit Adobe telles qu’AEM, Audience, Adobe Campaign, Application mobile, etc. |
   | Description | Toutes les dimensions ne comportent pas de descriptions. |
   | Connecteur source activé | Cette dimension est-elle activée pour le connecteur Adobe Analytics Source [pour les données de suite de rapports](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/adobe-applications/analytics) dans Adobe Experience Platform ? En d’autres termes, cette dimension peut-elle être migrée vers Customer Journey Analytics à l’aide du connecteur Source Analytics ? |

1. Déterminez les dimensions pertinentes pour la migration vers CJA.


#### Analyse des mesures

Cet écran fournit une vue détaillée de toutes les mesures définies pour une suite de rapports spécifique. Dans cette vue, vous pouvez répondre aux questions suivantes :

* Quelles mesures sont activées pour cette suite de rapports ?
* Quelles sont les dix principales mesures des 90 derniers jours ?

1. Cliquez sur le lien **[!UICONTROL Mesures]** sur la page Suite de rapports .


   | Élément | Description |
   | --- | --- |
   | Nom | Nom de la mesure |
   | ID | Identifiant de la mesure. |
   | Type | Type de mesure. Les valeurs possibles sont les suivantes : Conversion, Trafic, Navigation, Sources de trafic, Clients, Date ou des dimensions spécifiques au produit Adobe telles qu’AEM, Audience, Adobe Campaign, Application mobile, etc. |
   | Description | Toutes les dimensions ne comportent pas de descriptions. |
   | Connecteur source activé | Cette mesure est-elle activée pour le connecteur Adobe Analytics Source [pour les données de suite de rapports](https://experienceleague.adobe.com/fr/docs/experience-platform/sources/connectors/adobe-applications/analytics) dans Adobe Experience Platform ? En d’autres termes, cette mesure peut-elle être migrée vers Customer Journey Analytics à l’aide du connecteur Source Analytics ? |

1. Déterminez les mesures pertinentes pour la migration vers CJA.

### Exporter dans un fichier CSV

1. Pour exporter la liste des suites de rapports, des dimensions ou des mesures vers un fichier .csv, cliquez sur **[!UICONTROL Exporter au format CSV]**.

1. Le fichier .csv s’affiche dans votre dossier Téléchargements.

1. Ouvrez-le et enregistrez-le avec une feuille de calcul sur votre appareil.

>[!NOTE]
>
>Les éléments et les colonnes filtrés ne sont pas exportés vers le fichier .csv.


### Filtrer, rechercher, classer et parcourir

* Vous pouvez effectuer une recherche dans le tableau.
* Dans le rail de gauche, cliquez sur l’icône Filtrer pour filtrer par « Type ». Ou cliquez sur **[!UICONTROL Masquer le filtre]**.
* Vous pouvez classer toutes les colonnes par ordre croissant/décroissant (classement d’une seule colonne uniquement).
* Vous pouvez cliquer sur des éléments dans le chemin de navigation pour accéder à un autre écran.

## Gestion des utilisateurs et utilisatrices {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="Gestion des utilisateurs et utilisatrices"
>abstract="Cette section indique le nombre d’utilisateurs et d’utilisatrices dans votre environnement Adobe Analytics."

<!-- markdownlint-enable MD034 -->

User Management sera disponible dans une version ultérieure de l’inventaire Analytics.

## Migration des composants

Grâce à la [ Migration des composants ](/help/admin/tools/component-migration/component-migration.md), les administrateurs et administratrices d’Adobe Analytics peuvent migrer des projets Analytics et leurs composants associés vers Customer Journey Analytics.

Le processus de migration comprend :

* La recréation de projets Adobe Analytics dans Customer Journey Analytics.

* Le mappage des dimensions et des mesures des suites de rapports Adobe Analytics à des dimensions et des mesures dans les vues de données de Customer Journey Analytics.