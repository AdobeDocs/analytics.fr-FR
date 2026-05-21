---
description: Découvrez comment utiliser Microsoft Excel avec des fonctions Report Builder sans accéder à l’interface utilisateur de Report Builder.
title: Découvrez comment utiliser Microsoft Excel avec les fonctions Report Builder.
uuid: 5342cc4f-085d-4a2d-a498-38b00a3ef4d3
feature: Report Builder
role: User, Admin
exl-id: b412f2b5-affe-4297-af4b-85e8c6dfd257
TQID: https://experienceleague.adobe.com/cgDjTqGH0KzSrpg66sRfF8Kf81Q-WDwSWJ-OBvJK8DM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 503
ht-degree: 23%

---

# Utilisation des fonctions Report Builder avec Microsoft Excel

{{legacy-arb}}

Vous pouvez utiliser les fonctions Report Builder pour accéder à la fonctionnalité sans accéder à l’interface utilisateur de Report Builder.

Par exemple, pour actualiser automatiquement les requêtes Report Builder avec des filtres d’entrée basés sur les données extraites d’autres sources dans Excel, utilisez la chaîne RefreshRequestsInCellsRange(..) fonction. Tous les appels sont asynchrones et ils reviennent immédiatement sans attendre l’exécution complète.

**Conditions**

* Report Builder 5.0 (ou version ultérieure) est requis.

Le tableau suivant répertorie les fonctions exposées.

| Nom de la fonction | Type | Description |
|:---| --- | ---|
| AsyncRefreshAll() | string | Actualise toutes les requêtes du Report Builder présentes dans un classeur. |
| AsyncRefreshRange(string rangeAddressInA1Format) | string | Actualise toutes les requêtes Report Builder présentes dans l’adresse de plage de cellules spécifiée (une expression de chaîne représentant une plage de cellules au format A1, par exemple « Sheet1!A2:A10 »). |
| AsyncRefreshRangeAltTextParam() | string | Actualise toutes les requêtes du Report Builder présentes dans la plage de cellules spécifiée qui est transférée par l’intermédiaire du Texte de remplacement du Contrôle de formulaire MS. |
| AsyncRefreshActiveWorksheet() | string | Actualise toutes les requêtes du Report Builder présentes dans la feuille de calcul active. |
| AsyncRefreshWorksheet(string worksheetName) | string | Actualise toutes les requêtes du Report Builder présentes dans la feuille de calcul indiquée (le nom de la feuille de calcul tel qu’il s’affiche dans l’onglet). |
| AsyncRefreshWorksheetAltTextParam(); | string | Actualise toutes les requêtes du Report Builder présentes dans le nom de feuille de calcul spécifique qui a été transféré par l’intermédiaire du Texte de remplacement du Contrôle de formulaire MS. |
| chaîne GetLastRunStatus() | string | Renvoie une chaîne qui décrit le statut de la dernière exécution. |

Pour accéder aux fonctions Report Builder, accédez à **[!UICONTROL Formules]** > **[!UICONTROL Insérer une fonction]**. Utilisez le champ de recherche pour rechercher une fonction ou sélectionnez une catégorie pour répertorier les fonctions de cette catégorie.

![Capture d’écran affichant la fenêtre Insérer une fonction avec la liste de catégories développée.](assets/arb_functions.png)

## Exemple {#section_034311081C8D4D7AA9275C1435A087CD}

L&#39;exemple suivant montre *Si la valeur de la cellule P5 est du texte ou est vide, actualisez la plage qui se trouve dans la cellule P9*.

```
=IF(OR(ISTEXT(P5),ISBLANK(P5)),AsyncRefreshRange("P9"),"")
```

## Utilisation des fonctions Report Builder avec le contrôle de format {#section_26123090B5BD49748C8D8ED7A1C5ED84}

Vous pouvez affecter une macro à un contrôle que vous avez créé et ce contrôle peut être une fonction qui actualise une demande de classeur. Par exemple, la fonction AsyncRefreshActiveWorksheet actualisera toutes les demandes d&#39;une feuille de calcul. Cependant, il peut arriver que vous souhaitiez actualiser uniquement certaines requêtes.

1. Définissez le paramètre de macro.
1. Cliquez avec le bouton droit sur le contrôle et sélectionnez **[!UICONTROL Affecter une macro]**.
1. Saisissez le nom de la fonction Report Builder (pas de paramètres ni de parenthèses).

![Capture d’écran affichant la fenêtre Affecter une macro.](assets/assign_macro.png)

## Transmettre des paramètres aux fonctions Report Builder à l’aide du contrôle de format {#section_ECCA1F4990D244619DFD79138064CEF0}

Deux fonctions qui prennent un paramètre peuvent être utilisées avec le contrôle de format. Vous devez utiliser le champ **Texte secondaire:** :

* AsyncRefreshRange(string rangeAddressInA1Format)
* AsyncRefreshWorksheet(string worksheetName)

Pour transmettre des paramètres à des fonctions Report Builder à l’aide du contrôle de format

1. Cliquez avec le bouton droit et sélectionnez **[!UICONTROL Format de contrôle]**.

   ![Capture d’écran affichant le contrôle de format sélectionné.](assets/format_control.png)

1. Cliquez sur l’onglet **[!UICONTROL Texte de remplacement]**.

   ![Capture d’écran affichant l’onglet Texte de remplacement et Texte de remplacement : field.](assets/alt_text.png)

1. Sous **[!UICONTROL Texte secondaire]**, saisissez la plage de cellules à actualiser.
1. Ouvrez la liste des paramètres Report Builder sous **[!UICONTROL Formules]** > **[!UICONTROL Insérer une fonction]**> **[!UICONTROL Adobe.ReportBuilder.Bridge]**.

1. Sélectionnez une des deux fonctions qui se terminent par AltTextParam et cliquez sur **[!UICONTROL OK]**.
