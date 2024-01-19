---
description: Utilisez des répartitions lorsque vous souhaitez obtenir des informations sur la relation entre un segment ou un élément de rapport et d’autres rapports. On parle généralement de « ventilation » d’un rapport en fonction d’un autre rapport.
title: Répartitions
uuid: a49fa18b-f518-4d1a-a4db-793451b427cc
feature: Reports & Analytics Basics
role: User, Admin
exl-id: bc695b30-c5ac-4bb4-90f4-db6dd83c2f30
source-git-commit: a2e69b5f39de3c964381bb5dd5ecd4d9714e9249
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 93%

---

# Répartitions

{{ra-eol}}

Utilisez des répartitions lorsque vous souhaitez obtenir des informations sur la relation entre un segment ou un élément de rapport et d’autres rapports. On parle généralement de « ventilation » d’un rapport en fonction d’un autre rapport.

Prenons l’exemple de la répartition d’un rapport de trafic personnalisé nommé Groupe d’âge, dans lequel vous avez rassemblé les âges des visiteurs du site suite à un sondage. Ce rapport vous permet de voir quelle tranche d’âge est responsable de la majorité du trafic sur votre site. Cependant, si vous avez pris la peine de capturer une information telle que l’âge d’un visiteur, vous voudrez peut-être en savoir plus que les simples pages vues. Vous pouvez donc générer un rapport avec ventilation sur le moteur de recherche utilisé, les mots-clés utilisés ou leur situation géographique. Vous mettez en corrélation le groupe d’âge et le moteur de recherche.

Si vous ventilez un rapport par *`Referrer Type`*, un point de données peut s’afficher pour *`Inside Your Site`*. Cette valeur indique une page de référence qui figure sur la liste des filtres d’URL internes. Reportez-vous à la section [Filtres d’URL internes](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) dans la Référence d’administration.

Vous pouvez ventiler toute variable Analytics (eVar ou prop) en fonction de toute autre variable. Le menu **[!UICONTROL Ventiler en fonction de]** dans le tableau des rapports correspond au menu de création de rapports Analytics standard, ce qui permet de préserver la cohérence.

## Exécution d’un rapport de répartition {#task_F685624830E64C829C8BE6435A107F69}

Pour exécuter un rapport de ventilation :

<!-- 

t_reports_breakdown.xml

 -->

1. Ouvrez un rapport, tel que **[!UICONTROL Analytics]** > **[!UICONTROL Rapports]** > **[!UICONTROL Contenu du site]** > **[!UICONTROL Pages]**.
1. Cliquez sur l’icône **[!UICONTROL Répartir en fonction de]** dans le tableau du rapport.

   Si l’icône **[!UICONTROL Répartir en fonction de]** n’est pas visible, la fonction n’est pas disponible ou pas activée.

   ![](assets/breakdown.png)

   Le menu **[!UICONTROL Ventiler en fonction de]** affiche toutes les options de ventilation disponibles pour le rapport en cours.
