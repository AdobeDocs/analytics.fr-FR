---
description: Les classifications numériques 2 disposent de mesures souples et personnalisées que vous pouvez importer dans Adobe Experience Cloud via l’importateur.
subtopic: Classifications
title: Classifications numériques 2 - Aperçu
topic: Admin tools
uuid: cbea7cd1-3a92-4e9d-b671-646e9add1ee6
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Classifications numériques 2 - Aperçu

Les classifications numériques 2 disposent de mesures souples et personnalisées que vous pouvez importer dans Adobe Experience Cloud via l’importateur.

>[!IMPORTANT]
>
>La possibilité d’importer des classifications numériques 2 et des classifications activées par date a été supprimée du code base. Cette modification prendra effet lors de la version de maintenance de juillet 2019. S’il y a des colonnes numériques ou des colonnes activées par date dans le fichier d’importation, ces cellules seront ignorées et les autres données de ce fichier seront importées normalement. Les classifications existantes peuvent toujours être exportées par le biais du workflow de classification standard et sont toujours disponibles dans les rapports.

>[!NOTE] Dans la version de maintenance du 10 mai 2018 d’Analytics, Adobe a commencé à limiter les fonctionnalités des classifications activées par date et numériques. Ces types de classifications ont été supprimés des interfaces Administration et Importateur de classifications. Aucune nouvelle classification numérique et à date d’activation ne peut être ajoutée. Il sera possible de continuer à gérer les classifications actuelles (les transférer, les supprimer) par l’intermédiaire des processus de classification standard et elles resteront disponibles dans le reporting.

Les classifications numériques 2 sont couramment utilisées pour les variables numériques qui changent au fil du temps pour différents articles, comme le coût des marchandises vendues. Dans l’administration, vous pouvez créer des classifications sur la [!UICONTROL Conversion Classification] page, puis utiliser l’importateur pour exporter un fichier, apporter des modifications, puis réimporter le fichier dans Adobe. Après avoir importé les données, vous pouvez utiliser les classifications numériques lors de la création de mesures calculées.

>[!IMPORTANT]
>
>Les fonctionnalités Analysis Workspace et Ad Hoc Analysis ne prennent pas en charge les classifications Numérique 2.

Le tableau suivant illustre les différences entre les types de classification :

| FONCTIONNALITÉ | TEXTE | NUMERIQUE 1.0 | NUMERIQUE 2.0 |
|---|---|---|---|
| S’affiche sous forme de rapport | Oui | Non | Non |
| Peut être utilisé comme mesure | Non | Oui | Oui |
| Peut être créé à partir du rapport de base | Oui | Non | Oui |
| Calculé en fonction des  du | Non | Oui | Oui |
| Plusieurs lignes par clé | Non | Non | Oui |
| Peut avoir des valeurs différentes pour des périodes différentes | Non | Non | Oui |
| Peut être utilisé dans les mesures calculées | Non | Oui | Oui |

