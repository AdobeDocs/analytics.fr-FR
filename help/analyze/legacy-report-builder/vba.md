---
title: Utilisation des macros Visual Basic en Report Builder
description: Découvrez comment étendre les fonctionnalités des classeurs et des Reports Builder Excel à l’aide de macros VBA.
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 64%

---

# Macros Visual Basic dans le Report Builder

{{legacy-arb}}

Les macros Visual Basic (VBA) contiennent des fonctionnalités qui vous permettent d’actualiser des classeurs Excel. Visual Basic a accès au classeur, Excel et Windows.

Vous devez exécuter la dernière version de Report Builder et vous connecter avant d’exécuter les macros VBA.

>[!IMPORTANT]
>
>Pour des raisons de sécurité, vous ne pouvez pas planifier un classeur qui contient une macro.

Adobe prend en charge trois méthodes d’API de Report Builder.

## `RefreshAllReportBuilderRequests()`

La macro `RefreshAllReportBuilderRequests()` actualise toutes les requêtes de Report Builder dans le classeur actif. Elle commence par appeler le complément COM de Report Builder grâce à son ID de produit, puis elle appelle la commande API `RefreshAllRequests()` :

```vba
Sub RefreshAllReportBuilderRequests()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshAllRequests(ActiveWorkbook)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInActiveWorksheet()`

La macro `RefreshAllReportBuilderRequestsInActiveWorksheet()` actualise toutes les requêtes de Report Builder dans la feuille de calcul active. L’appel API `RefreshWorksheetRequests()` prend un objet de feuille de calcul comme argument. Vous pouvez utiliser cet appel pour toute feuille de calcul contenant des requêtes de Report Builder :

```vba
Sub RefreshAllReportBuilderRequestsInActiveWorksheet()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshWorksheetRequests(ActiveWorkbook.ActiveSheet)
 
End Sub
```

## `RefreshAllReportBuilderRequestsInCellsRange()`

La macro `RefreshAllReportBuilderRequestsInCellsRange()` actualise toutes les requêtes de Report Builder dont les résultats intersectent la plage de cellules spécifiée. La plage de cellules utilisée dans cet exemple pointe vers la plage `B1:B54` de la feuille de calcul « Data » du classeur actif. L’expression de plage est compatible avec toutes les expressions de plage prises en charge par Excel :

```vba
Sub RefreshAllReportBuilderRequestsInCellsRange()
 
 Dim addIn As COMAddIn
 Dim automationObject As Object
 Dim success As String
 Set addIn = Application.COMAddIns("ReportBuilderAddIn.Connect")
 Set automationObject = addIn.Object
 success = automationObject.RefreshRequestsInCellsRange("'Data'!B1:B54")
  
End Sub
```
