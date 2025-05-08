---
title: Créer un jeu de classifications
description: Champs et descriptions disponibles lors de la création d’un ensemble de classifications.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 8%

---

# Créer un jeu de classifications

Vous pouvez utiliser le gestionnaire des ensembles de classifications pour créer un ensemble de classifications.

**[!UICONTROL Composants]** > **[!UICONTROL Ensembles de classifications]** > **[!UICONTROL Ensembles]** > **[!UICONTROL Ajouter]**

Lors de la création d’un ensemble de classifications, les champs suivants sont disponibles.

* **[!UICONTROL Nom]** : champ de texte utilisé pour identifier l’ensemble de classifications. Ce champ ne peut pas être modifié lors de la création, mais peut être renommé ultérieurement.
* **[!UICONTROL Nom de la colonne]** : le nom de la première dimension de classification que vous souhaitez créer. Ce champ correspond au nom de la dimension utilisé dans Analysis Workspace et au nom de la colonne lors de l’exportation des données de classification. Vous pouvez ajouter d’autres noms de colonne après la création de l’ensemble de classifications.
* **[!UICONTROL Type]** : cases d’option qui indiquent le type de classification.
   * **[!UICONTROL Principal]** : à appliquer aux dimensions collectées dans Analytics. Ils permettent de regrouper (classifier) les valeurs de dimension granulaires dans des niveaux de données plus significatifs. Par exemple, vous pouvez regrouper des mots-clés de recherche interne en catégories de recherche interne, afin de mieux comprendre les thèmes dans vos données de recherche.
   * **[!UICONTROL Recherche]** : Généralement appelée ‘classifications enfants’ ou ‘sous-classifications’, une table de recherche est une classification d’une classification principale. Il s’agit de métadonnées sur une valeur de classification, plutôt que sur la dimension d’origine. Par exemple, la variable Product peut avoir une classification principale « Code couleur ». Une table de recherche de « Nom de la couleur » pourrait ensuite être jointe au « Code de couleur » pour mieux expliquer ce que chaque code signifie.
* **[!UICONTROL Abonnements]** les suites de rapports et les dimensions auxquelles cet ensemble de classifications s’applique. Vous pouvez ajouter plusieurs combinaisons de suites de rapports et de dimensions à un ensemble de classifications.

![Créer un ensemble de classifications](../../assets/classification-set-create.png)

S’il existe un ensemble de classifications pour une suite de rapports + une variable donnés, la classification est ajoutée au schéma à la place. Une combinaison suite de rapports + variable donnée ne peut pas appartenir à plusieurs ensembles de classifications.
