---
description: valeur nulle
title: Segments
uuid: 677f6030-5b3e-4dfa-bb79-9f27f3382fb1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Segments {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

## Rail des segments {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

Le rail des segments sous le menu Composants affiche les segments, ainsi que les modèles de segments, comme représentés par ces icônes :

![](assets/segment_icons.png)

[Utilisation de segments dans Analysis Workspace sur YouTube](https://www.youtube.com/watch?v=QlUCdQDnni4)(6:46)

## Création de segments {#section_693CFADA668B4542B982446C2B4CF0F5}

Vous pouvez créer des segments instantanés en déplaçant n’importe quel type de composant (dimension, élément de dimension, , mesure, segment, modèle de segment, plage de dates) dans la zone de dépôt de segment située en haut d’un panneau.

Les types de composants sont automatiquement transformés en segments. Sinon, vous pouvez cliquer sur le signe « + » dans la zone de dépôt Ajouter un segment.

Gardez les éléments suivants à l’esprit :

* Vous **ne pouvez** pas déposer les types de composants suivants dans la zone de segment : mesures calculées et dimensions/mesures à partir desquelles vous ne pouvez pas créer de segments.
* Pour l’intégralité des dimensions et événements, Analysis Workspace crée des segments de chute « existe ». Exemples : &quot;Accès là où l’eVar1 existe&quot; ou &quot;Accès là où l’1 existe&quot;.
* Si des éléments de type « non spécifié » ou « aucun » sont déposés dans la zone de dépose, ils sont automatiquement transformés en segment « n’existe pas » afin d’être traités correctement dans la segmentation.

![](assets/segment-dropzone.png)

>[!NOTE] Les segments créés de cette façon sont internes au projet.

Vous pouvez choisir de rendre ces segments publics (globaux) en procédant comme suit :

1. Passez la souris sur le segment dans la zone de dépôt et cliquez sur l’icône &quot;i&quot;.
1. In the information panel that displays, click **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Autres méthodes d’application de segments {#section_10FF2E309BA84618990EA5B473015894}

Il existe plusieurs autres méthodes pour appliquer des segments à un projet de forme libre.

| Action | Description |
|--- |--- |
| Création d’un segment d’après une sélection | Créez un segment incorporé. Sélectionnez des lignes, cliquez avec le bouton droit de la souris sur la sélection, puis créez un segment incorporé. Ce segment s’applique uniquement au projet ouvert et n’est pas enregistré comme un segment Analytics. 1. Sélectionnez des lignes.  2. Cliquez avec le bouton de la souris sur la sélection.  3. Cliquez sur *Créer un segment d’après la sélection*. |
| Composants > Nouveau segment | Ouvre le créateur de segments. Voir [Créateur de segment](https://docs.adobe.com/content/help/fr-FR/analytics/components/segmentation/segmentation-workflow/seg-build.html) pour en savoir plus sur la segmentation. |
| Partager > Partager le projet ou Partager > Traiter les données du projet | Dans l’outil [Traiter et partager](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), découvrez comment les segments que vous appliquez au projet sont disponibles dans l’analyse partagée avec le destinataire. |
| Utiliser les segments comme dimensions | Vidéo : Utilisation [de segments comme dimensions dans  espace de travail](https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39) |
