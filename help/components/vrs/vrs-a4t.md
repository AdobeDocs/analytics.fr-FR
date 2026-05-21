---
description: Remarques particulières concernant lʼutilisation des suites de rapports virtuelles A4T et Adobe Analytics
title: Suites de rapports virtuelles et Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
TQID: https://experienceleague.adobe.com/SIJbZiyHFtGFUrlno5-Kov3kDP4QOXREW00jyDsIGFI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 137
ht-degree: 100%

---

# Suites de rapports virtuelles et Analytics for Target (A4T)

Tenez compte des avertissements suivants lorsque vous utilisez des suites de rapports virtuelles dans le contexte dʼAdobe Target :

* Vous ne pouvez pas envoyer directement des données de Target vers une suite de rapports virtuelle, mais uniquement vers une suite de rapports réelle.
* Vous pouvez créer des rapports sur les activités A4T dans une suite de rapports virtuelle. Toutefois, les données A4T sont limitées aux lignes correspondant au segment de la suite de rapports virtuelle (et à tout autre segment appliqué). Par exemple, si vous avez créé une suite de rapports virtuelle pour vos clients EMEA, les données A4T de cette suite de rapports virtuelle reflètent uniquement les données Target de vos clients EMEA.
* Vous ne pouvez pas publier les segments dʼune suite de rapports virtuelle vers Target pour les activer.
