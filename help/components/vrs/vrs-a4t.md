---
description: 'Remarques spéciales sur l’utilisation des suites de rapports virtuelles A4T et Adobe Analytics '
title: Suites de rapports virtuelles et Analytics pour Target (A4T)
source-git-commit: 6a47ebc58cb36079940cfc4e5cdc80cf99c18a50
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# Suites de rapports virtuelles et Analytics pour Target (A4T)

Tenez compte des avertissements suivants lorsque vous utilisez des suites de rapports virtuelles dans le contexte d’Adobe Target :

* Vous ne pouvez pas envoyer directement des données de Target vers une suite de rapports virtuelle, mais uniquement vers une suite de rapports réelle.
* Vous pouvez créer des rapports sur les activités A4T dans une suite de rapports virtuelle. Toutefois, les données d’A4T sont limitées aux lignes correspondant au segment de la suite de rapports virtuelle (et à tout autre segment appliqué). Par exemple, si vous avez créé une suite de rapports virtuelle pour vos clients EMEA, les données A4T de cette suite de rapports virtuelle reflètent uniquement les données Target de vos clients EMEA.
* Vous ne pouvez pas republier les segments d’une suite de rapports virtuelle vers Target pour activation.