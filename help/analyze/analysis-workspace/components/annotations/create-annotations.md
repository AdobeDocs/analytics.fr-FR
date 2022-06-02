---
title: Création d’annotations
description: Comment créer des annotations dans l’espace de travail.
role: User, Admin
feature: Annotations
exl-id: 3cf9a0fd-11c9-4375-8bbe-9551ba86f86d
source-git-commit: 20ab0e9728969c4cc11227a1255e41e3d1a1540f
workflow-type: ht
source-wordcount: '590'
ht-degree: 100%

---

# Création d’annotations

1. Pour créer des annotations, plusieurs moyens s’offrent à vous :

| Méthode de création | Détails |
| --- | --- |
| **Accédez à [!UICONTROL Analytics] > [!UICONTROL Composants] > [!UICONTROL Annotation].** | La page du gestionnaire d’annotations s’ouvre. Cliquez sur [!UICONTROL Créer une annotation] pour ouvrir le [!UICONTROL créateur d’annotations]. |
| **Cliquez avec le bouton droit sur un point d’un tableau.** | [!UICONTROL Le créateur d’annotations] s’ouvre. Notez que, par défaut, les annotations créées de cette manière sont visibles uniquement dans le projet dans lequel elles ont été créées. Mais vous pouvez les rendre accessibles à tous les projets. Remarquez également que la ou les dates et les mesures, etc., ont déjà été remplies.<p>![](assets/annotate-table.png) |
| **Cliquez avec le bouton droit sur un point d’un graphique [!UICONTROL linéaire].** | Le [!UICONTROL créateur d’annotations] s’ouvre. Notez que, par défaut, les annotations créées de cette manière sont visibles uniquement dans le projet dans lequel elles ont été créées. Mais vous pouvez les rendre accessibles à tous les projets. Remarquez également que la ou les dates et les mesures, etc., ont déjà été remplies.<p>![](assets/annotate-line.png) |
| **Dans l’espace de travail, accédez à [!UICONTROL Composants] > [!UICONTROL Créer une annotation].** | Le [!UICONTROL créateur d’annotations] s’ouvre. |
| **Utilisez cette touche de raccourci** pour ouvrir le créateur d’annotations : (PC) `ctrl` `shift` + O, (Mac) `shift` + `command` + O. | Remarquez qu’en utilisant la touche de raccourci pour créer une annotation, vous créez une annotation d’un seul jour pour la date actuelle, sans aucune portée présélectionnée (mesures ou dimensions). |

{style=&quot;table-layout:auto&quot;}

1. Renseignez les éléments du [!UICONTROL créateur d’annotations].

   ![](assets/ann-builder.png)

   | Élément | Description |
   | --- | --- |
   | [!UICONTROL Annotation réservée au projet] | Par défaut, l’annotation s’applique au projet en cours. En cochant cette case, vous pouvez faire en sorte que l’annotation s’affiche dans tous les projets que vous détenez.<p> ![](assets/project-only.png) |
   | [!UICONTROL Titre] | Nommez l’annotation, par exemple : « Memorial Day ». |
   | [!UICONTROL Description] | (Facultatif) Fournissez une description de l’annotation, par exemple : « Jour férié observé aux États-Unis ». |
   | [!UICONTROL Balises] | (Facultatif) Organisez les annotations en créant ou en appliquant une balise. |
   | [!UICONTROL Date appliquée] | Sélectionnez la date ou la période qui doit être indiquée pour que l’annotation soit visible. |
   | [!UICONTROL Couleur] | Appliquez une couleur à l’annotation. L’annotation apparaît dans le projet avec la couleur sélectionnée. Vous pouvez utiliser la couleur pour classer les annotations comme les jours fériés, les événements externes, les problèmes de suivi, etc. |
   | [!UICONTROL Portée] | (Facultatif) Faites glisser et déposez les mesures qui déclenchent l’annotation. Faites ensuite glisser et déposez toutes les dimensions ou tous les segments qui servent de filtres (c’est-à-dire avec lesquels l’annotation sera visible). Si vous n’indiquez pas de portée, l’annotation s’applique à toutes vos données.<ul><li>**[!UICONTROL L’une de ces mesures est présente]** : faites glisser et déposez jusqu’à 10 mesures qui déclencheront l’affichage de l’annotation.</li><li>**[!UICONTROL Avec tous ces filtres]** : faites glisser et déposez jusqu’à 10 dimensions ou segments qui filtreront lorsque l’annotation s’affichera.</li></ul><p>Cas d’utilisation : une eVar a cessé de collecter des données pour une période spécifique. Faites glisser l’eVar dans la boîte de dialogue **[!UICONTROL L’une de ces mesures est présente]**. Ou votre mesure [!UICONTROL Visites] n’indique aucune donnée. Suivez le même processus.<p>**Remarque :** toute annotation appliquée à un composant, qui est ensuite utilisé comme élément d’une mesure calculée ou d’une définition de segment, n’hérite PAS automatiquement de l’annotation. La mesure calculée concernée doit également être ajoutée à la portée pour afficher l’annotation. Toutefois, une nouvelle annotation doit être créée pour tout segment que vous souhaitez annoter avec les mêmes informations.<p>Exemple : vous appliquez une annotation à la mesure [!UICONTROL Commandes] un jour spécifique. Vous pouvez ensuite utiliser la mesure [!UICONTROL Commandes] au sein d’une mesure calculée couvrant la même période. La nouvelle mesure calculée n’affichera pas automatiquement l’annotation pour les commandes. Pour que l’annotation s’affiche, la mesure calculée doit également être ajoutée à la portée. |
   | [!UICONTROL Appliquer à toutes les suites de rapports] | Par défaut, l’annotation s’applique à la suite de rapports d’origine. En cochant cette case, vous pouvez faire en sorte que l’annotation s’applique à toutes les suites de rapports de l’entreprise. |

   {style=&quot;table-layout:auto&quot;}

1. Cliquez sur **[!UICONTROL Enregistrer]**.
