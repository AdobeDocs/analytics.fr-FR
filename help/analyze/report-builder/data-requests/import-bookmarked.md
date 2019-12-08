---
description: Tous les rapports mis en signet et de tableau de bord sont désormais répertoriés en tant que dimensions à l’étape 1 de l’Assistant Requête et peuvent être importés en tant que requêtes du Créateur de rapports.
title: Importation de rapports marqués d’un signet et de mini-rapports de tableau de bord
topic: Report builder
uuid: 0fdbdb2e-5db7-4f64-b571-23482ba3606d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Importation de rapports marqués d’un signet et de mini-rapports de tableau de bord

Tous les rapports mis en signet et de tableau de bord sont désormais répertoriés en tant que dimensions à l’étape 1 de l’Assistant Requête et peuvent être importés en tant que requêtes du Créateur de rapports.

Lorsque vous sélectionnez un rapport mis en signet, l’Assistant Requête remplit toutes les dimensions et mesures qui définissent ce rapport mis en signet. La période, la granularité et le segment sélectionné sont également mis à jour selon le signet choisi..

Voici la façon dont l’étape 1 de l’Assistant Requête présente un tableau de bord et ses mini-rapports :

![](assets/import_dashboard_reportlet.png)

When you click **[!UICONTROL Retrieve your Dashboards]** or **[!UICONTROL Retrieve your Bookmarks]**, your existing dashboard and/or bookmark data is retrieved and pasted in the worksheet.

> [!NOTE] Dans le créateur de rapports, la liste des tableaux de bord et des signets disponibles est limitée à l’utilisateur, mais aussi à ceux qui s’appliquent à la suite de rapports sélectionnée à l’étape 1 de l’assistant. Par comparaison, dans les rapports et analyses marketing, vous avez accès à tous les signets et tableaux de bord à votre disposition, quelles que soient les suites de rapports utilisées dans ces tableaux de bord et signets.

> [!NOTE] Seules les données sont importées. Par conséquent, si le signet contient un graphique ou si le mini-rapport du tableau de bord se compose uniquement d’un graphique, seules les données utilisées pour remplir le graphique sont importées.

Une fois que vous avez créé une requête en important un mini-rapport de tableau de bord (ou un signet), la requête est alors associée à la dimension principale du mini-rapport (ou signet). En conséquence, si vous modifiez la requête, l’arborescence ne sélectionne plus le nœud d’arborescence du mini-rapport de tableau de bord (ou nœud du signet) mais la dimension principale.

Le signet d’applet importé va définir correctement la suite de rapports, le segment sélectionné, la dimension et les mesures sélectionnées sur les mêmes paramètres que ceux du signet des Rapports et analyses. 

>[!IMPORTANT]
>
>La plage de dates sera définie sur la même plage de dates, mais sous la forme d’une plage de dates statique - même si cette plage de dates était une plage de dates variable dans le signet Rapports et analyses.

