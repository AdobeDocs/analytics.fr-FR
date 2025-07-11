---
title: Préférences de l’utilisateur ou de l’utilisatrice
description: Découvrez comment définir des préférences générales et de projet pour les utilisateurs et utilisatrices.
feature: Workspace Basics
role: User, Admin
exl-id: f32e3061-f396-4730-96e1-d251b00e32f0
source-git-commit: 6cec1085093404235e29319db984d4389c68c31e
workflow-type: tm+mt
source-wordcount: '3461'
ht-degree: 80%

---

# Préférences de l’utilisateur ou de l’utilisatrice

Vous pouvez gérer les paramètres d’Analysis Workspace et ses composants connexes pour tous les nouveaux projets ou panneaux que vous créez. Les projets et panneaux existants ne sont pas affectés.


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Gérer les préférences](https://video.tv.adobe.com/v/332600/?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

## Mettre à jour les préférences

Vous pouvez mettre à jour vos préférences des manières suivantes :

- Sélectionnez ![Administrateur utilisateur/Administratrice utilisatrice](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Modifier les préférences]** dans l’interface principale de Workspace.
- Sélectionnez **[!UICONTROL Projet]** > **[!UICONTROL Préférences utilisateur]** dans le menu lorsque vous travaillez dans un projet Workspace.
- Sélectionnez **[!UICONTROL Composants]** > **[!UICONTROL Préférences]** dans la barre de menus supérieure de Customer Journey Analytics (disponible uniquement pour les administrateurs et administratrices de produit).

## Configuration des préférences

Vous pouvez configurer les préférences suivantes :


## Préférences générales

Vous pouvez personnaliser les préférences générales de tous les nouveaux projets que vous créez dans Analysis Workspace. Pour plus d’informations sur l’accès à ces préférences, consultez [Mettre à jour les préférences](#update-preferences).

| Préférence | Options |
| --- | --- |
| Page de destination | Choisissez la page qui s’affiche par défaut lorsque vous accédez à Adobe Analytics : <ul><li>Liste des projets (par défaut)</li><li>Projet vierge</li><li>Projet spécifique sélectionné dans une liste</li></ul> |
| Afficher les conseils | Affiche les conseils dans un cadre bleu de la zone inférieure droite d’Analysis Workspace. <p>Cette option est activée par défaut.</p> |
| Composants affichés dans les groupes du rail de gauche | Choisissez le nombre de chaque composant à afficher dans le menu Composants du rail de gauche. <p>Si vous choisissez 0, le composant n’est plus accessible à partir du rail de gauche de vos espaces de travail.</p><p>Par défaut, 5 composants sont affichés pour chacun des éléments suivants :</p> <ul><li>Dimensions</li><li>Mesures</li><li>Filtres</li><li>Périodes</li></ul> <p>Pour plus d’informations sur les composants dans Analysis Workspace, consultez [Présentation des composants](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).</p> |

## Préférences de la société {#company-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_shareonlyworkspace"
>title="Autorisation du partage uniquement avec les utilisateurs et utilisatrices de Workspace"
>abstract="Lorsque cette option est activée, l’option **[!UICONTROL Partager avec tout le monde]** n’est plus disponible pour les utilisateurs et les utilisatrices lors du partage d’un projet Analysis Workspace. Les personnes qui avaient obtenu l’accès à un projet via cette option de partage ne peuvent plus accéder au projet."

>[!CONTEXTUALHELP]
>id="workspace_prefs_requireexperiencecloudauth"
>title="Exiger une authentification Experience Cloud"
>abstract="Si vous activez cette option, les personnes qui ont accès à un projet à partir de l’option **[!UICONTROL Partager avec tout le monde]** dans Analysis Workspace doivent s’authentifier à l’aide de leurs informations d’identification Experience Cloud."

>[!CONTEXTUALHELP]
>id="workspace_prefs_projectcommenting"
>title="Autoriser les commentaires sur les projets"
>abstract="Lorsque cette option est activée, une zone de commentaires est disponible dans le rail de droite de chaque projet dans Analysis Workspace."


Vous pouvez mettre à jour les préférences de la société qui s’appliquent aux utilisateurs et utilisatrices et aux projets de votre organisation. Pour plus d’informations sur l’accès à ces préférences, consultez [Mettre à jour les préférences](#update-preferences).

| Section | Préférence | Options |
| --- | --- | --- |
| **Onglet Modèles** | | |
|  | Masquer l’onglet Modèles | Masque l’onglet Modèles pour tous les utilisateurs de votre organisation. |
| **Partage des projets** | | |
| | Autorisation du partage uniquement avec les utilisateurs et utilisatrices de Workspace | Lorsque cette option est activée, les utilisateurs et les utilisatrices de votre organisation ne peuvent pas voir l’option **[!UICONTROL Partager avec tout le monde]** dans le menu **[!UICONTROL Partager]**. Les utilisateurs ne peuvent pas partager des projets avec des personnes qui ne disposent pas d’un compte Analysis Workspace dans votre organisation, comme décrit dans la section [Partager un projet avec tout le monde (aucune connexion requise)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).<br/>Cette option est désactivée par défaut pour toutes les organisations, à l’exception des clients qui disposent d’une licence Healthcare Shield. <p>Tenez compte des points suivants lorsque vous activez ou désactivez cette option :<ul><li>Lorsque vous activez cette option, les personnes qui avaient auparavant reçu l’accès à un projet via l’option de partage **[!UICONTROL Partager avec tout le monde]** ne peuvent plus accéder au projet.</li><li>Si cette option est activée (pour permettre le partage uniquement avec les utilisateurs et utilisatrices de Workspace), puis désactivée ultérieurement (pour permettre le partage avec tout le monde), les personnes qui ont précédemment reçu l’accès à un projet via l’option de partage **[!UICONTROL Partager avec tout le monde]** ne retrouvent pas automatiquement leur accès au projet. Dans ce cas, l’utilisateur qui a partagé le projet doit activer l’option [!UICONTROL **Le lien est actif**] disponible lors du partage d’un projet avec tout le monde **([!UICONTROL Partager]** > **[!UICONTROL Partager avec tout le monde]**), comme décrit dans [Partager un projet avec tout le monde (aucune connexion requise)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).</li><li>**Pour les clientes et clients qui détiennent une licence Healthcare Shield :** cette option est activée par défaut et ne peut pas être désactivée. Avant de pouvoir désactiver cette option pour que les utilisateurs et les utilisatrices puissent utiliser l’option de partage **[!UICONTROL Partager avec tout le monde]**, vous devez d’abord ajouter l’autorisation [!UICONTROL Partager les liens du projet avec tout le monde] (située dans [!UICONTROL Outils de création de rapports]) dans Adobe Admin Console. Une fois l’autorisation ajoutée, vous pouvez désactiver cette option, puis accepter la mention légale qui en résulte. Pour plus d’informations sur l’ajout d’une autorisation dans Admin Console, voir [Gestion des autorisations de produit dans Admin Console](https://helpx.adobe.com/fr/enterprise/using/manage-permissions-and-roles.html).</li></ul> |
| | Exiger une authentification Experience Cloud | Lorsque cette option est activée, les personnes qui ont accès à un projet par le biais de l’option **[!UICONTROL Partager avec tout le monde]** dans Analysis Workspace doivent s’authentifier à l’aide de leurs informations d’identification Experience Cloud.<p>Une fois cette option activée, chaque fois qu’un utilisateur ou une utilisatrice partage un projet à l’aide de l’option de partage **[!UICONTROL Partager avec tout le monde]**, l’option **[!UICONTROL Exiger une authentification Experience Cloud]** est activée dans la boîte de dialogue de partage et ne peut pas être désactivée par l’utilisateur ou l’utilisatrice qui partage le projet. Pour plus d’informations sur la manière dont les utilisateurs peuvent partager des projets avec tout le monde, voir [ Partager un projet avec tout le monde (aucune connexion requise)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link). <p> <p>Tenez compte des points suivants lorsque vous activez cette option : <ul><li>Lorsque vous activez cette option, tous les projets précédemment partagés avec l’option de partage **[!UICONTROL Partager avec tout le monde]** pour lesquels l’option [!UICONTROL Exiger une authentification Experience Cloud] n’est pas activée, sont désactivés.<p>Si cette option est activée (pour exiger une authentification Experience Cloud), puis désactivée ultérieurement (pour permettre à toute personne disposant du lien d’accéder au projet), les personnes qui ont auparavant reçu l’accès à un projet via l’option de partage **[!UICONTROL Partager avec tout le monde]** ne récupèrent pas automatiquement leur accès au projet. Dans ce cas, l’utilisateur qui a partagé le projet doit activer l’option [!UICONTROL Le lien est actif] disponible lors du partage d’un projet avec tout le monde **([!UICONTROL Partager]** > **[!UICONTROL Partager avec tout le monde]** > **[!UICONTROL Le lien est actif]**), comme décrit dans [Partager un projet avec tout le monde (aucune connexion requise)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-public-link).</li><li>Cette option est disponible uniquement si l’authentification unique est implémentée dans votre organisation. Pour plus d’informations sur la manière dont les administrateurs et les administratrices système peuvent activer l’authentification unique pour votre organisation, consultez [Configurer l’identité et l’authentification unique](https://helpx.adobe.com/fr/enterprise/using/set-up-identity.html).</p><p>Si l’authentification unique est configurée pour votre organisation, vérifiez si un type de création de compte automatique est implémenté dans la console. En règle générale, un administrateur ou une administratrice système effectue cette configuration, comme décrit dans la section [Activer la création automatique de compte](https://helpx.adobe.com/fr/enterprise/using/automatic-account-creation.html).</li><li>Si votre entreprise détient une licence Healthcare Shield, cette option est activée par défaut et ne peut pas être désactivée.</li></ul> |

{style="table-layout:auto"}

## Préférences des projets et analyses {#project-analyses-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_categoricalpalette"
>title="Palette catégorielle"
>abstract="Appliquée à de nombreuses visualisations dans Analysis Workspace et l’analyse guidée. Chaque couleur représente une valeur catégorielle distincte."

>[!CONTEXTUALHELP]
>id="workspace_prefs_divergingpalette"
>title="Palette divergente"
>abstract="Appliquée à la table de cohorte dans Analysis Workspace et l’analyse guidée par la croissance des utilisateurs et des utilisatrices. Cette palette a une signification numérique avec deux extrêmes et une ligne de base au milieu."

>[!CONTEXTUALHELP]
>id="workspace_prefs_sequentialpalette"
>title="Palette séquentielle"
>abstract="Appliquée à l’analyse guidée des tendances de fréquence (barres empilées). Cette palette a une signification numérique allant du plus clair au plus foncé."

Vous pouvez personnaliser les préférences du projet de tous les nouveaux projets que vous créez dans Analysis Workspace. Pour plus d’informations sur l’accès à ces préférences, consultez [Préférences de mise à jour](#update-preferences).

Certaines de ces préférences peuvent également être personnalisées pour des projets individuels, comme décrit dans la section [Présentation des projets](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).

Cliquez sur les titres des préférences liées pour plus d’informations et de contexte sur chaque préférence.

| Section | Préférence | Options |
| --- | --- | --- |
| **Afficher** | | |
|  | [Afficher la densité](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density) | Sélectionnez le contenu à afficher à l’écran en réduisant l’espacement vertical du rail de gauche, des tableaux à structure libre et des tableaux de cohortes. <ul><li>Compact</li><li>Confortable</li><li>Développé (par défaut)</li></ul> |
| | [Palette de couleurs](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes) | Sélectionnez les palettes de couleurs de visualisation utilisées dans Analysis Workspace.<ul><li>**Palette catégorielle** : appliquée à de nombreuses visualisations dans Analysis Workspace. Chaque couleur représente une valeur catégorielle distincte. Choisissez parmi les options fournies par Adobe ou saisissez une palette personnalisée définie par des valeurs hexadécimales délimitées par des virgules.</li><li>**Palette divergente** : appliquée à la table de cohorte dans Analysis Workspace. Cette palette a une signification numérique, avec deux extrêmes et une ligne de base au milieu.</li><li>**Palette séquentielle** : appliquée à l’analyse guidée Tendances de fréquence (barre empilée). Cette palette a une signification numérique allant du clair au foncé.</li></ul> |
| **Données** | | |
|  | [Suite de rapports](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/panels/panels) | Choisissez l’emplacement où les tableaux et les visualisations obtiennent leurs données. <ul><li>La plus récente (par défaut)</li><li>Suite de rapports spécifique sélectionnée dans une liste</li></ul> |
|  | [Calendrier](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/panels/panels) | Effectuez une sélection dans une liste de : <ul><li>Plages fournies par Adobe (par défaut, ce mois-ci)</li><li>Plages personnalisées</li></ul> |
|  | [Type de panneau](https://experienceleague.adobe.com/fr/docs/analytics/analyze/analysis-workspace/panels/panels) | <ul><li>À structure libre (par défaut)</li><li>Vide</li><li>Quick Insights</li></ul> |
|  | Compter les instances répétées | Ce paramètre indique si les instances répétées sont comptabilisées dans les rapports. Par exemple, lorsqu’il est activé, ce paramètre traite plusieurs pages vues consécutives sur la même page comme plusieurs pages vues. Lorsque ce paramètre est désactivé, elles sont comptabilisées comme une seule page vue. <p>**Remarque :** ce paramètre affecte uniquement certaines mesures (telles que Visites de page unique) et ne s’applique pas aux visualisations Flux ou Abandons.</p> |
|  | Format du nombre | <ul><li>1 000,00 (par défaut)</li><li>1.000,00</li><li>1 000,00</li></ul> |
|  | Caractère séparateur CSV | <ul><li>Virgule (par défaut)</li><li>Point-virgule</li><li>Deux-points</li><li>Tube</li><li>Point</li><li>un espace</li><li>Tabulation</li></ul> |
|  | Affichage des annotations | Indiquez si les annotations sont visibles dans les projets. Pour plus d’informations sur les annotations, consultez [Présentation des annotations](/help/analyze/analysis-workspace/components/annotations/overview.md). |

## Préférences du tableau à structure libre {#freeform-table-preferences}

>[!CONTEXTUALHELP]
>id="workspace_prefs_showanomalies"
>title="Afficher les anomalies"
>abstract="Sélectionnez **[!UICONTROL Afficher les anomalies]** pour exécuter automatiquement la détection des anomalies sur la première colonne de mesure d’une visualisation de tableau à structure libre de série temporelle."

>[!CONTEXTUALHELP]
>id="workspace_prefs_showforecast"
>title="Afficher la prévision"
>abstract="Sélectionnez **[!UICONTROL Afficher les prévisions]** pour effectuer une prévision automatique de la première colonne de mesures ajoutée à une visualisation de tableau à structure libre de série temporelle."


>[!CONTEXTUALHELP]
>id="workspace_prefs_defaulttablemetric"
>title="Mesure par défaut du tableau"
>abstract="Sélectionnez la mesure par défaut à utiliser pour les tableaux à structure libre. Si la vue de données sélectionnée ne contient pas la mesure par défaut sélectionnée, le tableau passe automatiquement à une autre mesure principale."


Vous pouvez personnaliser les préférences du tableau à structure libre pour tous les nouveaux projets que vous créez dans Analysis Workspace. Pour plus d’informations sur l’accès à ces préférences, consultez [Préférences de mise à jour](#update-preferences).

Certaines de ces préférences peuvent également être personnalisées pour des tableaux individuels.

Cliquez sur les titres des sections liées pour plus d’informations et de contexte sur les préférences disponibles.

| Section | Préférence | Options |
| --- | --- | --- |
| **Tableau** | | |
| | Type de tableau | <ul><li>Tableau à structure libre</li><li>Créateur de tableaux</li></ul> |
| | Mesure par défaut du tableau | <ul><li>Occurrences</li><li>Visiteurs uniques</li><li>Visites</li></ul> |
| | Dimension du tableau par défaut | Sélectionnez l’option Minute, Heure, Jour, Semaine, Mois, Trimestre ou Année. |
| | Aligner les dates | Sélectionnez cette option pour harmoniser les dates de chaque colonne afin qu’elles commencent toutes à partir de la même ligne. |
| **[Colonne](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)** | | |
| | Renvoyer à la ligne le texte d’en-tête | Renvoyez à la ligne le texte de l’en-tête dans les tableaux à structure libre afin de rendre les en-têtes plus lisibles et les tableaux plus faciles à partager. Le renvoi à la ligne est utile pour le rendu PDF et pour les mesures dont le nom est long. Activé par défaut. |
| | Afficher les totaux | Ce total est généralement égal à ou à un sous-ensemble du [!UICONTROL total général]. Il reflète les filtres de tableau appliqués dans le tableau à structure libre, y compris l’option [!UICONTROL Inclure aucun]. |
| | Afficher les totaux généraux | Ce total représente tous les accès qui ont été collectés, parfois appelé *total de la suite de rapports*. Lorsqu’un segment est appliqué au niveau du panneau ou dans le tableau à structure libre, ce total s’ajuste pour refléter tous les accès qui correspondent aux critères de segment. Le total général n’est pas pris en charge pour les tableaux ou les répartitions avec des [lignes statiques](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| | Afficher les graphiques sparkline | Afficher ou masquer les graphiques en courbes au bas du graphique. Lorsqu’elle est masquée, la légende ne fait plus référence visuellement aux lignes. |
| | Nombre | Détermine si une cellule affiche/masque la valeur numérique pour la mesure. Par exemple, si la mesure correspond aux pages vues, la valeur numérique correspond au nombre de pages vues pour l’élément de ligne. |
| | Pourcentage | Détermine si une cellule affiche/masque la valeur de pourcentage pour la mesure. Par exemple, si la mesure est Pages vues, la valeur de pourcentage correspond au nombre de pages vues pour l’élément de ligne, divisé par le nombre total de pages vues pour la colonne.  Note : Pour être plus précis, les pourcentages supérieurs à 100 % sont parfois affichés. La limite supérieure est déplacée à 1 000 % pour que les colonnes puissent avoir des largeurs trop grandes. |
| | Afficher les anomalies | Détermine si la détection des anomalies est exécutée sur les valeurs de cette colonne. |
| | Interpréter zéro comme n’étant pas une valeur | Pour les cellules dont la valeur est 0, détermine s’il convient d’afficher un 0 ou une cellule vierge. Ce paramètre est utile lorsque vous examinez les données pour chaque jour d’un mois et que certains jours n’ont pas encore eu lieu.  Des cellules vierges peuvent être affichées au lieu de 0 pour les dates futures. Les graphiques respectent également ce paramètre (en d’autres termes, ils n’affichent pas de ligne ou de barre avec des valeurs 0 lorsque ce paramètre est coché). |
| | Arrière-plan | Détermine si une cellule affiche/masque toute la mise en forme de cellule, y compris le graphique en barres et la mise en forme conditionnelle. <ul><li>Graphique en barres</li> Graphique à barres horizontal représentant la valeur de la cellule par rapport au total de la colonne. <li>Mise en forme conditionnelle</li>Pour plus d’informations sur la mise en forme conditionnelle, consultez « Mise en forme conditionnelle » dans [Paramètres de colonne](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).</ul> |
| | Aperçu de la cellule | Aperçu de l’aspect de chaque cellule après application des options de mise en forme actuellement sélectionnées. |
| **[Ligne](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)** | | |
| | Répartition par position | Sélectionnez cette option si vous souhaitez que la répartition conserve la position de l’élément plutôt que l’élément lui-même. Pour plus d’informations sur les répartitions, consultez [Répartition des dimensions](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md). |
| | Calcul du pourcentage | <ul><li>Colonne</li><li>Ligne</li></ul> |
| | Totaux des colonnes (lignes statiques uniquement) | <ul><li>Afficher la somme des lignes : affiche la somme des éléments de ligne individuels. </li><li>Afficher le total général : affiche la somme dédupliquée des lignes.</li></ul> |

## Préférences de visualisation

Vous pouvez mettre à jour les préférences de visualisation pour tous les nouveaux projets que vous créez dans Analysis Workspace. Pour plus d’informations sur l’accès à ces préférences, consultez [Préférences de mise à jour](#update-preferences).

Certaines de ces préférences peuvent également être personnalisées pour des visualisations individuelles.

Cliquez sur les titres des sections liées pour plus d’informations et de contexte sur les préférences disponibles.

| Section | Préférence | Options |
| --- | --- | --- |
| **Valeurs par défaut générales** | | |
| | Pourcentages | Affiche les valeurs en pourcentages pour toutes les visualisations. |
| | Légende visible | Permet de masquer le texte de légende détaillé pour toutes les visualisations. |
| | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X pour toutes les visualisations. Cela peut s’avérer utile si vous disposez d’un jeu de données volumineux. |
| | Afficher l’axe double (le cas échéant) | S’applique uniquement s’il existe deux mesures : vous pouvez afficher un axe des y sur la gauche (pour une mesure) et un sur la droite (pour l’autre mesure). Ce paramètre s’avère utile lorsque les mesures tracées sont de magnitude très différente. |
| | Normalisation (le cas échéant) | Exprime les mesures en proportions égales. Ce paramètre s’avère utile lorsque les mesures tracées sont de magnitude très différente. |
| | Ancrer l’axe Y sur zéro | Si toutes les valeurs tracées sur le graphique sont considérablement au-dessus de zéro, le bas de l’axe Y devient NON-ZÉRO par défaut. Si vous cochez cette case, l’axe Y est forcé à zéro (et le graphique est à nouveau dessiné). |
| | Autoriser les anomalies à mettre à l’échelle l’axe Y | Si un graphique comporte plusieurs mesures, vous devez pointer sur chaque anomalie pour afficher la marge de confiance correspondante. Pour rendre la visualisation plus lisible, l’intervalle de confiance Détection des anomalies ne met pas automatiquement à l’échelle l’axe Y. Cette option permet à l’intervalle de confiance de mettre la visualisation à l’échelle. <p>Pour plus d’informations, consultez [Affichage des anomalies dans Analysis Workspace](/help/analyze/analysis-workspace/c-anomaly-detection/view-anomalies.md).</p> |
| **[Ligne](/help/analyze/analysis-workspace/visualizations/line.md)** | | |
| | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Ligne. |
| | Légende visible | Masquez le texte de légende détaillé pour la visualisation Ligne. |
| | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X dans la visualisation Ligne. Ce paramètre est utile si vous disposez d’un jeu de données volumineux. |
| | Afficher l’axe double (le cas échéant) | S’applique uniquement s’il existe deux mesures : vous pouvez afficher un axe des y sur la gauche (pour une mesure) et un sur la droite (pour l’autre mesure). Ce paramètre s’avère utile lorsque les mesures tracées sont de magnitude très différente. |
| | Normalisation (le cas échéant) | Exprime les mesures en proportions égales. Ce paramètre s’avère utile lorsque les mesures tracées sont de magnitude très différente. |
| | Afficher l’axe X | Affiche l’axe X sur le graphique en courbes. |
| | Afficher l’axe Y | Affiche l’axe Y sur le graphique en courbes. |
| | Ancrer l’axe Y | Si toutes les valeurs tracées sur le graphique sont considérablement au-dessus de zéro, le bas de l’axe Y devient NON-ZÉRO par défaut. Si vous cochez cette case, l’axe Y est forcé à zéro (et le graphique est à nouveau dessiné). |
| | Afficher la valeur minimale | Superposez un libellé de valeur minimale pour mettre rapidement en surbrillance les creux d’une mesure. Remarque : les valeurs minimales sont dérivées des points de données visibles dans la visualisation, et non du jeu complet de valeurs dans une dimension. |
| | Afficher la valeur maximale | Superposez un libellé de valeur maximale pour mettre rapidement en surbrillance les pics d’une mesure. Remarque : les valeurs maximales sont dérivées des points de données visibles dans la visualisation, et non du jeu complet de valeurs dans une dimension. |
| | Afficher la courbe de tendance | Affichez une courbe de tendance de régression ou de moyenne glissante sur votre série de lignes. Les courbes de tendance permettent d’illustrer plus clairement un schéma dans les données. |
| **[Cohorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)** | | |
| | Granularité | Pour les visualisations de tendances, vous pouvez modifier la granularité temporelle (Jour, Semaine, Mois, Trimestre ou Année). Cette modification sʼapplique également au tableau de source de données. |
| | Afficher uniquement le pourcentage | Supprime la valeur numérique et affiche uniquement le pourcentage. |
| | Arrondir le pourcentage à l’entier le plus proche | Arrondit la valeur de pourcentage à l’entier le plus proche au lieu d’afficher la valeur décimale. |
| | Afficher la ligne en pourcentage moyen | Insère une nouvelle ligne en haut du tableau, puis ajoute la moyenne des valeurs dans chaque colonne. |
| | Aperçu des cohortes | Un aperçu de la façon dont la palette de couleurs apparaît dans la visualisation de cohorte. |
| | Palette de cohortes | Palette de couleurs utilisée dans la visualisation de cohorte. |
| **[Graphiques combinés](/help/analyze/analysis-workspace/visualizations/combo-charts.md)** | | |
| | Afficher l’axe X | Affiche l’axe X sur le graphique combiné. |
| | Afficher l’axe Y | Affiche l’axe Y sur le graphique combiné. |
| | Afficher les barres à disques sur les lignes | Affiche les barres à disques sur les lignes des graphiques combinés. |
| **[Résumé des mesures clés](/help/analyze/analysis-workspace/visualizations/key-metric.md)** | | |
| | Type d’affichage du résumé | <ul><li>Mettre en gras le pourcentage de modification</li><li>Mettre en gras la valeur numérique</li></ul> |
| | Afficher les graphiques sparkline | Affichez ou masquez les graphiques en courbes au bas du graphique. Lorsqu’elle est masquée, la légende ne fait plus référence visuellement aux lignes. |
| | Afficher les valeurs minimales et maximales sur les graphiques sparkline | Affichez les valeurs minimales et maximales sur les graphiques en courbes principaux et de comparaison. |
| | Afficher la comparaison | Affichez les données de comparaison. Lorsqu’ils sont masqués, les objets de modification de graphique en courbes de comparaison et de modification de résumé sont n’apparaissent pas dans la vue. |
| | Options de valeur numérique | Dans la section [!UICONTROL **Résumé des mesures clés**] <ul><li>Afficher le pourcentage de modification</li><li>Afficher la différence brute</li>Différence brute entre la valeur totale de la mesure dans la période principale et la période secondaire</ul> |
| **[Abandon](/help/analyze/analysis-workspace/visualizations/fallout/configuring-fallout.md)** | | |
| | Conteneur | Basculez entre Visite et Visiteur pour analyser le cheminement du visiteur. La valeur par défaut est Visiteur. Ces paramètres permettent de comprendre l’engagement des visiteurs au niveau des visiteurs (à l’échelle de toutes visites) ou de contraindre l’analyse à une seule visite. <p>Les options disponibles sont les suivantes :</p> <ul><li>Visite</li><li>Visiteur</li></ul> |
| **[Flux](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md)** | | |
| | Conteneur | Dans la section [!UICONTROL **Flux**] <ul><li>Visite</li><li>Visiteur</li></ul> |
| | Développer les étiquettes | Habituellement, les étiquettes sur les éléments de flux sont tronquées pour gagner de l’espace à l’écran, mais vous pouvez afficher l’étiquette complète en cochant cette case. Valeur par défaut = non coché. |
| | Inclure des instances de répétition | Les visualisations Flux sont basées sur des instances d’une dimension. Ce paramètre vous donne la possibilité d’inclure ou d’exclure des instances de répétition, telles que des actualisations de page. Toutefois, les répétitions ne peuvent pas être supprimées des visualisations de flux qui incluent des dimensions à valeurs multiples, comme des listVars, listProps, s.product, eVars de marchandisage, etc. Valeur par défaut = non coché. |
| | Afficher les infobulles | Détermine si les infobulles contenant les données de nœud s’affichent lorsque vous passez la souris sur des nœuds individuels dans une visualisation de flux. |
| | Nombre de colonnes | Détermine le nombre de colonnes souhaité dans le diagramme Flux. |
| | Éléments développés par colonne | Nombre d’éléments à inclure dans chaque colonne. |
| **Graphiques empilés** | | |
| | 100 % empilé | Ce paramètre appliqué aux graphiques à zones empilées, à barres empilées ou à barres horizontales empilées offre un aperçu « 100 % empilé » du diagramme. <p>Pour plus d’informations, consultez [Barres et barres empilées](/help/analyze/analysis-workspace/visualizations/bar.md).</p> |
| **[Histogramme](/help/analyze/analysis-workspace/visualizations/histogram.md)** | | |
| | Nombre d’intervalles | Sélectionnez le nombre de plages de données (intervalles) dans la visualisation. Il ne peut pas y avoir plus de 50 intervalles. <p>Pour plus d’informations, consultez [Histogramme](/help/analyze/analysis-workspace/visualizations/histogram.md).</p> |
| | Méthode de comptage | Choisissez l’une des options suivantes : <ul><li>Accès</li><li>Visite</li><li>Visiteur</li></ul> <p>Par exemple, lorsque vous l’utilisez avec les pages vues, vous pouvez choisir les pages vues par visiteur, les pages vues par visite ou les pages vues par accès. Pour l’accès, la mesure « Occurrences » est utilisée comme mesure de l’axe Y dans un tableau à structure libre.</p> |
| **[Carte](/help/analyze/analysis-workspace/visualizations/map-visualization.md)** | | |
| | Traçage de la dimension | <ul><li>Latitude/longitude mobile</li><li>Dimension géographique</li></ul> |
| | Type de carte | <ul><li>Bulles</li><li>Carte thermique</li></ul> |
| | Thème de couleur | Faites votre choix parmi un corail, des rouges, des verts, des bleus, une carte thermique et positif/négatif. |
| | Style de carte | Faites votre choix parmi de base, des rues, lumineux, clair, foncé et satellite. |
| **[Synthèse des modifications](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Valeur | <!-- Seem to be basically the same options as in "Number value options" --> <ul><li>Changement en pourcentage</li><li>Différence brute</li></ul> |
| | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Synthèse des modifications. |
| | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Synthèse des modifications. |
| | Abréger la valeur | Lorsque cette option est sélectionnée, spécifiez le nombre de décimales. |
| **[Synthèse des chiffres](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)** | | |
| | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Synthèse des chiffres. |
| | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Synthèse des chiffres. |
| | Synthèse des valeurs par | Choisissez parmi Max, Min, Moyenne, Médiane et Somme. |
| | Abréger la valeur | Lorsque cette option est sélectionnée, spécifiez le nombre de décimales. |
| **[Treemap](/help/analyze/analysis-workspace/visualizations/treemap.md)** | | |
| | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Treemap. |
| | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X dans la visualisation Treemap. Cela peut s’avérer utile si vous disposez d’un jeu de données volumineux. |
| **[Venn](/help/analyze/analysis-workspace/visualizations/venn.md)** | | |
| | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Venn. |
| **[Dispersion](/help/analyze/analysis-workspace/visualizations/scatterplot.md)** | | |
| | Pourcentages | Affiche les valeurs en pourcentages pour les visualisations Dispersion. |
| | Légende visible | Permet de masquer le texte de légende détaillé pour la visualisation Dispersion. |
| | Nombre max d’éléments | Réduit le nombre d’éléments sur l’axe X dans la visualisation Dispersion. Cela peut s’avérer utile si vous disposez d’un jeu de données volumineux. |
| | Ancrer l’axe Y sur zéro | Si toutes les valeurs tracées sur le graphique sont considérablement au-dessus de zéro, le bas de l’axe Y devient NON-ZÉRO par défaut. Si vous cochez cette case, l’axe Y est forcé à zéro (et le graphique est à nouveau dessiné). |

## Restaurer les préférences par défaut

Vous pouvez restaurer toutes vos préférences utilisateur aux valeurs par défaut du système. Cette option n’affecte pas les préférences administrateur sous l’onglet **[!UICONTROL Société]**. Cette action ne peut pas être annulée.

1. Dans Adobe Analytics, sélectionnez [!UICONTROL **Composants**] **>** [!UICONTROL **Préférences**] dans le menu supérieur. Vous pouvez aussi sélectionner **[!UICONTROL Projet]** > **[!UICONTROL Paramètres utilisateur]** dans le menu Workspace.

1. Dans le coin supérieur droit, sélectionnez **[!UICONTROL Restaurer les valeurs par défaut]**.

1. Sélectionnez **[!UICONTROL Restaurer les paramètres par défaut]** dans **[!UICONTROL Restaurer les paramètres par défaut du système]**.

## [!UICONTROL Thème sombre]

Si vous préférez afficher un arrière-plan sombre pour votre interface utilisateur de Customer Journey Analytics, vous pouvez activer le [!UICONTROL Thème sombre].

1. Cliquez sur lʼicône dʼutilisateur ou d’utilisatrice Experience Cloud en haut à droite.

   ![thème-sombre](assets/dark-theme.png)

1. Activez le **[!UICONTROL Thème sombre]**.

