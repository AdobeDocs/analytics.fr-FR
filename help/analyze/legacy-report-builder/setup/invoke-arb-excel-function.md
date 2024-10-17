---
description: Découvrez comment utiliser Microsoft Excel avec des fonctions de Report Builder sans accéder à l’interface utilisateur de Report Builder.
title: Découvrez comment utiliser Microsoft Excel avec des fonctions de Report Builder
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 41%

---

# Utilisation de fonctions de Report Builder avec Microsoft Excel

{{legacy-arb}}

Vous pouvez utiliser des fonctions de Report Builder pour accéder à la fonctionnalité sans accéder à l’interface utilisateur de Report Builder.

Par exemple, pour actualiser automatiquement les requêtes de Report Builder avec des filtres d’entrée basés sur des données extraites d’Excel à partir d’autres sources, utilisez la chaîne RefreshRequestsInCellsRange(..) . Tous les appels sont asynchrones et renvoient immédiatement et n’attendent pas de s’exécuter complètement.

**Conditions**

* Report Builder 5.0 (ou version ultérieure) est requis.

Le tableau suivant répertorie les fonctions exposées.

| Nom de la fonction | Type | Description |
|:---| --- | ---|
| AsyncRefreshAll() | string | Actualise toutes les requêtes du Report Builder présentes dans un classeur. |
| AsyncRefreshRange(string rangeAddressInA1Format) | string | Actualise toutes les requêtes du Report Builder présentes dans l’adresse de plage de cellules spécifiée (une expression string représentant une plage de cellules au format A1, par exemple « Sheet1!A2:A10 »). |
| AsyncRefreshRangeAltTextParam() | string | Actualise toutes les requêtes du Report Builder présentes dans la plage de cellules spécifiée qui est transférée par l’intermédiaire du Texte de remplacement du Contrôle de formulaire MS. |
| AsyncRefreshActiveWorksheet() | string | Actualise toutes les requêtes du Report Builder présentes dans la feuille de calcul active. |
| AsyncRefreshWorksheet(string worksheetName) | string | Actualise toutes les requêtes du Report Builder présentes dans la feuille de calcul indiquée (le nom de la feuille de calcul tel qu’il s’affiche dans l’onglet). |
| AsyncRefreshWorksheetAltTextParam(); | string | Actualise toutes les requêtes du Report Builder présentes dans le nom de feuille de calcul spécifique qui a été transféré par l’intermédiaire du Texte de remplacement du Contrôle de formulaire MS. |
| tring GetLastRunStatus() | string | Renvoie une chaîne qui décrit l’état de l’exécution la plus récente. |

Pour accéder aux fonctions de Report Builder, accédez à **[!UICONTROL Formules]** > **[!UICONTROL Insérer fonction]**. Utilisez le champ de recherche pour rechercher une fonction ou sélectionnez une catégorie afin de répertorier les fonctions de cette catégorie.

![Capture d&#39;écran montrant la fenêtre Insérer une fonction avec la liste de catégories étendue.](assets/arb_functions.png)

## Exemple {#section_034311081C8D4D7AA9275C1435A087CD}

L’exemple suivant montre *Si la valeur de la cellule P5 est textuelle ou est vide, actualisez la plage qui se trouve dans la cellule P9*.

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

## Utilisation de fonctions de Report Builder avec contrôle de format {#section_26123090B5BD49748C8D8ED7A1C5ED84}

Vous pouvez affecter une macro à un contrôle que vous avez créé et ce contrôle peut être une fonction qui actualise une requête de classeur. Par exemple, la fonction AsyncRefreshActiveWorksheet actualise toutes les requêtes d’une feuille de calcul. Cependant, il peut arriver que vous souhaitiez actualiser uniquement certaines requêtes.

1. Définissez le paramètre de macro.
1. Cliquez avec le bouton droit et sélectionnez **[!UICONTROL Affecter une macro]**.
1. Saisissez le nom de la fonction de Report Builder (pas de paramètres ni de parenthèses).

![Capture d&#39;écran de la fenêtre Attribuer une macro.](assets/assign_macro.png)

## Transfert de paramètres à des fonctions de Report Builder à l’aide de la commande de format {#section_ECCA1F4990D244619DFD79138064CEF0}

Deux fonctions qui utilisent un paramètre peuvent être utilisées avec la commande Format. Vous devez utiliser le champ **Texte de remplacement :** :

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string worksheetName)

Transfert de paramètres à des fonctions de Report Builder à l’aide de la commande de format

1. Cliquez avec le bouton droit et sélectionnez **[!UICONTROL Format de contrôle]**.

   ![Capture d&#39;écran montrant le format de commande sélectionné.](assets/format_control.png)

1. Cliquez sur l’onglet **[!UICONTROL Texte de remplacement]**.

   ![Capture d&#39;écran montrant l&#39;onglet Texte de remplacement et le champ Texte de remplacement.](assets/alt_text.png)

1. Sous **[!UICONTROL Texte de remplacement]**, saisissez la plage de cellules que vous souhaitez actualiser.
1. Ouvrez la liste des paramètres de Report Builder sous **[!UICONTROL Formules]** > **[!UICONTROL Insérer fonction]**> **[!UICONTROL Adobe.ReportBuilder.Bridge]**.

1. Sélectionnez une des deux fonctions qui se terminent par AltTextParam et cliquez sur **[!UICONTROL OK]**.
