---
description: Vous pouvez préciser une période en sélectionnant, dans une feuille de calcul, les cellules qui contiennent une requête. Report Builder utilise les informations de période spécifiques dans ces requêtes. Si vous sélectionnez la date d’aujourd’hui, vous verrez des données partielles basées sur l’heure d’exécution de la requête.
title: Dates à partir d’une cellule
uuid: 0d9bf08d-d39d-4f37-94f1-232da0813245
feature: Report Builder
role: User, Admin
exl-id: e10573cc-984e-4202-a797-c2c9bec2af96
TQID: https://experienceleague.adobe.com/9-U5bdrNbEahhtBuJA4ylaXzGEgH01q1z7FBR2w5sPs
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
source-wordcount: 179
ht-degree: 42%

---

# Dates à partir d’une cellule

{{legacy-arb}}

Vous pouvez préciser une période en sélectionnant, dans une feuille de calcul, les cellules qui contiennent une requête. Report Builder utilise les informations de période spécifiques dans ces requêtes. Si vous sélectionnez la date d’aujourd’hui, vous verrez des données partielles basées sur l’heure d’exécution de la requête.

**Pour configurer des dates à partir d’une cellule**

1. Dans la fenêtre [!UICONTROL Assistant Requête : Étape 1], sélectionnez **[!UICONTROL Dates à partir d’une cellule]**.
1. Saisissez les références de cellule dans les champs **[!UICONTROL De]** et **[!UICONTROL À]** ou cliquez sur le sélecteur et sélectionnez les cellules contenant les demandes avec les dates de début et de fin.

   Par exemple, créez une demande du Report Builder en définissant la période sur « hier » et générez la date de la demande dans la même cellule que « aujourd’hui()-1 ».

Voici une liste des formats de date pris en charge :

![Capture d’écran montrant les formats de date pris en charge.](assets/date-formats.png)

