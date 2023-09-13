---
description: Data Warehouse fait référence à la copie de données Analytics pour les rapports de stockage et personnalisés, que vous pouvez exécuter en filtrant les données. Vous pouvez demander des rapports qui présentent un niveau avancé de relations entre les données brutes, en fonction de vos questions. Les rapports de l’entrepôt de données sont envoyés par courrier électronique ou envoyés à un fournisseur de stockage dans le cloud, et leur traitement peut prendre jusqu’à 72 heures. La durée de traitement dépend de la complexité de la requête et de la quantité de données demandées.
title: Data Warehouse - Aperçu
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 58%

---

# Data Warehouse - Aperçu

Data Warehouse vous permet de copier des données Adobe Analytics pour les stocker et créer des rapports personnalisés, que vous pouvez exécuter en filtrant les données.

## Rapports - Aperçu

Les rapports Data Warehouse peuvent afficher des relations avancées entre les données brutes, en fonction de vos questions. Elles peuvent inclure un nombre illimité de lignes dans une seule requête (pour les rapports individuels, planifiés et téléchargés).

>[!NOTE]
>
>Data Warehouse consigne la première valeur rencontrée dans la période de création du rapport.

>[!IMPORTANT]
>
>Lors de la segmentation des valeurs classifiées, Analysis Workspace et Data Warehouse traitent différemment les valeurs « non spécifiées ». Dans Workspace, « Non spécifié » fait référence à des valeurs qui ne sont pas classées, tandis que dans Data Warehouse, cela fait référence à des valeurs que vous avez classées comme « Non spécifiées ».

## Présentation de la diffusion

Les rapports du Data Warehouse sont envoyés par courrier électronique ou envoyés à un fournisseur de stockage dans le cloud, et leur traitement peut prendre jusqu’à 72 heures. La durée de traitement dépend de la complexité de la requête et de la quantité de données demandées.

Data Warehouse compresse automatiquement les fichiers de plus de 1 Mo. La taille totale des pièces jointes d’un courrier électronique ne peut pas dépasser 10 Mo.

## Accès

Adobe active Data Warehouse pour les seuls utilisateurs de niveau administrateur, et ce, pour des suites de rapports spécifiques. (Data Warehouse peut être activée pour les suites de rapports globales et secondaires, mais pas pour les suites de rapports de cumul.) L’administrateur peut créer un groupe ayant accès à Data Warehouse, puis y associer des utilisateurs qui ne sont pas administrateurs.

Voir [Gestion des autorisations de Data Warehouse](/help/export/data-warehouse/t-dw-group.md).

## Créer une demande dans Data Warehouse

Pour plus d’informations sur la création d’une requête de Data Warehouse, voir [Création d’une requête de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

## Gérer les demandes de Data Warehouse

Pour plus d’informations sur la gestion des requêtes de Data Warehouse, voir [Gestion des requêtes de Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

## FAQ

Pour obtenir la liste des questions fréquemment posées, voir [FAQ sur Data Warehouse](/help/export/data-warehouse/faq.md).