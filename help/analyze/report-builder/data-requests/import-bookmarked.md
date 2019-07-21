---
description: Tous les rapports mis en signet et de tableau de bord sont désormais répertoriés en tant que dimensions à l’étape 1 de l’Assistant Requête et peuvent être importés en tant que requêtes du Créateur de rapports.
seo-description: Tous les rapports mis en signet et de tableau de bord sont désormais répertoriés en tant que dimensions à l’étape 1 de l’Assistant Requête et peuvent être importés en tant que requêtes du Créateur de rapports.
seo-title: Importation de rapports mis en signet et de mini-rapports de tableau de bord
solution: Analytics
title: Importation de rapports mis en signet et de mini-rapports de tableau de bord
topic: Créateur de rapports
uuid: 0 fdbdb 2 e -5 db 7-4 f 64-b 571-23482 ba 3606 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Importation de rapports mis en signet et de mini-rapports de tableau de bord

Tous les rapports mis en signet et de tableau de bord sont désormais répertoriés en tant que dimensions à l’étape 1 de l’Assistant Requête et peuvent être importés en tant que requêtes du Créateur de rapports.

Lorsque vous sélectionnez un rapport mis en signet, l’Assistant Requête remplit toutes les dimensions et mesures qui définissent ce rapport mis en signet. La période, la granularité et le segment sélectionné sont également mis à jour selon le signet choisi..

Voici la façon dont l’étape 1 de l’Assistant Requête présente un tableau de bord et ses mini-rapports :

![](assets/import_dashboard_reportlet.png)

When you click **[!UICONTROL Retrieve your Dashboards]** or **[!UICONTROL Retrieve your Bookmarks]**, your existing dashboard and/or bookmark data is retrieved and pasted in the worksheet.

>[!NOTE]
>
>Dans le créateur de rapports, la liste des tableaux de bord et signets disponibles est limitée à l'utilisateur, mais aussi à ceux qui s'appliquent à la suite de rapports sélectionnée à l'étape 1 de l'assistant. Par comparaison, dans les rapports et analyses marketing, vous avez accès à tous les signets et tableaux de bord à votre disposition, quelles que soient les suites de rapports utilisées dans ces tableaux de bord et signets.

>[!NOTE]
>
>Seules les données sont importées. Par conséquent, si le signet contient un graphique ou si le petit rapport du tableau de bord est composé d'un seul graphique, seules les données utilisées pour remplir le graphique sont importées.

Une fois que vous avez créé une requête en important un mini-rapport de tableau de bord (ou un signet), la requête est alors associée à la dimension principale du mini-rapport (ou signet). En conséquence, si vous modifiez la requête, l’arborescence ne sélectionne plus le nœud d’arborescence du mini-rapport de tableau de bord (ou nœud du signet) mais la dimension principale.

Le signet d’applet importé va définir correctement la suite de rapports, le segment sélectionné, la dimension et les mesures sélectionnées sur les mêmes paramètres que ceux du signet des Rapports et analyses. 

>[!IMPORTANT]
>
>La période est définie sur la même période, mais sous la forme d'une plage de dates statique, même si cette période était une période variable dans le signet Rapports et analyses.

