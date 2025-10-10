---
description: Tous les rapports marqués d’un signet et rapports de tableau de bord sont désormais répertoriés en tant que dimensions à l’étape 1 de l’Assistant Requête et peuvent être importés en tant que requêtes Report Builder.
title: Importation de rapports marqués d’un signet et de mini-rapports de tableau de bord
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 65%

---

# Importation de rapports marqués d’un signet et de mini-rapports de tableau de bord

{{legacy-arb}}

Tous les rapports marqués d’un signet et rapports de tableau de bord sont désormais répertoriés en tant que dimensions à l’étape 1 de l’Assistant Requête et peuvent être importés en tant que requêtes Report Builder.

Lorsque vous sélectionnez un rapport mis en signet, l’Assistant Requête remplit toutes les dimensions et mesures qui définissent ce rapport mis en signet. La période, la granularité et le segment sélectionné sont également mis à jour en fonction du signet sélectionné.

Voici la façon dont l’étape 1 de l’Assistant Requête présente un tableau de bord et ses mini-rapports :

![Capture d’écran montrant l’étape 1 de 2 de l’Assistant Requête, avec la mise en surbrillance Récupérer vos tableaux de bord et Récupérer vos signets.](assets/import_dashboard_reportlet.png)

Lorsque vous cliquez sur **[!UICONTROL Récupérer vos tableaux de bord]** ou **[!UICONTROL Récupérer vos signets]**, les données des tableaux de bord et signets existants sont récupérées et collées dans la feuille de calcul.

>[!NOTE]
>
>Seules les données sont importées. En conséquence, si le signet comporte un graphique, ou si le petit rapport de tableau de bord n’est composé que d’un seul graphique, seules les données utilisées pour remplir le graphique sont importées.

Une fois que vous avez créé une requête en important un mini-rapport de tableau de bord (ou un signet), la requête est alors associée à la dimension principale du mini-rapport (ou signet). En conséquence, si vous modifiez la requête, l’arborescence ne sélectionne plus le nœud d’arborescence du mini-rapport de tableau de bord (ou nœud du signet) mais la dimension principale.

