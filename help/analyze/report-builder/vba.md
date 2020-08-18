---
title: Macros Visual Basic dans le Report Builder
description: Développez les fonctionnalités des classeurs et des Reports Builder Excel à l’aide de VBA.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# Macros Visual Basic dans le Report Builder

Les macros VBA, également connues sous le nom de macros Visual Basic, vous permettent de manipuler des classeurs de la manière dont Microsoft Excel seul ne peut pas le faire. Visual Basic a accès au classeur, à Excel et même à Windows.

adobe prend en charge trois méthodes d’API de Report Builder. Assurez-vous que la dernière version du créateur de rapports est installée et connectez-vous avant d’exécuter les macros.

>[!IMPORTANT]
>
>Pour des raisons de sécurité, vous ne pouvez pas planifier un classeur qui contient une macro.

## `RefreshAllReportBuilderRequests()`

The `RefreshAllReportBuilderRequests()` macro refreshes all Report Builder requests in the active workbook. Il début en appelant l&#39;Ajoute COM du Report Builder par l&#39;intermédiaire de son ID de produit, puis appelle la commande `RefreshAllRequests()` API :

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

The `RefreshAllReportBuilderRequestsInActiveWorksheet()` macro refreshes all Report Builder requests in the active worksheet. L&#39;appel `RefreshWorksheetRequests()` API prend un objet de feuille de calcul comme argument. Vous pouvez utiliser cet appel pour toute feuille de calcul contenant des requêtes de Report Builder :

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

The `RefreshAllReportBuilderRequestsInCellsRange()` macro refreshes all Report Builder requests whose cell outputs intersect the specified range of cells. La plage de cellules utilisée dans cet exemple pointe vers la plage `B1:B54` de la feuille de calcul &quot;Données&quot; du classeur principal. L&#39;expression de plage prend en charge toutes les expressions de plage Excel prises en charge :

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
