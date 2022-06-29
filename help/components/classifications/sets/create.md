---
title: Créer un jeu de classifications
description: Champs et descriptions disponibles lors de la création d’un jeu de classifications.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Créer un jeu de classifications

Vous pouvez utiliser le Gestionnaire de jeux de classifications pour créer un jeu de classifications.

>[!NOTE]
>
>Cette fonctionnalité est actuellement en version limitée. Si vous souhaitez accéder à cette fonctionnalité, contactez l’Assistance clientèle d’Adobe ou votre gestionnaire de compte, qui peut transmettre votre demande à l’équipe Classifications pour la mise en service.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]** > **[!UICONTROL Visionneuses]** > **[!UICONTROL Ajouter]**

Lors de la création d’un jeu de classifications, les champs suivants sont disponibles.

* **[!UICONTROL Nom]**: Champ de texte utilisé pour identifier le jeu de classifications. Ce champ ne peut pas être modifié lors de sa création, mais peut être renommé ultérieurement.
* **[!UICONTROL Nom de la colonne]**: Nom de la dimension de classification que vous souhaitez créer. Ce champ correspond au nom de la dimension utilisé dans Analysis Workspace et au nom de la colonne lors de l’exportation de données de classification.
* **[!UICONTROL Type]**: Boutons radio indiquant le type de classification. Les classifications Principal sont généralement utilisées ; Les classifications de recherche représentent [Sous-classifications](../c-sub-classifications.md).
* **[!UICONTROL Abonnements]** Suite de rapports et dimension auxquelles ce jeu de classifications s’applique. La prise en charge de plusieurs suites de rapports est prévue.

![Créer un jeu de classifications](../assets/classification-set-create.png)

S’il existe un jeu de classifications pour une suite de rapports + variable donnée, la classification est ajoutée au schéma à la place.
