---
description: Data Warehouse fait référence à la copie de données Analytics pour les rapports de stockage et personnalisés, que vous pouvez exécuter en filtrant les données. Vous pouvez demander des rapports qui présentent un niveau avancé de relations entre les données brutes, en fonction de vos questions. Les rapports d’entrepôt de données sont envoyés par e-mail ou envoyés à un fournisseur de stockage dans le cloud. Leur traitement peut prendre jusqu’à 72 heures. La durée de traitement dépend de la complexité de la requête et de la quantité de données demandées.
title: Data Warehouse - Aperçu
feature: Data Warehouse
uuid: 768557dd-1644-4ce6-bfc2-8c46dd6e1cd1
exl-id: 6a051d53-397b-4a55-9cca-1c83b31c9448
source-git-commit: 3af2cca02675e424b3f704a95d46de92886a88d8
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 100%

---

# Data Warehouse - Aperçu

Data Warehouse vous permet de copier les données Adobe Analytics pour le stockage et la création de rapports personnalisés, que vous pouvez exécuter en filtrant les données.

## Vue d’ensemble des rapports

Les rapports Data Warehouse peuvent afficher des relations de données avancées à partir de données brutes en fonction de vos questions. Ils peuvent inclure un nombre illimité de lignes dans une seule requête (pour des rapports individuels, planifiés et téléchargés).

>[!NOTE]
>
>Data Warehouse consigne la première valeur rencontrée dans la période de création du rapport.

>[!IMPORTANT]
>
>Lors de la segmentation des valeurs classifiées, Analysis Workspace et Data Warehouse traitent différemment les valeurs « non spécifiées ». Dans Workspace, « Non spécifié » fait référence à des valeurs qui ne sont pas classées, tandis que dans Data Warehouse, cela fait référence à des valeurs que vous avez classées comme « Non spécifiées ».

## Vue d’ensemble de la diffusion

Les rapports Data Warehouse sont envoyés par e-mail ou envoyés à un fournisseur de stockage dans le cloud. Leur traitement peut prendre jusqu’à 72 heures. La durée de traitement dépend de la complexité de la requête et de la quantité de données demandées.

Data Warehouse compresse automatiquement les fichiers de plus de 1 Mo. La taille totale des pièces jointes d’un courrier électronique ne peut pas dépasser 10 Mo.

## Accéder à

Adobe active Data Warehouse pour les seuls utilisateurs de niveau administrateur, et ce, pour des suites de rapports spécifiques. (Data Warehouse peut être activée pour les suites de rapports globales et secondaires, mais pas pour les suites de rapports de cumul.) L’administrateur peut créer un groupe ayant accès à Data Warehouse, puis y associer des utilisateurs qui ne sont pas administrateurs.

Consultez [Gestion des autorisations Data Warehouse](/help/export/data-warehouse/t-dw-group.md).

## Créer une requête Data Warehouse

Pour plus d’informations sur la création d’une requête Data Warehouse, consultez [Création d’une requête Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

## Gérer les requêtes Data Warehouse

Pour plus d’informations sur la gestion des requêtes Data Warehouse, consultez [Gestion des requêtes Data Warehouse](/help/export/data-warehouse/data-warehouse-requests-manage.md).

## FAQ

Pour obtenir la liste des questions fréquemment posées, consultez [FAQ sur Data Warehouse](/help/export/data-warehouse/faq.md).