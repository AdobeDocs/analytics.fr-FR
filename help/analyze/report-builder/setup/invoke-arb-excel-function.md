---
description: Cette fonctionnalité intègre un peu plus l’utilisation du Report Builder dans le processus Excel naturel, sans nécessiter d’accéder à l’interface utilisateur du Report Builder.
title: Appel de la fonctionnalité Report Builder depuis les fonctions Microsoft Excel
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 100%

---

# Appel de la fonctionnalité Report Builder depuis les fonctions Microsoft Excel

Cette fonctionnalité intègre un peu plus l’utilisation du Report Builder dans le processus Excel naturel, sans nécessiter d’accéder à l’interface utilisateur du Report Builder.

Par exemple, vous souhaitez peut-être actualiser automatiquement les requêtes du Report Builder dont le filtre d’entrée est basé sur des données extraites d’Excel provenant d’autres sources. Vous pouvez effectuer cette opération à l’aide de la fonction string RefreshRequestsInCellsRange(..) . Tous les appels sont asynchrones. Ils renvoient immédiatement et n’attendent pas un appel pour s’exécuter entièrement.

>[!NOTE]
>
>La version 5.0 (ou supérieure) du Report Builder doit être installée pour que cette fonctionnalité fonctionne.

Vous trouverez ci-dessous un tableau comportant la liste des fonctions présentées :

| Nom de la fonction | Description |
|---|---|
| string AsyncRefreshAll() | Actualise toutes les requêtes du Report Builder présentes dans un classeur. |
| string AsyncRefreshRange(string rangeAddressInA1Format) | Actualise toutes les requêtes du Report Builder présentes dans l’adresse de plage de cellules spécifiée (une expression string représentant une plage de cellules au format A1, par exemple « Sheet1!A2:A10 »). |
| string AsyncRefreshRangeAltTextParam() | Actualise toutes les requêtes du Report Builder présentes dans la plage de cellules spécifiée qui est transférée par l’intermédiaire du Texte de remplacement du Contrôle de formulaire MS. |
| string AsyncRefreshActiveWorksheet() | Actualise toutes les requêtes du Report Builder présentes dans la feuille de calcul active. |
| string AsyncRefreshWorksheet(string worksheetName) | Actualise toutes les requêtes du Report Builder présentes dans la feuille de calcul indiquée (le nom de la feuille de calcul tel qu’il s’affiche dans l’onglet). |
| string AsyncRefreshWorksheetAltTextParam(); | Actualise toutes les requêtes du Report Builder présentes dans le nom de feuille de calcul spécifique qui a été transféré par l’intermédiaire du Texte de remplacement du Contrôle de formulaire MS. |
| string GetLastRunStatus() | Renvoie une chaîne qui décrit l’état de l’exécution la plus récente. |

Pour accéder à ces fonctions dans le Créateur de rapports, accédez à [!UICONTROL Formules] > [!UICONTROL Insérer fonction]. Dans la partie inférieure de la liste de catégories, vous trouverez Adobe.ReportBuilder.Bridge :

![](assets/arb_functions.png)

## Utilisation de ces fonctions dans une formule {#section_034311081C8D4D7AA9275C1435A087CD}

Par exemple, la formule

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

indique « Si la cellule P5 contient du texte ou est vierge, actualisez la plage se trouvant dans la cellule P9. »

## Utilisation des fonctions du Report Builder avec le format de contrôle {#section_26123090B5BD49748C8D8ED7A1C5ED84}

Vous pouvez à présent affecter une macro à un contrôle que vous avez créé et ce dernier peut être une fonction qui actualise une requête de classeur. Par exemple, la fonction AsyncRefreshActiveWorksheet actualise toutes les requêtes d’une feuille de calcul. Parfois, néanmoins, vous souhaitez n’actualiser que certaines requêtes, pas toutes.

1. Définissez le paramètre de macro.
1. Cliquez avec le bouton droit et sélectionnez **[!UICONTROL Affecter une macro]**.
1. Saisissez le nom de la fonction du Créateur de rapports (sans paramètre ou parenthèse).

![](assets/assign_macro.png)

## Transfert de paramètres aux fonctions du Report Builder par l’intermédiaire du format de contrôle {#section_ECCA1F4990D244619DFD79138064CEF0}

Les deux fonctions qui utilisent un paramètre peuvent être utilisées avec le format de contrôle mais uniquement par l’intermédiaire du champ Texte de remplacement :

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string worksheetName)

1. Cliquez avec le bouton droit et sélectionnez **[!UICONTROL Format de contrôle]**.

   ![](assets/format_control.png)

1. Cliquez sur l’onglet [!UICONTROL Texte de remplacement].

   ![](assets/alt_text.png)

1. Sous [!UICONTROL Texte de remplacement], saisissez la plage de cellules que vous souhaitez actualiser.
1. Ouvrez la liste des paramètres du Créateur de rapports sous [!UICONTROL Formules] > [!UICONTROL Insérer fonction] > [!UICONTROL Adobe.ReportBuilder.Bridge].

1. Sélectionnez une des deux fonctions qui se terminent par AltTextParam et cliquez sur **[!UICONTROL OK]**.
