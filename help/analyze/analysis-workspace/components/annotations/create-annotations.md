---
title: Création d’annotations
description: Comment créer des annotations dans Workspace.
role: User, Admin
source-git-commit: 6b5fd4e25056d7efbf3119a4d55d2e0a7897965f
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 3%

---


# Création d’annotations

>[!NOTE]
>
>Cette fonctionnalité fait actuellement l’objet de tests limités.

1. Pour créer des annotations, vous avez 4 façons de commencer :

   * Accédez à [!UICONTROL Analytics] > [!UICONTROL Composants] > [!UICONTROL Annotation]. La page Gestionnaire des annotations s’ouvre. Cliquez sur [!UICONTROL Créer une annotation] et le créateur d’annotations s’ouvre.

   * Cliquez avec le bouton droit de la souris sur un point d’un tableau ou d’un graphique linéaire. Le créateur d’annotations s’ouvre. Notez que, par défaut, les annotations créées de cette manière sont visibles uniquement dans le projet dans lequel elles ont été créées. Mais vous pouvez les rendre disponibles pour tous les projets.

   * Dans Workspace, accédez à [!UICONTROL Composants] > [!UICONTROL Créer une annotation]. Le créateur d’annotations s’ouvre.

   * Utilisez cette touche rapide pour ouvrir le créateur d’annotations :
      * (PC) `ctrl` `shift` + o
      * (Mac) `shift` + `command` + o

1. Renseignez les éléments du créateur d’annotations .

   ![](assets/ann-builder.png)

   | Élément | Description |
   | --- | --- |
   | [!UICONTROL Titre] | Nommez l’annotation, par exemple : &quot;Journée commémorative&quot; |
   | [!UICONTROL Description] | (Facultatif) Fournissez une description de l’annotation, par exemple : &quot;Jour férié observé aux Etats-Unis&quot;. |
   | [!UICONTROL Balises] | (Facultatif) Organisez les annotations en créant ou en appliquant une balise. |
   | [!UICONTROL Date appliquée] | Sélectionnez la date ou la période qui doit être présente pour que l’annotation soit visible. |
   | [!UICONTROL Couleur] | Appliquez une couleur à l’annotation. L’annotation apparaît dans le projet avec la couleur sélectionnée. Vous pouvez utiliser la couleur pour classer les annotations (jours fériés, événements externes, problèmes de suivi, etc.). |
   | [!UICONTROL Portée] | (Facultatif) Faites glisser et déposez les mesures qui déclenchent l’annotation. Faites ensuite glisser et déposez les dimensions ou segments qui agissent comme des filtres (c’est-à-dire que l’annotation sera visible avec). Si vous n’indiquez pas de portée, l’annotation s’appliquera à toutes vos données.<ul><li>**[!UICONTROL Toutes ces mesures sont présentes]**: Faites glisser jusqu’à 10 mesures qui déclencheront l’annotation à afficher.</li><li>**[!UICONTROL Avec tous ces filtres]**: Faites glisser jusqu’à 10 dimensions ou segments qui seront filtrés lors de l’affichage de l’annotation.</li></ul><p>Cas pratiques : Un eVar a cessé de collecter des données pour une période spécifique. Faites glisser l’eVar dans le **[!UICONTROL Toutes ces mesures sont présentes]** boîte de dialogue. Ou votre [!UICONTROL Visites] n’indique aucune donnée. Suivez le même processus. |
   | [!UICONTROL Appliquer à toutes les suites de rapports] | Par défaut, l’annotation s’applique à la suite de rapports d’origine. En cochant cette case, vous pouvez appliquer l’annotation à toutes les suites de rapports de l’entreprise. |
   | [!UICONTROL Appliquer à tous les projets] | Par défaut, l’annotation s’applique au projet en cours. En cochant cette case, vous pouvez faire en sorte que l’annotation s’applique à tous les projets que vous détenez. Notez que cette case à cocher s’affiche uniquement lorsque vous lancez le créateur d’annotations à partir du créateur d’annotations ? |

1. Cliquez sur [!UICONTROL Enregistrer].

## Création d’annotations à partir d’une [!UICONTROL Ligne] chart

1. Depuis dans [!UICONTROL Ligne] graphique, sélectionnez un creux ou un pic dans la variable [!UICONTROL Ligne] puis cliquez avec le bouton droit de la souris. Une fenêtre contextuelle appelée **[!UICONTROL Annoter la sélection]** apparaît.

   ![](assets/annotate-line.png)

1. Cliquez sur **[!UICONTROL Annoter la sélection]**. Le créateur d’annotations s’ouvre.

>[!NOTE]
>
>Notez l’annotation Projet uniquement. Cochez la case pour que l’annotation soit disponible pour tous vos projets.

1. Renseignez les détails comme indiqué ci-dessus. Notez que la ou les dates et toute mesure, etc., ont déjà été renseignées.

## Création d’une annotation dans un tableau à structure libre

1. Continuez comme pour un graphique en courbes, mais cliquez avec le bouton droit de la souris sur une ligne du tableau qui doit être annotée.

1. Sélectionner **[!UICONTROL Création d’une annotation d’après la sélection]**.

   ![](assets/annotate-table.png)

1. Renseignez les détails comme indiqué ci-dessus. Notez que la ou les dates et toute mesure, etc., ont déjà été renseignées.
