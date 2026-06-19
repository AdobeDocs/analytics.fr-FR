---
title: Adresse IP
description: L’adresse IP à partir de laquelle chaque accès a été envoyé, disponible dans Data Warehouse.
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 108
ht-degree: 17%

---

# Adresse IP

La [dimension](overview.md) « Adresse IP » répertorie l’adresse IP à partir de laquelle chaque accès a été envoyé.

>[!IMPORTANT]
>
>Cette dimension est uniquement disponible dans Data Warehouse.

## Renseignement de cette dimension avec des données

AppMeasurement collecte automatiquement l’adresse IP de l’en-tête HTTP de chaque demande d’image. Il correspond à la colonne `ip` dans les flux de données. Voir [Référence des colonnes de données](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) pour plus d’informations.

Si l’option [!UICONTROL Obscurcissement d’IP] est activée dans les [Paramètres généraux du compte](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) de la suite de rapports, les adresses IP sont obscurcies ou supprimées partout dans Analytics, y compris dans Data Warehouse.

## Éléments de dimension

Les éléments Dimension incluent les adresses IP à partir desquelles les accès ont été envoyés.
