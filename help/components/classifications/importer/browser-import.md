---
description: Vous pouvez importer (télécharger) des données de classification à l’aide du navigateur. Cette méthode limite le téléchargement des données de classification à une seule suite de rapports.
title: Importation navigateur
feature: Classifications
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
TQID: https://experienceleague.adobe.com/iFVW-d9C12dj6TXnUlA3-zVF0oBAWpJwg1JK8LqzF-s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 83%

---

# Importation navigateur (héritée)

{{classification-importer-deprecation}}

Vous pouvez importer (télécharger) des données de classification à l’aide du navigateur. Cette méthode limite le téléchargement des données de classification à une seule suite de rapports.

## Importation navigateur {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

Vous pouvez importer (télécharger) des données de classification à l’aide du navigateur. Cette méthode limite le téléchargement des données de classification à une seule suite de rapports.

**[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**

## Classifications – Importation navigateur – Description des champs {#section_F628C47081DA4026A4D30E3D3454B1DA}

| Élément | Description |
| --- | --- |
| Sélectionner une suite de rapports | Suite de rapports dans laquelle vous souhaitez importer les données de classification. Le fichier de données d’importation doit correspondre au format de l’ensemble de données de la suite de rapports. |
| Données à classer | Jeu de données de réception des classifications. La liste déroulante comprend tous les rapports des suites de rapports qui sont configurés pour les classifications. |
| Sélectionner le fichier à importer | Permet de rechercher le fichier de données d’importation à télécharger.  Remarque : La taille du fichier de téléchargement est limitée à 1 Mo. |
| Remplacer les données en cas de conflit | Remplace automatiquement les données existantes qui entrent en conflit avec les données importées.<br>**Important** : cette option n’est pas disponible pour les suites de rapports activées pour la nouvelle architecture de classification. |
| Télécharger automatiquement le fichier de classification après la fin de l’importation | Télécharge automatiquement un fichier délimité par des tabulations qui représente le jeu de données avec les données de classification nouvellement chargées. Adobe génère automatiquement ce fichier pour vous si l’importation génère des identifiants uniques ou en cas d’erreur.<br>**Important** : cette option n’est pas disponible pour les suites de rapports activées pour la nouvelle architecture de classification. |


## Importer des classifications par le biais du navigateur {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

1. Cliquez sur **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.
1. Cliquez sur **[!UICONTROL Importer un fichier]**.
1. Configurez les champs **[!UICONTROL Importation navigateur]**.
1. Cliquez sur **[!UICONTROL Importer un fichier]**.
1. Vérifiez les messages de traitement dans la fenêtre d’état.
1. (Sous condition) Si vous avez sélectionné **[!UICONTROL Télécharger automatiquement le fichier de classification au terme du téléchargement vers le serveur]**, indiquez où stocker le fichier obtenu une fois l’importation terminée. Notez que cette option n’est pas disponible pour les suites de rapports activées pour la nouvelle architecture de classification.

>Une importation réussie affiche immédiatement les modifications adéquates dans une exportation. Toutefois, les modifications des données dans les rapports peuvent prendre jusqu’à quatre heures pour s’afficher en cas d’importation avec l’option Navigateur (et jusqu’à 24 heures en cas d’importation FTP).
