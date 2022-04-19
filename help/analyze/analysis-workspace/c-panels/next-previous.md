---
description: Panneau qui affiche les éléments de dimension précédents ou suivants pour une dimension spécifique.
title: Panneau d’élément suivant ou précédent
feature: Panels
role: User, Admin
source-git-commit: d4106324f6716139731cc6bd948ef06b35303620
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 8%

---


# Panneau d’élément suivant ou précédent

Le [!UICONTROL Élément suivant ou précédent] a commencé en tant que rapport dans Reports &amp; Analytics, sous [!UICONTROL Rapports] > [!UICONTROL Le plus populaire] > [!UICONTROL Page suivante/page précédente]. Ce panneau Workspace contient plusieurs tableaux et visualisations pour identifier facilement l’élément de dimension précédent ou suivant pour une dimension spécifique. Par exemple : 
        

## Accès au panneau

Vous pouvez accéder au panneau à partir de la fonction [!UICONTROL Rapports] ou dans [!UICONTROL Workspace].

| Point d’accès | Description |
| --- | --- |
| [!UICONTROL Rapports] | <ul><li>Le panneau est déjà déposé dans un projet.</li><li>Le rail de gauche est réduit.</li><li>Si vous avez sélectionné [!UICONTROL Page suivante], les paramètres par défaut ont déjà été appliqués, comme [!UICONTROL Page] pour [!UICONTROL Dimension], et la page supérieure comme [!UICONTROL Élément de Dimension], [!UICONTROL Suivant] pour [!UICONTROL Direction] et [!UICONTROL Visite] pour [!UICONTROL Conteneur]. Vous pouvez modifier tous ces paramètres.</li></ul>![Panneau Suivant/Précédent](assets/next-previous.png) |
| Workspace | Créez un projet et sélectionnez l’icône Panneau dans le rail de gauche. Faites ensuite glisser le [!UICONTROL Élément suivant ou précédent] au-dessus du tableau à structure libre. Notez que la variable [!UICONTROL Dimension] et [!UICONTROL Élément de Dimension] Les champs ne sont pas renseignés. Sélectionnez une dimension dans la liste déroulante. [!UICONTROL Éléments de Dimension] sont renseignées en fonction de la variable [!UICONTROL dimension] vous avez choisi. L’élément de dimension supérieur est ajouté, mais vous pouvez sélectionner un autre élément. Les valeurs par défaut sont Suivant et Visiteur. Vous pouvez également les modifier.<p>![Panneau Suivant/Précédent](assets/next-previous2.png) |

{style=&quot;table-layout:auto&quot;}

## Entrées de panneau {#Input}

Vous pouvez configurer la variable [!UICONTROL Élément suivant ou précédent] panneau à l’aide des paramètres d’entrée suivants :

| Paramètre | Description |
| --- | --- |
| Zone de dépôt de segment (ou autre composant) | Vous pouvez faire glisser et déposer des segments ou d’autres composants pour filtrer davantage les résultats du panneau. |
| Dimension | Dimension pour laquelle vous souhaitez explorer les éléments suivants ou précédents. |
| Élément Dimension | L’élément spécifique au centre de votre requête suivante/précédente. |
| Direction | Indiquez si vous recherchez le [!UICONTROL Suivant] ou le [!UICONTROL Précédent] élément de dimension. |
| Conteneur | [!UICONTROL Visite] ou [!UICONTROL Visiteur] (par défaut) déterminez la portée de votre requête. |

{style=&quot;table-layout:auto&quot;}

Cliquez sur **[!UICONTROL Build]** pour créer le panneau.

## Sortie de panneau {#output}

Le [!UICONTROL Élément suivant ou précédent] renvoie un riche ensemble de données et de visualisations pour vous aider à mieux comprendre les occurrences qui suivent ou précèdent des éléments de dimension spécifiques.

![Sortie de panneau suivante/précédente](assets/next-previous-output.png)

![Sortie de panneau suivante/précédente](assets/next-previous-output2.png)

| Visualisation | Description |
| --- | --- |
| Barre horizontale | Répertorie les éléments suivants (ou précédents) en fonction de l’élément de dimension choisi. Le survol d’une barre individuelle met en surbrillance l’élément correspondant dans le tableau à structure libre. |
| Numéro de résumé | Numéro de résumé de haut niveau de toutes les occurrences d’élément de dimension précédente ou suivante pour le mois en cours (à ce jour). |
| Tableau à structure libre | Répertorie les éléments suivants (ou précédents) en fonction de l’élément de dimension choisi, dans un format de tableau. Par exemple, les pages les plus populaires (par occurrence) sur lesquelles les utilisateurs se sont rendus après (ou avant) la page d’accueil ou la page de l’espace de travail. |

{style=&quot;table-layout:auto&quot;}
