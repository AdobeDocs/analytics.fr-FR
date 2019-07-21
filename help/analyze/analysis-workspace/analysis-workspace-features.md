---
keywords: Analysis Workspace
seo-title: Présentation de l'espace de travail d'analyse
solution: Analytics
title: Présentation de l'espace de travail d'analyse
topic: Reports and Analytics
uuid: 4 df 6 be 48-2 c 88-4 b 9 d -9536-ed 64 ffbb 6 ee 4
translation-type: tm+mt
source-git-commit: cab449bb5c6a824f800845edd3d45c8b7a1238aa

---


# Présentation de l'espace de travail d'analyse

Analysis Workspace élimine toutes les limites courantes d’un rapport Analytics unique. Il offre un canevas robuste et souple permettant de créer des projets d’analyses personnalisés. Faites glisser des tableaux de données, des visualisations et des composants (dimensions, mesures, segments et granularités temporelles) sur un projet. Créez instantanément des ventilations et des segments, des cohortes pour analyse, ainsi que des alertes, comparez des segments, analysez les flux et les abandons, et traitez et planifiez les rapports pour les partager avec n’importe qui dans votre entreprise.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Espace de travail]**

## Overview video {#section_B99BF8A326D94ECB91BD69C9888AD10C}

>[!VIDEO](https://www.youtube.com/watch?v=IHOy-QsvVcA)

Vous trouverez [ici](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) la liste complète de sélections YouTube.

>[!NOTE]
>
>See [What's New in Analysis Workspace](../../analyze/analysis-workspace/new-features-in-analysis-workspace.md#concept_EDB651D6F41E4F7BB4EB5E1EBB95D195) for updates about features.

## Full control over project elements and components {#section_B7E3EDA3EDEE407D833F4FDB69646EEC}

Analysis Workspace offre liberté et flexibilité :

* Faire glisser des composants (dimensions, mesures, segments et granularités temporelles)
* Faire glisser plusieurs visualisations sur le projet
* Déplacer, redimensionner et empiler des visualisations à l’emplacement de votre choix dans un projet

![](assets/fa_project_new.png)

Voir [Création d’un projet Analysis Workspace](../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md#task_C2C698ACC7954062A28E4784911E6CF2) pour en savoir plus.

## Multiple visualizations in a project {#section_B7670740C2D44130B21DAF0873280DA5}

Faites glisser autant de visualisations que vous le souhaitez sur un projet.

![](assets/visualizations-multiple.png)

Créez un projet indiquant le pourcentage de modifications, avec plusieurs visualisations correspondant aux cellules dans un tableau de données à structure libre.

![](assets/visualizations-multiple02.png)

See [Create an Analysis Workspace project](../../analyze/analysis-workspace/build-workspace-project/t-freeform-project.md#task_C2C698ACC7954062A28E4784911E6CF2) for more information.

## Intra-linking to panels and visualizations {#section_253EA04E067F4A29A8B54CE2B7631086}

In conjunction with the [rich text editing](../../analyze/analysis-workspace/visualizations/text.md#concept_2315D97E27364E3194AC1C459B654B2F) capabilities of Analysis Workspace, you can link down to specific panels and visualizations within a project from a text box, such as to create a project's table of contents. Ces liens peuvent être partagés comme n’importe quel lien de projet, afin de rediriger un utilisateur vers une visualisation ou un panneau spécifique au sein d’un projet. De nouvelles options contextuelles, nommées Obtenir un lien vers le panneau et Obtenir un lien vers la visualisation, ont été ajoutées. Pour ajouter des intra-liens à votre projet, procédez comme suit :

1. Faites glisser une visualisation de texte dans un projet, par exemple près d’une visualisation ou d’un tableau auquel il convient d’ajouter davantage de contexte.
1. Renseignez la zone de texte avec, par exemple, une table des matières, puis surlignez un élément à lier à un panneau ou à une visualisation, par exemple les mesures de succès.

   ![](assets/intra-linking1.png)

1. Accédez à ce panneau ou à cette visualisation, puis cliquez avec le bouton droit sur son en-tête.
1. Scroll down and select **[!UICONTROL Get Panel Link]** or **[!UICONTROL Get Visualization Link]**:

   ![](assets/intra-linking2.png)

1. Copiez ce lien, puis ajoutez-le au lien hypertexte Mesures de succès dans la visualisation de texte. Cliquez sur la coche pour enregistrer le texte.

Quand un utilisateur clique sur un lien, les panneaux ou visualisations réduits dans le projet sont agrandis afin d’être visibles.

>[!NOTE]
>
>You can also use this feature within the **[!UICONTROL Edit Description]** right-click option.

## Link to other projects {#section_AE886C367C3E4F189B65B1BD9BCDBD8C}

You can link users to other projects that may be of interest to them by going to  **[!UICONTROL Share]** &gt; **[!UICONTROL Get Project Link]** and embedding this link in project descriptions, for example.

## Dynamic visualization of selected cells {#section_182CEC285E4547EBA4608D5F70C9D5D7}

Sélectionnez des cellules individuelles et observez les visualisations changer dynamiquement. [Synchronisez et verrouillez](../../analyze/analysis-workspace/analysis-workspace-features.md#section_9D66A001586F49CEB0C565581E44957C) une visualisation avec les cellules sélectionnées.

![](assets/visualize-selected-cells.png)

## Lock selected items or positions {#section_9D66A001586F49CEB0C565581E44957C}

Verrouillez les visualisations pour contrôler quelles sources de tableaux de données à structure libre correspondent aux visualisations.

![](assets/manage-data-source.png)

See [Manage data sources](../../analyze/analysis-workspace/visualizations/t-sync-visualization.md#task_A73B065DC3834AFCA422E364A1468099).

## Trend visualizations from selected cells {#section_34930C967C104C2B9092BA8DCF2BF81A}

Créez une visualisation d’après les cellules sélectionnées (Right-click &gt; **[!UICONTROL Trend Selection]**.)

![](assets/trend-selection.png)

Les sélections de tendances sont maintenant **liées** au tableau ci-dessous, de sorte que si vous sélectionnez une autre ligne du tableau, le tableau des tendances reflétera cette ligne.

![](assets/trend-selection2.png)

## Dimensions and dimension item breakdowns {#section_1380C1F9E51E4BFB8C5D35E7A53BC70D}

En tant que détaillant, vous pouvez approfondir davantage encore l’analyse de vos campagnes afin de comprendre comment mieux mobiliser vos clients. Ventilez vos données de différentes manières en fonction de vos besoins ; créez des requêtes à l’aide de mesures, de dimensions, de segments, de chronologies pertinentes et autres valeurs de ventilation d’analyse.

![Résultat de l’étape](assets/fa_data_table_actions.png)

See [Break down dimensions](../../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md#task_B594DA2476E84DFDA8279E831F0BD9C4).

## Segments from table selections {#section_73BC3688089B426D969B3D5B606DA970}

Sélectionnez des cellules du tableau à structure libre et créez un segment d’après la sélection.

Comparez plusieurs segments et créez et appliquez instantanément des segments. Vous pouvez appliquer plusieurs segments afin de vous focaliser sur des clients spécifiques d’après leur comportement et leur interaction, puis les comparer et les contraster.

![](assets/segment_inline.png)

Déposez un segment sur le panneau d’analyse à structure libre au niveau du projet ; le segment est alors appliqué au projet entier.

![](assets/segment-panel.png)

Voir   [Segments](../../analyze/analysis-workspace/components/t-freeform-project-segment.md#task_11C6A2C7717B48049E5750B9D20FEC80).

## Project and component tagging {#section_F54D688132A541F2982326D5E022B90D}

Vous pouvez appliquer des balises aux projets et aux composants dans Analysis Workspace :

* Appliquez ou créez des balises au niveau du projet dans le panneau Informations. (![)](assets/information_icon.png)

* Cliquez avec le bouton droit de la souris sur ces composants pour les baliser (ou créez des balises) à partir du panneau Composants.
* Utilisez le caractère # dans le champ Rechercher pour localiser les balises.

## Component actions {#section_CBF4D0A5F63E4B0883077B8D852B800B}

Dans le menu Actions, vous réalisez les actions au niveau du composant en haut du rail gauche des composants. Sélectionnez un composant, puis cliquez sur **[!UICONTROL Actions]pour afficher les actions.**

| Action des composants | Description |
|--- |--- |
| Baliser | Organisez ou gérez les composants en leur appliquant des balises. Il apparaît ensuite dans le gestionnaire de composants correspondant, par exemple : Analytics &gt; Composants &gt; Segments ou Analytics &gt; Composants &gt; Projets. |
| Favori | Ajoutez le composant à votre liste de favoris. Il apparaît ensuite dans le gestionnaire de composants correspondant, par exemple : Analytics &gt; Composants &gt; Segments ou Analytics &gt; Composants &gt; Projets  . |
| Approuver | Approuvez le composant pour le rendre canonique. Il apparaît ensuite dans le gestionnaire de composants correspondant, par exemple : Analytics &gt; Composants &gt; Segments ou Analytics &gt; Composants &gt; Projets. |
| Partager | S’applique seulement aux segments. |
| Supprimer | S’applique seulement aux segments. |

Voir [Visualisations](../../analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#concept_09242627629147A88A68F1506954C276) pour en savoir plus.

## Additional feature descriptions {#section_5F06AE43C0194CFDBCA7EE0EA3C30B05}

**Ce que vous pouvez faire glisser et empiler**

Composants

* Dimensions
* Segments
* Mesures
* Plages de dates
* Granularités temporelles (heure, jour, semaine, etc.).

**Tableaux à structure libre et visualisations multiples**

Aucune limite technique ne restreint le nombre de tableaux à structure libre et de visualisations que vous pouvez ajouter au panneau. Vous pouvez également exécuter une nouvelle visualisation (ou l’exporter au format CSV) pour chaque tableau à structure libre ou la sélection de lignes d’un tableau.

**Organisation, tri et copie des colonnes**

* Paramètres prédéfinis de tri des plages de dates (ne comprennent pas les plages de dates personnalisées).
* Ctrl (ou Commande) + clic + faire glisser une colonne copie la colonne ; quand vous faites glisser la copie, elle est collée à ce nouvel emplacement dans le tableau.

See [Hotkeys Available in Analysis Workspace](../../analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md#concept_9A6356084DBC4D468E265E7A65B3E051) for more information.

**Sélections et actions**

Sélectionnez des lignes et des colonnes comme vous le faites dans Excel. Puis agissez sur ces sélections. Par exemple :

* créez des visualisations des sélections ;
* copiez-les dans le Presse-papiers (Ctrl ou Commande + C) ;
* ventilez plusieurs lignes sélectionnées : sélectionnez des lignes puis faites glisser une dimension sur la sélection. Ou cliquez avec le bouton droit de la souris sur la sélection et utilisez le menu Ventilation.

**Enregistrement automatique et modifications non enregistrées**

Vous serez invité à enregistrer vos modifications si vous tentez de fermer le navigateur (ou utilisez le bouton Retour) alors que le projet n’a pas été enregistré. En cas de plantage du système, vous recevrez au chargement du projet une alerte vous invitant à le restaurer à son état antérieur.

Les projets existants (qui ne sont pas nouveaux) s’enregistrent automatiquement seulement en cas de blocage du navigateur ou dans d’autres circonstances, quand vous n’avez pas eu l’occasion de les enregistrer.

**Toutes les visites**

Un segment par défaut propre à Analysis Workspace. *`All Visits`* présente les totaux correspondant aux composants que vous avez ajoutés au tableau.

**Mesures calculées**

Utilisez les calculs de la même façon que vous utilisez les mesures standard.

Voir [Mesures calculées](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/).
