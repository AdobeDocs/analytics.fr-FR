---
description: Permet aux utilisateurs de niveau administrateur d’afficher et de gérer des rapports planifiés à l’échelle de l’organisation.
title: File d’attente des rapports planifiés
feature: Admin Tools
uuid: 3fcf92d3-a472-465f-ad7a-c48cd9a8238b
exl-id: 7287e6c7-e354-48a0-9343-35dccfc46e63
role: Admin
TQID: https://experienceleague.adobe.com/HL78cbB5NqKCjv4NvZ5OiqjfbwBjI0KAC8hEr8Afd2U
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 319
ht-degree: 53%

---

# File d’attente des rapports planifiés

Permet aux utilisateurs de niveau administrateur d’afficher et de gérer des rapports planifiés à l’échelle de l’organisation.

**[!UICONTROL Analytics]** > **[!UICONTROL Composants]** > **[!UICONTROL Tous les composants]** > **[!UICONTROL Rapports planifiés]**.

Les fonctionnalités de niveau administrateur dans le gestionnaire de rapports programmés incluent :

* L’option [&#x200B; Afficher tous les rapports planifiés &#x200B;](/help/components/scheduled-reports-admin.md#section_3F167CAAEEC24140B476CF95B7402690) dans votre organisation.
* [Fonctionnalités de filtrage avancé](/help/components/scheduled-reports-admin.md#section_206A52A85DE84947AAB3AD082FBF6275) à l’échelle de votre organisation.
* Nouvel onglet [&#x200B; File d’attente des rapports &#x200B;](/help/components/scheduled-reports-admin.md#section_03C866115D354BB182E90BF4D52F1E0B) répertoriant tous les rapports mis en file d’attente pour exécution sur les serveurs de création de rapports.
* Exposition de l’[ID de planification](/help/components/scheduled-reports-admin.md#section_568B70F4228C4229977CB85D2DCD53A1) dans l’interface de file d’attente des rapports.

## Affichage de tous les rapports planifiés {#section_3F167CAAEEC24140B476CF95B7402690}

Dans l’onglet **[!UICONTROL Liste des rapports]**, vous pouvez **[!UICONTROL Afficher tous les rapports planifiés]** de votre organisation en plus de ceux que vous avez personnellement planifiés.

>[!NOTE]
>
>La colonne **[!UICONTROL Nom de rapport]** affiche le nom du rapport planifié et la colonne **[!UICONTROL Nom de fichier]** affiche tout nom de fichier personnalisé défini par vous dans les Options de diffusion avancées. Par conséquent, si vous planifiez plusieurs rapports du même type et que vous spécifiez des noms personnalisés pour chacun d&#39;eux, le Gestionnaire de rapports planifiés affiche plusieurs entrées portant le même nom de rapport, mais avec des noms de fichier différents. En effet, le rapport principal planifié est identique, de sorte que la colonne Nom du rapport aurait les mêmes noms de rapport pour tous les noms de fichier, à l’exception des noms de fichier personnalisés (comme défini).

![](assets/show_all_scheduled_reports.png)

## Fonctionnalités de filtrage avancées {#section_206A52A85DE84947AAB3AD082FBF6275}

Par exemple, si vous souhaitez filtrer selon tous les rapports planifiés par heure, indiquez **[!UICONTROL Fréquence égale toutes les heures]** dans le filtre **[!UICONTROL Avancé]** et cliquez sur **[!UICONTROL Appliquer]** :

![](assets/advanced_filtering_schedl_reports.png)

## File d’attente des rapports {#section_03C866115D354BB182E90BF4D52F1E0B}

Cette file d’attente vous permet de gérer et éventuellement de supprimer tous les rapports planifiés qui la « bouchent ». (En règle générale, les rapports expirent au bout de 4 heures.)

![](assets/scheduled_reports_2.png)

La file d’attente des rapports vous permet également d’« ignorer un rapport planifié une fois ». Cliquez simplement sur l’icône bleue dans la colonne **[!UICONTROL Gérer]**.

## Identifiant de planification {#section_568B70F4228C4229977CB85D2DCD53A1}

L’exposition de l’**[!UICONTROL Identifiant de planification]** dans l’interface de file d’attente des rapports est utile lorsque vous devez contacter le service clientèle d’Adobe pour la résolution d’un problème de rapports planifiés.

![](assets/schedule_id.png)
