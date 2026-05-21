---
description: Tous les rapports marqués d’un signet et rapports de tableau de bord sont désormais répertoriés en tant que dimensions à l’étape 1 de l’Assistant Requête et peuvent être importés en tant que requêtes Report Builder.
title: Importation de rapports marqués d’un signet et de mini-rapports de tableau de bord
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
TQID: https://experienceleague.adobe.com/dnOYs7eOvv15K73EPrfRegz1vH9-B5p8xI8d86vPYe4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 241
ht-degree: 18%

---

# Importation de rapports marqués d’un signet et de mini-rapports de tableau de bord

{{legacy-arb}}

Tous les rapports marqués d’un signet et rapports de tableau de bord sont désormais répertoriés en tant que dimensions à l’étape 1 de l’Assistant Requête et peuvent être importés en tant que requêtes Report Builder.

Lorsque vous sélectionnez un rapport marqué d’un signet, l’Assistant Requête renseigne toutes les dimensions et mesures qui définissent ce rapport. La période, la granularité et le segment sélectionné sont également mis à jour en fonction du signet sélectionné.

Voici comment l’étape 1 de l’Assistant Requête affiche un tableau de bord et ses petits rapports :

![Capture d’écran montrant l’étape 1 de 2 de l’Assistant Requête, avec la mise en surbrillance Récupérer vos tableaux de bord et Récupérer vos signets.](assets/import_dashboard_reportlet.png)

Lorsque vous cliquez sur **[!UICONTROL Récupérer vos tableaux de bord]** ou **[!UICONTROL Récupérer vos signets]**, les données de votre tableau de bord et/ou de votre signet existant sont récupérées et collées dans la feuille de calcul.

>[!NOTE]
>
>Seules les données sont importées. En conséquence, si le signet comporte un graphique, ou si le petit rapport de tableau de bord n’est composé que d’un seul graphique, seules les données utilisées pour remplir le graphique sont importées.

Une fois que vous avez créé une requête en important un petit rapport de tableau de bord (ou un signet), la requête est associée à la dimension principale du petit rapport (ou du signet). Par conséquent, si vous modifiez la requête, l’arborescence ne sélectionne plus le nœud d’arborescence du petit rapport de tableau de bord (ou le nœud de signet) : elle sélectionne plutôt sa dimension principale.

