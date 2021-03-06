---
title: Création d’un ensemble de classifications
description: Champs et descriptions disponibles lors de la création d’un ensemble de classifications
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
source-git-commit: 3b0e2bbe531692f26ed118b1d2adc0b5ed28a9bf
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%

---

# Création d’un ensemble de classifications

Vous pouvez utiliser le Gestionnaire d’ensembles de classifications pour créer un ensemble de classifications.

>[!NOTE]
>
>Cette fonctionnalité est actuellement limitée. Si vous souhaitez y avoir accès, contactez l’Assistance clientèle d’Adobe ou votre gestionnaire de compte, qui pourra transmettre votre demande à l’équipe Classifications pour la mise en service.

**[!UICONTROL Composants]** > **[!UICONTROL Ensembles de classifications]** > **[!UICONTROL Ensembles]** > **[!UICONTROL Ajouter]**

Lors de la création d’un ensemble de classifications, les champs suivants sont disponibles.

* **[!UICONTROL Nom]** : un champ de texte utilisé pour identifier l’ensemble de classifications. Ce champ ne peut pas être modifié lors de la création, mais peut être renommé ultérieurement.
* **[!UICONTROL Nom de la colonne]** : le nom de la dimension de classification que vous souhaitez créer. Ce champ correspond au nom de la dimension utilisé dans Analysis Workspace et au nom de la colonne lors de l’exportation de données de classification.
* **[!UICONTROL Type]** : cases d’option qui indiquent le type de classification. Les classifications principales sont généralement utilisées ; les classifications de recherche représentent des [sous-classifications](../c-sub-classifications.md).
* **[!UICONTROL Abonnements]** : la suite de rapports et la dimension auxquelles cet ensemble de classifications s’applique. La prise en charge de plusieurs suites de rapports est prévue.

![Création d’un ensemble de classifications](../assets/classification-set-create.png)

S’il existe un ensemble de classifications pour une suite de rapports + une variable donnés, la classification est ajoutée au schéma à la place.
