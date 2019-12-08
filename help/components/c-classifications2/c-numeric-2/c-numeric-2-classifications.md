---
description: Les classifications numériques 2 disposent de mesures souples et personnalisées que vous pouvez importer dans Adobe Experience Cloud via l’importateur.
subtopic: Classifications
title: Classifications numériques 2 - Aperçu
topic: Admin tools
uuid: cbea7cd1-3a92-4e9d-b671-646e9add1ee6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Classifications numériques 2 - Aperçu

Les classifications numériques 2 disposent de mesures souples et personnalisées que vous pouvez importer dans Adobe Experience Cloud via l’importateur.

>[!IMPORTANT]
>
>La possibilité d’importer des classifications numériques 2 et des classifications activées par date a été supprimée du code base. Cette modification prendra effet lors de la version de maintenance de juillet 2019. S’il y a des colonnes numériques ou des colonnes activées par date dans le fichier d’importation, ces cellules seront ignorées et les autres données de ce fichier seront importées normalement. Les classifications existantes peuvent toujours être exportées par un workflow de classification standard et continuent à être disponibles dans les rapports.

> [!NOTE] Dans la version de maintenance du 10 mai 2018 d’Analytics, Adobe a commencé à limiter les fonctionnalités des classifications activées par date et numériques. Ces types de classifications ont été supprimés des interfaces Administration et Importateur de classifications. Il n’est plus possible d’ajouter de nouvelles classifications numériques et activées par date. Il sera possible de continuer à gérer les classifications actuelles (les transférer, les supprimer) par l’intermédiaire des processus de classification standard et elles resteront disponibles dans le reporting.

Elles sont couramment utilisées lorsque les variables numériques de différents articles changent de temps à autre, comme les valeurs de coût des marchandises vendues. L’administration vous permet de créer des classifications sur la page [!UICONTROL Classification des conversions], puis d’utiliser l’importateur pour exporter un fichier, apporter des modifications et procéder à la réimportation dans Adobe. Une fois les données importées, vous pouvez utiliser les classifications numériques lors de la création des mesures calculées.

>[!IMPORTANT]
>
>Les fonctionnalités Analysis Workspace et Ad Hoc Analysis ne prennent pas en charge les classifications Numérique 2.

Le tableau suivant montre les différences entre les types de classifications :

| FONCTIONNALITÉ | TEXTE | NUMÉRIQUE 1.0 | NUMÉRIQUE 2.0 |
|---|---|---|---|
| S’affiche sous forme de rapport | Oui | Non | Non |
| Peut être utilisée comme mesure | Non | Oui | Oui |
| Peut être créée à partir du rapport de base | Oui | Non | Oui |
| Calculée en fonction des événements | Non | Oui | Oui |
| Plusieurs lignes par clé | Non | Non | Oui |
| Peut contenir des valeurs différentes pour différentes périodes | Non | Non | Oui |
| Peut être utilisée dans les mesures calculées | Non | Oui | Oui |

