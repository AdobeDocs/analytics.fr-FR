---
title: Utilisation des résultats mis en cache pour un chargement plus rapide dans Analysis Workspace
description: Activez un paramètre de projet dans Analysis Workspace qui met en cache les résultats pendant 12 heures afin que les projets se chargent instantanément. Actualisez à tout moment pour afficher les dernières données.
feature: Workspace Basics
hide: true
role: User
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: c457b289-f974-4a67-a5b6-dec3ffa77675
    internal-label: Workspace basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 1cbafc8cee90cbf213b8cd68768e017ff24d268a
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 5%
---

# Utiliser des résultats mis en cache dans les projets Workspace

>[!CONTEXTUALHELP]
>id="aa_project_cached_results"
>title="Utiliser des résultats mis en cache pour un chargement plus rapide"
>abstract="Lorsqu’ils sont activés, les résultats se chargent instantanément pendant 12 heures après la première ouverture d’un projet par un utilisateur ou une utilisatrice, ou leur diffusion selon un planning. Quiconque ouvre le projet pendant cette période voit les mêmes résultats, même si les données continuent de circuler en arrière-plan. Pour charger les derniers résultats, actualisez les panneaux individuels ou l’ensemble du projet."

{{release-limited-testing}}

Vous pouvez configurer des projets Analysis Workspace pour qu’ils affichent les résultats mis en cache pendant 12 heures, ce qui permet aux résultats de se charger instantanément pour toute personne qui ouvre le projet après son chargement initial.

Les projets peuvent être initialement chargés par un utilisateur qui ouvre le projet ou par une diffusion de projet planifiée.

## Présentation des résultats mis en cache dans un projet

### Lorsque les résultats sont mis en cache

La première fois que le projet se charge, les résultats se chargent à une vitesse normale et Analysis Workspace les met en cache pendant 12 heures. Cela se produit lorsque :

* Quelqu’un ouvre le projet

* Le projet s’exécute pour une diffusion planifiée

Par exemple, si la diffusion d’un projet est planifiée à 6 heures du matin, les résultats sont mis en cache jusqu’à 18 heures. Toute personne ouvrant le projet entre 6 h et 18 h voit les résultats se charger instantanément, y compris la première personne à l’ouvrir.

Au bout de 12 heures, les résultats mis en cache expirent. Au prochain chargement du projet, qu’un utilisateur l’ouvre ou qu’une diffusion planifiée s’exécute, les résultats se chargent à une vitesse normale et une nouvelle fenêtre de 12 heures démarre.

### Quels résultats sont mis en cache

#### Le projet est initialement mis en cache avec sa configuration d’origine

Analysis Workspace met en cache les résultats du projet tel qu’il a été configuré à l’origine, avec ses suites de rapports sélectionnées, les segments appliqués, les périodes, les sélections de listes déroulantes de panneaux, etc. Toutes les personnes qui ouvrent le projet voient ces résultats mis en cache.

Si une personne modifie la configuration du projet lors de l’affichage du projet mis en cache, les résultats se chargent normalement (et non instantanément) et [&#x200B; une nouvelle variation du projet est mise en cache](#project-variations-are-cached-as-the-project-is-modified).

#### Les variations du projet sont mises en cache au fur et à mesure que le projet est modifié

Une nouvelle variante du projet est créée lorsque quelqu’un modifie sa configuration d’origine, par exemple en sélectionnant un élément dans un menu déroulant de panneau, en appliquant un segment, en modifiant une période ou en modifiant la suite de rapports sélectionnée.

Une nouvelle variation se charge à vitesse normale la première fois. Ensuite, ses résultats sont également mis en cache, de sorte que toute personne qui charge la même variation voit les résultats instantanément.

Tenez compte des points suivants :

* Analysis Workspace met en cache chaque variation d’un projet chargé par une personne. Il ne met pas en cache toutes les variantes possibles d’un projet.

* La mise en cache d’une nouvelle variation ne remplace ni n’invalide les résultats déjà mis en cache. Le projet d’origine est mis en cache avec d’autres variations que les personnes ont chargées.

>[!BEGINSHADEBOX]

**Exemple de scénario**

Supposons qu’un projet Performances de campagne globale comprenne des segments pour différentes régions et qu’il soit programmé pour une diffusion à 6 h 00 :

| Heure | Action | Vitesse de charge |
| --- | --- | --- |
| 6 h 00 | Diffusion planifiée du projet | Normale (les résultats sont mis en cache pour une utilisation ultérieure) |
| 07:06 | L’utilisateur A ouvre le projet | Instantané |
| 07:07 | L’utilisateur A applique le segment Amériques | Normale (les résultats sont mis en cache pour une utilisation ultérieure) |
| 08:01 | L’utilisateur B ouvre le projet | Instantané |
| 08:05 | L’utilisateur B applique le segment Amériques | Instantané |
| 08:12 | L’utilisateur B applique le segment EMEA | Normale (les résultats sont mis en cache pour une utilisation ultérieure) |

>[!ENDSHADEBOX]

### Modifications entraînant l’actualisation des résultats mis en cache avec le chargement suivant du projet

Les modifications suivantes apportées à la configuration sous-jacente d’un projet entraînent l’actualisation des résultats par Analysis Workspace la prochaine fois qu’un utilisateur ouvre le projet, même si la période de 12 heures n’a pas expiré :

* Modifications apportées à une définition de [mesure calculée](/help/components/calculated-metrics/cm-overview.md) utilisée dans le projet

* Modifications apportées à une définition de segment utilisée dans le projet

Les résultats se chargent à une vitesse normale, puis sont mis en cache, ce qui ouvre une nouvelle fenêtre de 12 heures.

### Qui voit les résultats mis en cache

Les résultats mis en cache s’affichent par défaut pour toutes les personnes qui :

* A accès au projet

* A accès aux suites de rapports utilisées dans le projet

* Charge une variante du projet déjà mise en cache, par exemple une avec les mêmes segments ou sélections de menus déroulants de panneau (pour plus d’informations, voir [Quels résultats sont mis en cache &#x200B;](#what-results-are-cached))

Lors de l’affichage des résultats mis en cache, vous pouvez afficher les données les plus récentes en [actualisant manuellement les résultats](#manually-refresh-results-on-cached-projects).

### Quand laisser les résultats mis en cache désactivés sur un projet

Certains projets dépendent des résultats pour refléter les données les plus récentes à chaque ouverture. Cela est courant pour les projets qui reposent fortement sur des données du même jour, des données arrivant tardivement ou des [classifications](/help/components/classifications/classifications-overview.md) qui sont mises à jour fréquemment.

Laissez les résultats mis en cache désactivés dans votre projet si la plupart des personnes qui accèdent au projet ont besoin de voir :

* **Données du jour en cours**

  Si un projet est mis en cache à 7 h, les résultats n’incluent pas les données qui arrivent après 7 h jusqu’à ce que les résultats mis en cache expirent à 19 h.

* **Données arrivant immédiatement en retard**

  Les données arrivant en retard ont [horodatages](/help/implement/vars/page-vars/timestamp.md) d’une période antérieure, mais arrivent après l’expiration de cette période. Par exemple, les données [Sources de données](/help/import/data-sources/overview.md) d’un centre d’appels peuvent être chargées le lendemain ou une application mobile peut envoyer des accès qu’elle a stockés hors ligne. Les résultats mis en cache n’incluent pas ces données tant qu’ils n’expirent pas.

* **Valeurs de classification mises à jour**

  Les résultats mis en cache continuent d’afficher les valeurs de classification précédentes, telles que les anciens noms de produit, jusqu’à leur expiration.

>[!NOTE]
>
>Si ces besoins ne surviennent qu’occasionnellement, activez les résultats mis en cache et [actualisez le projet manuellement](#manually-refresh-results-on-cached-projects) lorsque vous avez besoin des dernières données.

## Activer les résultats mis en cache pour un projet

Toute personne pouvant mettre à jour les paramètres du projet peut activer les résultats mis en cache. Cela inclut le propriétaire du projet et toute personne disposant du rôle **[!UICONTROL Modifier l’original]** pour le projet. Pour plus d’informations sur les rôles de projet, voir [Partager un rôle de projet spécifique](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-specific-project-role).

>[!IMPORTANT]
>
>Les résultats mis en cache peuvent ne pas convenir si vous devez afficher immédiatement les données du jour en cours, les données arrivées tardivement ou les valeurs de classification mises à jour. Avant d’activer ce paramètre, consultez la section [&#x200B; Quand laisser les résultats mis en cache désactivés sur un projet &#x200B;](#when-to-leave-cached-results-disabled-on-a-project).

Dans le projet Workspace dans lequel vous souhaitez activer les résultats mis en cache pour un chargement plus rapide :

1. Accédez à **[!UICONTROL Projets]** > **[!UICONTROL Informations et paramètres du projet]**.

1. Sélectionnez **[!UICONTROL Utiliser les résultats mis en cache pour accélérer le chargement]**.

1. Sélectionnez **[!UICONTROL Enregistrer]**.

## Afficher les résultats mis en cache dans un projet

Un horodatage s’affiche en haut du projet lorsque les résultats mis en cache sont affichés. La date et l’heure indiquent si tous les résultats sont mis en cache ou seulement certains d’entre eux :

* **[!UICONTROL Affichage des résultats à partir du] [_date et heure_]**: tous les panneaux du projet affichent les résultats en mémoire cache de la date et de l’heure affichées.

* **[!UICONTROL Affichage de certains résultats à partir de] [_date et heure_]**: certains panneaux affichent les résultats mis en cache à partir de la date et de l’heure affichées, tandis que d’autres ont été actualisés plus récemment.

![Date et heure du projet mis en cache](assets/project-cache-timestamp.png)

Les panneaux affichent également un horodatage indiquant le moment où les résultats ont été mis en cache :

* **[!UICONTROL Affichage des résultats à partir de] [_date et heure_]**: le panneau affiche les résultats mis en cache à partir de la date et de l’heure affichées.

  >[!NOTE]
  >
  >Cette option n’est pas disponible pendant la phase alpha de la version.

## Actualisation manuelle des résultats sur les projets mis en cache

Seuls les résultats affichés dans le projet sont mis en cache. Les données sous-jacentes continuent de circuler dans Adobe Analytics comme d’habitude.

Pour afficher les dernières données avant l&#39;expiration des résultats mis en cache, vous pouvez actualiser manuellement les résultats d&#39;un projet à tout moment pendant la période de 12 heures. Lorsque vous actualisez l’ensemble du projet, une nouvelle fenêtre de 12 heures commence et toutes les personnes qui ouvrent le projet pendant cette fenêtre voient les résultats actualisés.

Dans le projet Workspace dans lequel vous souhaitez afficher les dernières données, vous pouvez actualiser les résultats pour l’ensemble du projet ou pour un seul panneau.

### Actualiser les résultats pour l’ensemble du projet

Pour charger les derniers résultats pour tous les panneaux et démarrer une nouvelle fenêtre de 12 heures :

1. Sélectionnez l’icône **[!UICONTROL Actualiser]** ![Actualiser](/help/assets/icons/Refresh.svg) en haut du projet à côté de la date et de l’heure du projet.

### Actualiser les résultats pour un seul panneau

>[!NOTE]
>
>Cette option n’est pas disponible pendant la phase alpha de la version.

Pour charger les derniers résultats pour un seul panneau uniquement :

1. Sélectionnez l’icône **[!UICONTROL Actualiser]** ![Actualiser](/help/assets/icons/Refresh.svg) en regard de la date et de l’heure d’un panneau.

