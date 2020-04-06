---
description: Cette fonctionnalité intègre un peu plus l’utilisation du Report Builder dans le processus Excel naturel, sans nécessiter d’accéder à l’interface utilisateur du Report Builder.
title: Appel de la fonctionnalité Report Builder depuis les fonctions Microsoft Excel
topic: Report builder
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Appel de la fonctionnalité Report Builder depuis les fonctions Microsoft Excel

Cette fonctionnalité intègre un peu plus l’utilisation du Report Builder dans le processus Excel naturel, sans nécessiter d’accéder à l’interface utilisateur du Report Builder.

Par exemple, vous souhaitez peut-être actualiser automatiquement les requêtes du Report Builder dont le filtre d’entrée est basé sur des données extraites d’Excel provenant d’autres sources. Vous pouvez effectuer cette opération à l’aide de la fonction string RefreshRequestsInCellsRange(..) . Tous les appels sont asynchrones. Ils reviennent immédiatement et n’attendent pas qu’un appel s’exécute complètement.

>[!NOTE] La version 5.0 (ou supérieure) du Report Builder doit être installée pour que cette fonctionnalité fonctionne.

Voici un tableau avec la  des fonctions exposées :

| Nom de la fonction | Description |
|---|---|
| string AsyncRefreshAll() | Actualise toutes les requêtes du Report Builder présentes dans un classeur. |
| chaîne AsyncRefreshRange(chaîne rangeAddressInA1Format) | Actualise toutes les requêtes du Report Builder présentes dans l’adresse de plage de cellules spécifiée (une expression string représentant une plage de cellules au format A1, par exemple « Sheet1!A2:A10 »). |
| string AsyncRefreshRangeAltTextParam() | Actualise toutes les requêtes du Report Builder présentes dans la plage de cellules spécifiée qui est transférée par l’intermédiaire du Texte de remplacement du Contrôle de formulaire MS. |
| string AsyncRefreshActiveWorksheet() | Actualise toutes les requêtes du Report Builder présentes dans la feuille de calcul active. |
| string AsyncRefreshWorksheet(string sheetName) | Actualise toutes les requêtes du Report Builder présentes dans la feuille de calcul indiquée (le nom de la feuille de calcul tel qu’il s’affiche dans l’onglet). |
| string AsyncRefreshWorksheetAltTextParam(); | Actualise toutes les requêtes du Report Builder présentes dans le nom de feuille de calcul spécifique qui a été transféré par l’intermédiaire du Texte de remplacement du Contrôle de formulaire MS. |
| string GetLastRunStatus() | Renvoie une chaîne qui décrit l’état de la dernière exécution. |

Pour accéder à ces fonctions dans le créateur de rapports, sélectionnez [!UICONTROL Formulas] > [!UICONTROL Insert Function]. Au bas du  de l’ de, vous trouverez Adobe.ReportBuilder.Bridge :

![](assets/arb_functions.png)

## Utilisation de ces fonctions dans une formule {#section_034311081C8D4D7AA9275C1435A087CD}

Par exemple, la formule

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

indique &quot;Si la valeur de la cellule P5 est du texte ou est vide, actualisez la plage qui se trouve dans la cellule P9.&quot;

## Utilisation des fonctions du Report Builder avec le format de contrôle {#section_26123090B5BD49748C8D8ED7A1C5ED84}

Vous pouvez maintenant affecter une macro à un contrôle que vous avez créé et ce contrôle peut être une fonction qui actualise une requête de classeur. Par exemple, la fonction AsyncRefreshActiveWorksheet actualise toutes les requêtes d&#39;une feuille de calcul. Cependant, il peut arriver que vous souhaitiez actualiser uniquement certaines requêtes, pas toutes.

1. Définissez le paramètre de macro.
1. Cliquez avec le bouton droit de la souris sur le contrôle et sélectionnez **[!UICONTROL Assign Macro]**.
1. Entrez le nom de la fonction du créateur de rapports (sans paramètre ni parenthèse).

![](assets/assign_macro.png)

## Transfert de paramètres aux fonctions du Report Builder par l’intermédiaire du format de contrôle {#section_ECCA1F4990D244619DFD79138064CEF0}

Les deux fonctions qui utilisent un paramètre peuvent être utilisées avec le contrôle de format, mais uniquement via le champ Texte de remplacement :

* AsyncRefreshRange(chaîne rangeAddressInA1Format)
* AsyncRefreshWorksheet(chaîne sheetName)

1. Cliquez avec le bouton droit de la souris sur le contrôle et sélectionnez **[!UICONTROL Format Control]**.

   ![](assets/format_control.png)

1. Click the [!UICONTROL Alt Text] tab.

   ![](assets/alt_text.png)

1. Sous [!UICONTROL Alternative text], entrez la plage de cellules à actualiser.
1. Ouvrez le  des paramètres du créateur de rapports sous [!UICONTROL Formulas] > [!UICONTROL Insert Function]> [!UICONTROL Adobe.ReportBuilder.Bridge].

1. Sélectionnez une des deux fonctions qui se terminent par AltTextParam et cliquez sur **[!UICONTROL OK]**.

