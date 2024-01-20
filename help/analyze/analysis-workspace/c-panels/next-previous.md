---
description: Panneau qui affiche les éléments de dimension précédents ou suivants pour une dimension spécifique.
title: Panneau d’éléments suivant ou précédent
feature: Panels
role: User, Admin
exl-id: 9f2f8134-2a38-42bb-b195-5e5601d33c4e
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 5%

---

# Panneau d’éléments suivant ou précédent

Ce panneau contient plusieurs tableaux et visualisations pour identifier facilement l’élément de dimension précédent ou suivant pour une dimension spécifique. Par exemple, vous souhaitez peut-être explorer les pages les plus consultées par les clients après avoir visité la page d’accueil.

## Accès au panneau

Vous pouvez accéder au panneau à partir de la fonction [!UICONTROL Rapports] ou dans [!UICONTROL Workspace].

| Point d’accès | Description |
| --- | --- |
| [!UICONTROL Rapports] | <ul><li>Le panneau est déjà déposé dans un projet.</li><li>Le rail de gauche est réduit.</li><li>Si vous avez sélectionné [!UICONTROL Page suivante], les paramètres par défaut ont déjà été appliqués, comme [!UICONTROL Page] pour [!UICONTROL Dimension], et la page supérieure comme [!UICONTROL Élément de Dimension], [!UICONTROL Suivant] pour [!UICONTROL Direction] et [!UICONTROL Visite] pour [!UICONTROL Conteneur]. Vous pouvez modifier tous ces paramètres.</li></ul>![Panneau Suivant/Précédent](assets/next-previous.png) |
| Workspace | Créez un projet et sélectionnez l’icône Panneau dans le rail de gauche. Faites ensuite glisser le [!UICONTROL Élément suivant ou précédent] au-dessus du tableau à structure libre. Notez que la variable [!UICONTROL Dimension] et [!UICONTROL Élément de Dimension] Les champs ne sont pas renseignés. Sélectionnez une dimension dans la liste déroulante. [!UICONTROL Éléments de Dimension] sont renseignées en fonction de la variable [!UICONTROL dimension] vous avez choisi. L’élément de dimension supérieur est ajouté, mais vous pouvez sélectionner un autre élément. Les valeurs par défaut sont Suivant et Visiteur. Vous pouvez également les modifier.<p>![Panneau Suivant/Précédent](assets/next-previous2.png) |

{style="table-layout:auto"}

## Entrées de panneau {#Input}

Vous pouvez configurer la variable [!UICONTROL Élément suivant ou précédent] panneau à l’aide des paramètres d’entrée suivants :

| Paramètre | Description |
| --- | --- |
| Zone de dépôt de segment (ou autre composant) | Vous pouvez faire glisser et déposer des segments ou d’autres composants pour filtrer davantage les résultats du panneau. |
| Dimension | Dimension pour laquelle vous souhaitez explorer les éléments suivants ou précédents. |
| Élément de Dimension | L’élément spécifique au centre de votre requête suivante/précédente. |
| Direction | Indiquez si vous recherchez le [!UICONTROL Suivant] ou le [!UICONTROL Précédent] élément de dimension. |
| Conteneur | [!UICONTROL Visite] ou [!UICONTROL Visiteur] (par défaut) déterminez la portée de votre requête. |

{style="table-layout:auto"}

Cliquez sur **[!UICONTROL Build]** pour créer le panneau.

## Sortie de panneau {#output}

La variable [!UICONTROL Élément suivant ou précédent] renvoie un riche ensemble de données et de visualisations pour vous aider à mieux comprendre les occurrences qui suivent ou précèdent des éléments de dimension spécifiques.

![Sortie de panneau suivante/précédente](assets/next-previous-output.png)

![Sortie de panneau suivante/précédente](assets/next-previous-output2.png)

| Visualisation | Description |
| --- | --- |
| Barre horizontale | Répertorie les éléments suivants (ou précédents) en fonction de l’élément de dimension que vous avez choisi. Le survol d’une barre individuelle met en surbrillance l’élément correspondant dans le tableau à structure libre. |
| Numéro de résumé | Numéro de résumé de haut niveau de toutes les occurrences d’élément de dimension précédente ou suivante pour le mois en cours (à ce jour). |
| Tableau à structure libre | Répertorie les éléments suivants (ou précédents) en fonction de l’élément de dimension choisi, dans un format de tableau. Par exemple, les pages les plus populaires (par occurrence) sur lesquelles les utilisateurs se sont rendus après (ou avant) la page d’accueil ou la page de l’espace de travail. |

{style="table-layout:auto"}
