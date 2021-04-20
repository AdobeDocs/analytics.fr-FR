---
title: Macros Visual Basic dans le Report Builder
description: Développez les fonctionnalités des classeurs Excel et du Report Builder à l’aide de VBA.
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 98%

---


# Macros Visual Basic dans le Report Builder

Les macros VBA, également appelées macros Visual Basic, vous permettent de manipuler des classeurs d’une façon impossible avec Microsoft Excel seul. Visual Basic a accès au classeur, à Excel et même à Windows.

Adobe est compatible avec trois méthodes de l’API Report Builder. Assurez-vous que la dernière version en date de Report Builder est installée et connectez-vous avant d’exécuter les macros.

>[!IMPORTANT]
>
>Pour des raisons de sécurité, vous ne pouvez pas planifier un classeur qui contient une macro.

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
