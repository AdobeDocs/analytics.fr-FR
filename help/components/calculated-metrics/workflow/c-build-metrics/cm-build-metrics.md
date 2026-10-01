---
description: Découvrez le créateur de mesures calculées qui fournit une zone de travail dans laquelle faire glisser et déposer des dimensions, des mesures, des segments et des fonctions pour créer des mesures personnalisées en fonction de la logique de hiérarchie des conteneurs, des règles et des opérateurs.
title: Créer des mesures
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
TQID: https://experienceleague.adobe.com/ds8aD51DynOEJ7uYZ5Id-kTng2JPN4nZYuMTaKj-ZvE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6
    internal-label: Workspace projects
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 8badbfc74bdc95a8ab673d4f00fe13e0829e64bb
workflow-type: tm+mt
source-wordcount: '1495'
ht-degree: 99%
---
# Créer des mesures calculées {#build-metrics}

Adobe Analytics fournit une zone de travail où faire glisser et déposer des dimensions, des mesures, des segments et des fonctions permettant de créer des mesures personnalisées en fonction de la logique de hiérarchie des conteneurs, des règles et des opérateurs. Grâce à cet outil de développement intégré, vous pouvez créer et enregistrer des mesures calculées simples ou complexes.

Vous pouvez utiliser le créateur de mesures calculées pour créer ou modifier des mesures calculées. Une fois créées de cette manière, les mesures calculées sont disponibles dans la liste des composants et peuvent ensuite être utilisées dans les projets de l’ensemble de votre organisation. Vous pouvez également créer rapidement une mesure calculée qui n’est disponible que pour le projet dans lequel elle a été créée, comme décrit dans la section [Création de mesures calculées pour un seul projet](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) dans [Mesures](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

[Créer une mesure calculée](../cm-workflow.md) décrit les différentes options disponibles pour créer une mesure calculée.

## Zones du créateur de mesures calculées

La boîte de dialogue du **[!UICONTROL Créateur de mesures calculées]** permet de créer ou de modifier des mesures calculées existantes. La boîte de dialogue s’intitule **[!UICONTROL Nouvelle mesure calculée]** ou **[!UICONTROL Modifier la mesure calculée]** pour les mesures calculées que vous créez ou gérez à partir du [[!UICONTROL gestionnaire de mesures calculées]](../cm-manager.md).

>[!BEGINTABS]

>[!TAB Créateur de mesures calculées]

![Fenêtre de détails des mesures calculées présentant les champs et options décrits dans la section suivante.](assets/calculated-metric-builder.png)

>[!TAB Créer ou modifier une mesure calculée]

![Fenêtre de détails des mesures calculées présentant les champs et options décrits dans la section suivante.](assets/create-edit-calculated-metric.png)

>[!ENDTABS]

1. Spécifiez les détails suivants (![Requis](/help/assets/icons/Required.svg) est obligatoire) :

   | Élément | Description |
   | --- | --- |
   | **[!UICONTROL Suite de rapports]** | Vous pouvez sélectionner la suite de rapports de la mesure calculée.  La mesure calculée que vous définissez est disponible dans les projets Workspace en fonction de la suite de rapports sélectionnée. |
   | **[!UICONTROL Mesure Projet uniquement]** | Une boîte de dialogue d’informations s’affiche en haut de cette boîte de dialogue lorsque vous modifiez une mesure calculée qui a été créée pour un seul projet, comme décrit dans la section [Créer des mesures calculées pour un seul projet](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project). <p>Si vous souhaitez que cette mesure calculée soit disponible pour tous les projets, sélectionnez l’option **[!UICONTROL Rendre cette mesure disponible pour tous vos projets et l’ajouter à votre liste de composants]**.</p> |
   | **[!UICONTROL Titre]** ![Requis](/help/assets/icons/Required.svg) | Nommez la mesure calculée, par exemple `Conversion Rate`. |
   | **[!UICONTROL Description]** | Fournissez une description du segment, par exemple, `Calculated metric to define the conversion rate.`. Il n’est pas nécessaire de décrire la formule de la mesure calculée, car la formule est déjà automatiquement disponible dans [!UICONTROL Résumé]. |
   | **[!UICONTROL Format]** | Sélectionnez un format pour la mesure calculée : vous pouvez choisir entre **[!UICONTROL Décimale]**, **[!UICONTROL Heure]**, **[!UICONTROL Pourcentage]** et **[!UICONTROL Devise]**. |
   | **[!UICONTROL Nombres de décimales]** | Spécifiez le nombre de décimales pour le format sélectionné. Activé uniquement lorsque le format sélectionné est Décimal, Devise et Pourcentage. |
   | **[!UICONTROL Afficher la tendance à la hausse sous forme de]** | Indiquez si une tendance à la hausse de la mesure calculée s’affiche sous la forme ▲ **[!UICONTROL Bon (Vert)]** ou ▼ **[!UICONTROL Mauvais (Rouge)]**. |
   | **[!UICONTROL Devise]** | Spécifiez la devise de la mesure calculée. Activé uniquement lorsque le format sélectionné est Devise. |
   | **[!UICONTROL Balises]** | Organisez la mesure calculée en créant ou en appliquant une ou plusieurs balises. Commencez à saisir du texte pour rechercher les balises existantes que vous pouvez sélectionner. Ou appuyez sur **[!UICONTROL ENTRÉE]** pour ajouter une nouvelle balise. Sélectionnez ![CrossSize75](/help/assets/icons/CrossSize75.svg) pour supprimer une étiquette. |
   | **[!UICONTROL Aperçu]** | La prévisualisation couvre les 90 derniers jours et permet de déterminer si vous avez correctement défini votre mesure. |
   | **[!UICONTROL Résumé]** | Affiche un résumé de la définition de la mesure calculée. <br/>Par exemple : ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Nombre total de commandes]** ![Diviser](/help/assets/icons/Divide.svg) ![Événement](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]**. |
   | **[!UICONTROL Définition]** ![Obligatoire](/help/assets/icons/Required.svg) | Définissez votre segment à l’aide du [créateur de définitions](#definition-builder). |

1. Pour vérifier si votre définition de mesure calculée est correcte, utilisez la **[!UICONTROL Prévisualisation]** des résultats de la mesure calculée mise à jour en permanence. La **[!UICONTROL Prévisualisation]** couvre les 90 derniers jours et évalue en continu la définition de votre mesure calculée.

   La **[!UICONTROL Compatibilité des produits]** indique la compatibilité de la mesure calculée avec les fonctionnalités d’Adobe Analytics. Consultez [Compatibilité de la mesure](/help/components/calculated-metrics/cm-compatibility.md) pour en savoir plus.

1. Sélectionnez :
   * **[!UICONTROL Enregistrez]** pour enregistrer la mesure calculée.
   * **[!UICONTROL Enregistrez sous]** pour enregistrer une copie de la mesure calculée.
   * **[!UICONTROL Annulez]** pour annuler toute modification apportée à une mesure calculée ou annuler la création d’une mesure calculée.


## Créateur de définitions

Utilisez le créateur de définitions pour faire glisser et déposer des dimensions, des mesures, des segments et des fonctions permettant de créer des mesures personnalisées en fonction de la logique de hiérarchie des conteneurs, des règles et des opérateurs. Dans cette construction, vous pouvez utiliser des mesures standard, des mesures définies par Adobe, des mesures calculées, des segments, des dimensions et des fonctions. Tous ces composants sont disponibles à partir du panneau des composants dans le créateur de mesures calculées. De plus, vous pouvez utiliser des opérateurs et des conteneurs dans la définition.

![Créer une mesure calculée](assets/create-calculated-metric.gif)

Seules les mesures sont définies comme des composants uniques dans la zone **[!UICONTROL Définition]**. Tous les autres composants sont définis comme un conteneur, des mesures d’encapsulation ou d’autres conteneurs. Consultez [Conteneurs](#containers) pour plus d’informations.

### Mesures

Pour ajouter une mesure, procédez comme suit :

* Faites glisser et déposez un composant ![Événements](/help/assets/icons/Event.svg) **[!UICONTROL Mesures]** du panneau Composants sur **[!UICONTROL Faites glisser et déposez ici des mesures, des dimensions, des éléments de dimension, des segments et/ou des fonctions]**. Vous pouvez utiliser la fonction ![Rechercher](/help/assets/icons/Search.svg) dans la barre des composants pour rechercher des composants spécifiques.

Lorsque vous utilisez une mesure calculée dans le cadre de votre définition, la mesure calculée est développée.

Pour modifier une mesure, procédez comme suit :

1. Sélectionnez ![Paramètre](/help/assets/icons/Setting.svg) dans un composant de mesure dans la zone **[!UICONTROL Définition]**.
1. Dans la boîte de dialogue contextuelle, vous pouvez définir le type de mesure et un modèle d’attribution. Consultez [Type de mesure et attribution](m-metric-type-alloc.md).

Pour supprimer une mesure, procédez comme suit :

* Sélectionnez ![Fermer](/help/assets/icons/Close.svg) dans la mesure.

### Opérateurs

Les opérateurs vous permettent de spécifier l’opérateur entre les composants ou les conteneurs. Les opérateurs apparaissent automatiquement entre :

* deux mesures ou plus dans un conteneur ;
* deux conteneurs ou plus dans un conteneur :
* une ou plusieurs mesures et un ou plusieurs conteneurs dans un conteneur.

Vous pouvez sélectionner :

| Symbole | Opérateur |
|:---:|---|
| ![Diviser](/help/assets/icons/Divide.svg) | Diviser (par défaut) |
| ![Fermer](/help/assets/icons/Close.svg) | Multiplication |
| ![Supprimer](/help/assets/icons/Remove.svg) | Soustraction |
| ![Ajouter](/help/assets/icons/Add.svg) | Ajouter |

### Nombre statique

Vous pouvez ajouter un nombre statique à votre définition de mesure calculée. Pour ajouter un nombre statique, procédez comme suit :

* Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** depuis un conteneur.
* Sélectionnez **[!UICONTROL Nombre statique]**. Un conteneur de nombre statique s’affiche.
* Sélectionnez [!UICONTROL *Cliquez pour ajouter une valeur*] puis saisissez-en une.


### Conteneurs

Vous ajoutez des dimensions, des segments et des fonctions en tant que conteneurs à une définition de mesure calculée. Vous pouvez également ajouter un conteneur générique. Les conteneurs fonctionnent comme une expression mathématique et déterminent la séquence des opérations. Tout ce qui se trouve dans un conteneur est traité avant le composant ou conteneur suivant.


#### Conteneur de segment

Le concept de conteneur de segment permet de créer une [mesure segmentée](metrics-with-segments.md). Vous pouvez créer un conteneur de segment à l’aide d’un segment, ou à l’aide d’un segment que vous créez à partir d’une dimension.

* Pour ajouter un conteneur de segment à partir d’une dimension, procédez comme suit :

  1. Faites glisser et déposez un composant ![Dimensions](/help/assets/icons/Dimensions.svg) **[!UICONTROL Dimensions]** du panneau Composants sur **[!UICONTROL Faites glisser et déposez ici des mesures, des dimensions, des éléments de dimension, des segments et/ou des fonctions]**. Vous pouvez utiliser la fonction ![Rechercher](/help/assets/icons/Search.svg) dans la barre des composants pour rechercher des composants spécifiques.
  1. Dans la fenêtre contextuelle **[!UICONTROL Créer un segment à partir d’une dimension]**, définissez la condition du segment. Sélectionnez un opérateur dans la liste, puis sélectionnez une valeur ou saisissez-en une. Par exemple, **[!UICONTROL Mois]** **[!UICONTROL est égal à]** ![ChevronDown](/help/assets/icons/ChevronDown.svg) `Sep 2024`.
  1. Sélectionnez **[!UICONTROL Terminé]**. Un conteneur de segment est ajouté à la **[!UICONTROL Définition]**.


* Pour ajouter un conteneur de segment à partir d’un segment, procédez comme suit :

  * Faites glisser et déposez un composant ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** du panneau Composants sur **[!UICONTROL Faites glisser et déposez ici des mesures, des dimensions, des éléments, des segments et/ou des fonctions]**. Vous pouvez utiliser la fonction ![Rechercher](/help/assets/icons/Search.svg) dans la barre des composants pour rechercher des segments spécifiques.
    Un conteneur de segment est automatiquement ajouté à la **[!UICONTROL définition]** à l’aide du nom du segment.

  * Faites glisser et déposez un composant ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segment]** du panneau Composants vers un conteneur générique. Le conteneur est modifié en conteneur de segment.

  * Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** depuis un conteneur :

    1. Sélectionnez **[!UICONTROL Segment]**. Un conteneur de segment est ajouté à la **[!UICONTROL Définition]**.
    1. Dans le nouveau conteneur de segment, sélectionnez un segment dans le menu déroulant [!UICONTROL *Sélectionner...*].

  >[!TIP]
  >
  >Vous pouvez ajouter plusieurs segments à un conteneur.

  Les segments du conteneur sont nommés en fonction du composant de segment. Par exemple, ![Segmentation](/help/assets/icons/Segmentation.svg) **[!UICONTROL Sessions web]**. Sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour afficher une fenêtre contextuelle contenant plus de détails sur le segment. Dans la fenêtre contextuelle, sélectionnez ![Modifier](/help/assets/icons/Edit.svg) pour modifier la définition du segment.

Pour supprimer un segment d’un conteneur, procédez comme suit :

* Sélectionnez ![Fermer](/help/assets/icons/Close.svg) en regard du nom du segment.

Consultez [Mesures segmentées](metrics-with-segments.md) pour obtenir plus de détails et des exemples.

#### Conteneur de fonction

Pour ajouter un conteneur de fonction, vous pouvez utiliser ce qui suit :

* Faire glisser et déposer :

  1. Faites glisser et déposez un composant ![Fonction](/help/assets/icons/Effect.svg) **[!UICONTROL Fonctions]** du panneau Composants sur **[!UICONTROL Faites glisser et déposez ici des mesures, des dimensions, des éléments, des segments et/ou des fonctions]**. Vous pouvez utiliser la fonction ![Rechercher](/help/assets/icons/Search.svg) dans la barre des composants pour rechercher des fonctions spécifiques.
  1. Un conteneur de fonction est automatiquement ajouté à la **[!UICONTROL Définition]** à l’aide du nom de la fonction.

* Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** depuis un conteneur :

  1. Sélectionnez **[!UICONTROL Fonction]**.
  1. Dans le conteneur, sélectionnez une fonction dans le menu déroulant [!UICONTROL *Sélectionner...*].

Le conteneur de fonction est nommé selon le composant de fonction. Par exemple, ![Fonction](/help/assets/icons/Effect.svg) **[!UICONTROL RACINE CARRÉE (mesure)]**. Sélectionnez ![InfoOutline](/help/assets/icons/InfoOutline.svg) pour afficher une fenêtre contextuelle contenant plus de détails sur la fonction. Sélectionnez **[!UICONTROL En savoir plus]** pour plus d’informations sur la fonction.

Consultez [Utiliser des fonctions](cm-using-functions.md) pour plus d’informations sur l’utilisation des fonctions et sur les fonctions disponibles pour créer une mesure calculée.


#### Conteneur générique

Pour ajouter un conteneur générique, procédez comme suit :

* Sélectionnez ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Ajouter]** depuis un conteneur.
* Sélectionnez **[!UICONTROL Conteneur]**. Un nouveau conteneur générique vide est ajouté à la **[!UICONTROL Définition]**. Vous pouvez utiliser un conteneur générique pour imbriquer ou créer une hiérarchie dans la définition de votre mesure calculée.


#### Supprimer un conteneur

Pour supprimer un conteneur, sélectionnez ![Fermer](/help/assets/icons/Close.svg) au niveau du conteneur.

>[!MORELIKETHIS]
>
>[Utilisation des fonctions](cm-using-functions.md)
>[Segments](/help/components/segmentation/seg-overview.md)
>
