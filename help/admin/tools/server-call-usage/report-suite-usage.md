---
description: L’onglet Suite de rapports d’utilisation fournit des données d’utilisation du serveur pour chaque suite de rapports pour toutes les sociétés de connexion associées à la société de facturation, pour la période d’utilisation actuelle.
title: Affichage de l’utilisation des suites de rapports
feature: Server Call Usage
exl-id: bedd4ed8-1c8b-45fd-a059-fed88e9fbe73
role: Admin
TQID: https://experienceleague.adobe.com/reCYMlZM7HH2H1ewI6tN6x6Bn4ghaKKyrkXGUzC64-g
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 82%

---

# Affichage de l’utilisation des suites de rapports

L’onglet Suite de rapports d’utilisation fournit des données d’utilisation du serveur pour chaque suite de rapports pour toutes les sociétés de connexion associées à la société de facturation, pour la période d’utilisation actuelle.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Utilisation de l’appel au serveur]** > **[!UICONTROL Suite de rapports d’utilisation]**

>[!IMPORTANT]
>
>Si une suite de rapports n’est pas liée à une organisation CX Enterprise, ses données d’utilisation ne sont pas reflétées dans ce tableau de bord. En outre, un identifiant de facturation peut être lié à plusieurs organisations d’entreprise CX ; il n’existe pas toujours de relation 1:1 entre une organisation et un identifiant de facturation.

Le tableau de bord de la suite de rapports d’utilisation :

* Affiche l&#39;utilisation des appels au serveur de la période d&#39;utilisation actuelle (Tous les appels, Principal, Secondaire, Principal mobile, Secondaire mobile) pour chaque suite de rapports de votre organisation CX Enterprise.
* affiche le pourcentage de l’utilisation générale par catégories d’appels au serveur ;
* est mis à jour quotidiennement ;
* est téléchargeable ;
* vous permet d’accéder à l’interface utilisateur de la **[!UICONTROL Gestion des alertes]**.

![](/help/admin/tools/server-call-usage/assets/report-suite-usage.png)

## Paramètres du tableau de bord {#settings}

| Colonne | Définition |
|--- |--- |
| Nom de la suite de rapports | Le nom convivial de la suite de rapports |
| Tous les appels (% du total) | Tous les appels au serveur effectués durant la période d’utilisation actuelle. |
| Appels principaux (%) | Tous les appels au serveur principal (et leur pourcentage du total) effectués durant la période d’utilisation actuelle. |
| Appels secondaires (%) | Tous les appels au serveur secondaire (et leur pourcentage du total) effectués durant la période d’utilisation actuelle. |
| Principal mobile (%) | Tous les appels au serveur principal mobile (et leur pourcentage du total) effectués durant la période d’utilisation actuelle. |
| Secondaire mobile (%) | Tous les appels au serveur secondaire mobile (et leur pourcentage du total) effectués durant la période d’utilisation actuelle. |

{style="table-layout:auto"}

## Télécharger le rapport d’utilisation {#download}

Cette option vous permet de télécharger les données d’utilisation actuelles, ainsi que les données de périodes antérieures (en remontant jusqu’à janvier 2015). Le rapport est téléchargé au format .cvs.

1. Sélectionnez au moins une suite de rapports.
1. Cliquez sur **[!UICONTROL Télécharger un rapport]**.

   ![](/help/admin/tools/server-call-usage/assets/download_report.png)

| Élément du rapport | Description |
|--- |--- |
| Nom de fichier | Nom codé en dur : rapport d’utilisation `day and time of report creation.csv` |
| Suites de rapports incluses | Toutes les suites de rapports que vous avez sélectionnées sur la page du rapport d’utilisation du serveur sont incluses dans cette liste. |
| Types d’appels inclus | Spécifiez n’importe quelle combinaison entre : Tous les appels (par défaut), Principal, Secondaire, Principal mobile, Principal secondaire. |
| Période | Vous pouvez sélectionner la période d’utilisation actuelle ou indiquer une période spécifique.  Pour définir une période personnalisée, indiquez le début de la période et la fin de la période. <br>**Remarque :** vous ne pouvez pas télécharger des données d’utilisation antérieures à janvier 2015 </br>. |

{style="table-layout:auto"}

1. Cliquez sur **[!UICONTROL Télécharger]**.

Voici une capture d’écran de ce à quoi ressemble le fichier .csv téléchargé. Il comprend une colonne pour l’identifiant de la suite de rapports. L’identifiant de la suite de rapports spécifie un ID unique pouvant uniquement contenir des caractères alphanumériques. Cet identifiant ne peut pas être modifié après la création d’une suite de rapports.

![](/help/admin/tools/server-call-usage/assets/download-usage.png)
