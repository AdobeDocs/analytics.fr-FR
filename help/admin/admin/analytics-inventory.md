---
description: Utilisation de l’inventaire Analytics
title: Inventaire Analytics
feature: Admin Tools
role: Admin
hide: true
hidefromtoc: true
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: fceb28b7af480e6d87abf09c26f45a7afb2d3270
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 36%

---

# Inventaire Analytics {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Inventaire Analytics"
>abstract="Cette page présente une vue d’ensemble complète de votre environnement Adobe Analytics, y compris le nombre de projets et de composants, les suites de rapports, les utilisateurs et utilisatrices, etc. Ces informations sont particulièrement utiles lorsque vous commencez à vous préparer à la mise à niveau vers Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

L’inventaire Analytics fournit une vue d’ensemble complète de votre environnement Adobe Analytics, y compris le nombre de projets et de composants, les suites de rapports, les utilisateurs, etc. Ces informations sont particulièrement utiles lorsque vous commencez à vous préparer à la mise à niveau vers Customer Journey Analytics.

L’objectif de cette application est de vous aider à répondre aux questions suivantes :

* Pour votre organisation, quelles ressources (telles que les suites de rapports, les segments, les utilisateurs, les projets d’espace de travail, les flux de données, etc.) devez-vous mettre à niveau et quelles ressources pouvez-vous laisser ?

* Une fois que vous avez déterminé la ressource à migrer :

   * Devriez-vous effectuer un nettoyage des ressources avant cette mise à niveau ?

   * Devriez-vous procéder à une consolidation des actifs dans le cadre du processus ?

   * Quelle doit être la séquence de mise à niveau de vos ressources ?

   * Quel groupe de suites de rapports devez-vous mettre à niveau en premier ? dernier ?

## Autorisations

Analytics Inventory est disponible pour les utilisateurs disposant de privilèges d&#39;administrateur de produit Adobe Analytics dans [Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/admin-roles-in-analytics).

## Accéder à l’inventaire Analytics

1. Cliquez sur **[!UICONTROL Inventaire Analytics]** dans le menu **[!UICONTROL Admin]**. Ou accédez à **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Inventaire Analytics]**.

![Analytics-Inventory-menu](assets/an-inventory-menu.png)

1. L’écran principal affiche un inventaire complet de votre environnement Adobe Analytics :

   ![Écran d’inventaire principal](assets/an_inventory.png)

>[!IMPORTANT]
>
>   Dans cette version initiale, vous pouvez voir des chiffres récapitulatifs pour les projets Workspace, les segments, les mesures calculées, les données avancées (Media Analytics) et les utilisateurs. Actuellement, les seuls éléments exploitables sont les suites de rapports.


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
>abstract="Cette section indique le nombre de suites de rapports dans votre environnement Adobe Analytics, ainsi que votre accès aux médias en streaming. "

<!-- markdownlint-enable MD034 -->

### Analyse des suites de rapports

1. Pour analyser les suites de rapports et décider lesquelles migrer, accédez à **[!UICONTROL Configuration et collecte des données]** > **[!UICONTROL Suites de rapports]** et cliquez sur **[!UICONTROL Analyser]**.

   ![Liste des suites de rapports](assets/an_inv_rs.png)

   | Élément | Description |
   | --- | --- |
   | Nom | Nom de la suite de rapports |
   | ID | Identifiant de suite de rapports (rsid). Indique un ID unique pouvant uniquement contenir des caractères alphanumériques. Une fois créé, il ne peut plus être modifié. Adobe définit le préfixe d’ID requis qui lui aussi ne peut pas être modifié. |
   | Occurrences (90 derniers jours) |  |
   | Mesures | How |
   | Dimensions |  |
   | Analytics for Target (A4T) activé |  |
   | Canaux marketing activés |  |
   | Connecteur Source activé | À suivre |
   | Type de calendrier | Pour plus d&#39;informations, voir [Calendriers personnalisés](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/custom-calendar#) |

1. Remarquez que...

### Exporter dans un fichier CSV

1. Pour exporter la liste des suites de rapports vers un fichier .csv, cliquez sur **[!UICONTROL Exporter au format CSV]**.

1. Le fichier .csv s’affiche dans votre dossier Téléchargements.

1. Ouvrez-le et enregistrez-le avec une feuille de calcul sur votre appareil.


## Gestion des utilisateurs et utilisatrices {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="Gestion des utilisateurs et utilisatrices"
>abstract="Cette section indique le nombre d’utilisateurs et d’utilisatrices dans votre environnement Adobe Analytics."

<!-- markdownlint-enable MD034 -->

User Management sera disponible dans une version ultérieure de l’inventaire Analytics.