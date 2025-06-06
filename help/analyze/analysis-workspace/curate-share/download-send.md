---
description: Vous pouvez télécharger des données à partir dʼAnalysis Workspace aux formats PDF et CSV, ou en les copiant.
title: Téléchargement de fichiers PDF ou CSV
feature: Curate and Share
role: User, Admin
exl-id: 085013dc-8263-4fc8-9492-99f0ecadf14b
source-git-commit: 04c588cbe8cd4cc9b8d6fe162e3623c2be076325
workflow-type: tm+mt
source-wordcount: '1044'
ht-degree: 89%

---

# Téléchargement de fichiers PDF ou CSV

Il existe plusieurs façons d’exporter des données à partir d’Analysis Workspace. La méthode choisie dépend du jeu de données à analyser et de la personne qui doit y accéder.

Les données exportées peuvent prendre la forme de données copiées, ou de fichiers CSV ou PDF. Il est généralement préférable d’utiliser un PDF si vous souhaitez inclure des visualisations dans le fichier. Utilisez le format CSV et les données copiées si vous souhaitez simplement des données en texte brut.

## Télécharger un projet au format CSV ou PDF {#download-project}

Tenez compte des points suivants lors du téléchargement de projets :

* Lors du téléchargement de projets au format CSV ou PDF, le projet peut être enregistré ou non lorsque vous demandez un téléchargement de projet. Cependant, seuls les projets enregistrés peuvent être [planifiés](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md).

* Lors du téléchargement de projets en tant que PDF :
   * L’exportation des téléchargements peut prendre plusieurs minutes, car le projet est réexécuté sur les serveurs d’Adobe avant le rendu au format PDF. Nous vous recommandons de ne pas quitter le projet tant que le fichier PDF n’a pas été téléchargé dans votre navigateur. Cependant, vous pouvez continuer à apporter des modifications au projet pendant que vous patientez. Si le rendu dʼun fichier PDF prend plus de 5 minutes, vous serez invité à l’envoyer par e-mail.
   * Les téléchargements sont générés en une seule page sans pagination.
   * Les rendus de PDF contiennent ce qui se trouve sur la page dans Workspace. Si un projet comprend des panneaux et des visualisations aux dimensions personnalisées, vous devez définir leurs dimensions automatiquement (à l’aide du bouton dans le coin supérieur droit) afin d’éviter toute troncation du contenu.
   * Les [hyperliens](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) qui existent dans les tableaux à structure libre ne sont pas fonctionnels dans le PDF téléchargé.

Pour télécharger un projet au format CSV ou PDF, procédez comme suit :

1. Effectuez l’une des opérations suivantes, selon le format dans lequel vous souhaitez télécharger le projet :

   * **PDF :** sélectionnez **[!UICONTROL Projet]** > **[!UICONTROL Télécharger un PDF]**.

     Choisissez cette option pour que le fichier téléchargé contienne tous les tableaux et toutes les visualisations affichés (visibles) dans le projet.

   * **CSV :** sélectionnez **[!UICONTROL Projet]** > **[!UICONTROL Télécharger un CSV]**.

     Choisissez cette option si vous souhaitez des données en texte brut.

   ![](assets/download-project.png)

1. Le cas échéant, si vous choisissez de télécharger un PDF, un message s’affiche une fois que le projet est prêt à être téléchargé. Cliquez sur [!UICONTROL **Télécharger**].
1. Cliquez sur l’icône **[!UICONTROL Télécharger ce fichier]** et enregistrez le fichier dans un dossier de votre choix.

## Copier les données dans le presse-papiers (raccourci clavier : Ctrl+C) {#copy-data}

Lʼoption **[!UICONTROL Copier dans le presse-papiers]**, accessible par un clic droit, permet de copier rapidement des données de Workspace et de les coller dans un outil tiers.

* Pour copier le tableau affiché, cliquez avec le bouton droit sur lʼen-tête du tableau et choisissez **Copier les données dans le presse-papiers**.
* Si vous souhaitez copier un sous-ensemble de données, effectuez une sélection dans le tableau et cliquez avec le bouton droit > **Copier la sélection dans le presse-papiers**.

>[!TIP]
>
>Vous pouvez utiliser la touche de raccourci `Ctrl+C` pour copier votre sélection dans le Presse-papiers, puis utiliser `Ctrl+V` pour la coller dans un outil tiers.

![](assets/copy-selection.png)

## Télécharger les données au format CSV {#download-data}

Lʼoption de clic droit **[!UICONTROL Télécharger les données au format CSV]** vous permet de télécharger un tableau de données ou la source de données de nʼimporte quelle visualisation au format CSV.

* Dans lʼen-tête dʼun tableau ou dʼune visualisation, cliquez avec le bouton droit et choisissez **[!UICONTROL Télécharger les données au format CSV]**. Cette option télécharge les données affichées dans le tableau ou la source de données sous-jacente pour une visualisation au format CSV.

  >[!NOTE]
  >
  >  Remarque : la visualisation Carte ne prend pas en charge cette option.

* Dans un tableau, cliquez avec le bouton droit et choisissez **[!UICONTROL Télécharger la sélection au format CSV]**. Seule la sélection est téléchargée avec cette option, par opposition au tableau complet affiché.

![](assets/download-data-viz.png)

## Télécharger les éléments au format CSV {#download-items}

Si vous souhaitez analyser davantage que les 400 lignes de données visibles dans un tableau, cliquez avec le bouton droit sur lʼen-tête du tableau ou sur une ligne et sélectionnez **Télécharger les éléments au format CSV (_nom de la dimension_)**. Cette option exporte jusquʼà 50 000 éléments de dimension (selon le tri du tableau) pour la dimension sélectionnée, avec des filtres et des segments appliqués. Si vous choisissez cette option dans la partie supérieure du tableau, la première dimension du tableau est exportée. Bien quʼaucune limite ne soit appliquée dans le tableau à structure libre, il est recommandé dʼutiliser lʼoption Télécharger les éléments dans des tableaux de moins de 20 colonnes afin dʼassurer des performances optimales.

>[!TIP]
>
> Si votre dimension dépasse 50 000 éléments, téléchargez le fichier avec différentes mesures de tri appliquées ou appliquez un filtre. Par exemple, triez les visites par ordre descendant dans un téléchargement, puis par ordre ascendant dans un second téléchargement. Cette astuce peut vous aider à récupérer des éléments à traîne longue.

Vous pouvez réaliser plusieurs tâches au sein du projet et même naviguer vers un nouveau projet Workspace dans le même onglet pendant le téléchargement est en cours. Le téléchargement est interrompu si vous ouvrez un nouvel onglet du navigateur. Le téléchargement est annulé si vous quittez complètement Workspace ou si vous fermez lʼonglet du navigateur.

![](assets/download-items.png)

### Fichier des éléments téléchargés

Les fonctionnalités du tableau seront appliquées au fichier téléchargé comme suit :

* Tous les segments du panneau sont appliqués en tant que filtres.
* Les répartitions **au-dessus** de la dimension sélectionnée dans le tableau sont appliquées en tant que filtres au-dessus de chaque colonne.
* Les répartitions **en dessous** de la dimension sélectionnée dans le tableau sont supprimées.

Dans lʼexemple ci-dessus, les éléments de page sont téléchargés avec le segment de panneau (nouveaux visiteurs/clients) et les composants (canal marketing = e-mail) sont appliqués en tant que filtres. Quant aux composants ci-dessous (type d’appareil mobile), ils sont supprimés du fichier CSV téléchargé.

![](assets/downloaded-file.png)

### Notifications de téléchargement

Au fur et à mesure du téléchargement du fichier, une notification dʼinformation sʼaffiche et indique la progression du téléchargement. Vous pouvez à tout moment annuler le téléchargement en cliquant sur **[!UICONTROL Annuler le téléchargement]**. La fermeture du toast **nʼannulera pas** le téléchargement.

Une fois le fichier terminé, une notification dʼachèvement sʼaffiche et le fichier est téléchargé dans votre navigateur.

Si vous demandez plus dʼun téléchargement à la fois, vous recevrez une notification indiquant que chaque téléchargement supplémentaire sera mis en attente jusquʼà ce que le téléchargement précédent se termine.

![](assets/toast.png)

## FAQ {#faq}

| Question | Réponse |
| --- | --- |
| Pourquoi mon PDF téléchargé ne comporte-t-il quʼune seule page ? | Pour lʼinstant, Workspace ne pagine pas les PDF téléchargés. |
| Puis-je exporter plus de 50 000 éléments avec lʼoption « Télécharger les éléments au format CSV » ? | Bien que chaque téléchargement puisse contenir jusquʼà 50 000 éléments de dimension, vous pouvez modifier le tri de votre tableau pour récupérer des éléments à traîne longue ou appliquer un filtre pour télécharger des éléments plus spécifiques. |
| À quoi sert l’option **[!UICONTROL Copier la visualisation]** ? | Contrairement aux options [!UICONTROL **Copier des données dans le presse-papiers**] ou [!UICONTROL **Copier la sélection dans le presse-papiers**], l’option **[!UICONTROL Copier la visualisation]**, accessible par un clic droit, n’est pas une option d’export. Cela vous permet de copier une visualisation ou un panneau dʼun emplacement Workspace à un autre. Par exemple, dʼun panneau à un autre au sein du même projet, ou dʼun projet à un autre. [Vidéo sur la liaison interne](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=fr) |
