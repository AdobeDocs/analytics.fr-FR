---
description: Remarques particulières concernant lʼutilisation des suites de rapports virtuelles A4T et Adobe Analytics
title: Suites de rapports virtuelles et Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 100%

---

# Suites de rapports virtuelles et Analytics for Target (A4T)

Tenez compte des avertissements suivants lorsque vous utilisez des suites de rapports virtuelles dans le contexte dʼAdobe Target :

* Vous ne pouvez pas envoyer directement des données de Target vers une suite de rapports virtuelle, mais uniquement vers une suite de rapports réelle.
* Vous pouvez créer des rapports sur les activités A4T dans une suite de rapports virtuelle. Toutefois, les données A4T sont limitées aux lignes correspondant au segment de la suite de rapports virtuelle (et à tout autre segment appliqué). Par exemple, si vous avez créé une suite de rapports virtuelle pour vos clients EMEA, les données A4T de cette suite de rapports virtuelle reflètent uniquement les données Target de vos clients EMEA.
* Vous ne pouvez pas publier les segments dʼune suite de rapports virtuelle vers Target pour les activer.
