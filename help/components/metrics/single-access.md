---
title: Accès unique
description: Le nombre de fois qu’un élément de dimension n’a pas changé au cours d’une visite.
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 15%

---

# Accès unique

La **[!UICONTROL Accès unique]** [mesure](overview.md) indique le nombre de visites pour lesquelles la dimension de rapport applicable ne contenait qu’une seule valeur pour une visite complète. Il s’agit de la version plus large et spécifique aux dimensions de [[!UICONTROL Visites sur une seule page]](single-page-visits.md). Cette mesure s’avère utile dans le contexte de toute dimension pour laquelle vous souhaitez afficher la valeur d’une dimension lorsqu’elle a été définie une seule fois lors d’une visite.

## Méthode de calcul de cette mesure

La définition de cette mesure dépend du paramètre du projet [[!UICONTROL Compter les instances répétées]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings) :

* **Compter les instances répétées activées** : compte les visites pour lesquelles la dimension contient exactement une valeur par visite. Si la dimension persiste, elle n’est plus qualifiée d’accès unique.
* **Compter les instances répétées désactivées** : compte les visites pour lesquelles la dimension contient une valeur unique. Vous pouvez définir l’élément de dimension sur la même valeur plusieurs fois ou le faire persister et qu’il soit toujours comptabilisé comme un accès unique.

Quel que soit « [!UICONTROL Compter les instances répétées] », la visite n’est plus qualifiée d’accès unique si la dimension passe à une seconde valeur unique. Les appels de suivi des liens sont inclus dans ce calcul si la dimension y est définie.

## Différence entre « [!UICONTROL &#x200B; Accès unique &#x200B;] » et « [!UICONTROL &#x200B; Visite sur une seule page &#x200B;] »

Dans le contexte de la dimension [[!UICONTROL Page]](../dimensions/page.md), « [!UICONTROL Accès unique] » et « [!UICONTROL Visites sur une seule page] » sont toujours exactement identiques, quel que soit le paramètre du projet « [!UICONTROL Compter les instances répétées] ». Des différences apparaissent lorsque vous utilisez d’autres dimensions.

* **[!UICONTROL Accès unique]** : affiche le nombre de visites pour lesquelles l’élément de dimension donné était présent pour un seul accès. Il est lié à la dimension que vous utilisez dans votre projet.
* **[!UICONTROL Visite sur une seule page]** : affiche le nombre de visites pour lesquelles la dimension « [!UICONTROL Page] » était présente pour un seul accès. Même si vous utilisez une autre dimension dans votre rapport, celle-ci comptabilise toujours les visites qui contiennent un seul élément de dimension « [!UICONTROL Page] » unique.

Si l’option [[!UICONTROL &#x200B; Compter les instances répétées &#x200B;]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings) est désactivée, les définitions de mesures changent légèrement :

* **Accès unique** : affiche le nombre de visites pour lesquelles l’élément de dimension donné n’a pas été modifié pour l’ensemble de la visite.
* **Visite sur une seule page** : indique le nombre de visites pour lesquelles la dimension « [!UICONTROL Page] » n’a pas été modifiée pour l’ensemble de la visite.

Prenons l’exemple suivant de visites à deux accès. La dimension de votre rapport est [[!UICONTROL section Site]](../dimensions/site-section.md) et l’option « [!UICONTROL Compter les instances répétées] » est désactivée.

* Un visiteur accède à deux pages, mais elles se trouvent toutes deux dans la même section du site. Comme la section du site est restée la même tout au long de la visite, elle est comptabilisée comme un accès unique. Elle n’est pas comptabilisée comme une visite sur une seule page, car la visite contient plusieurs éléments de dimension [!UICONTROL Page] uniques.
* Un visiteur accède à deux pages dans différentes sections du site, mais il se trouve que les deux pages portent le même nom. La visite n’est pas comptabilisée comme un accès unique, car il existait deux valeurs de section de site uniques. Cela compte comme une seule visite de page, car il y avait un seul élément de dimension [!UICONTROL Page] unique.
