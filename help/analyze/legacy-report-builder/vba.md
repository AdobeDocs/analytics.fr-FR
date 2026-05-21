---
title: Utilisation des macros Visual Basic dans Report Builder
description: Découvrez comment étendre les fonctionnalités des classeurs Excel et Report Builder à l’aide de macros VBA.
feature: Report Builder
role: User, Admin
exl-id: 0d92bce2-22ae-4b0c-af1d-3d12f2041ddf
TQID: https://experienceleague.adobe.com/RxOpojtJn2vi5uMO8CGzCCm7FcPp4qVwbH-XTEBSRsY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 195
ht-degree: 64%

---

# Macros Visual Basic dans le Report Builder

{{legacy-arb}}

Les macros Visual Basic (VBA) fournissent des fonctionnalités qui vous aident à actualiser les classeurs Excel. Visual Basic a accès au classeur, à Excel et à Windows.

Vous devez exécuter la dernière version de Report Builder et vous connecter avant d&#39;exécuter des macros VBA.

>[!IMPORTANT]
>
>Pour des raisons de sécurité, vous ne pouvez pas planifier un classeur qui contient une macro.

Adobe prend en charge trois méthodes d’API Report Builder.

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
