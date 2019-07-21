---
description: Vous pouvez attribuer un nom à votre rapport et configurer le mode d’affichage des en-têtes de lignes et de colonnes. Le lien Options de format est disponible pour les types Disposition personnalisée et Disposition croisée dynamique.
seo-description: Vous pouvez attribuer un nom à votre rapport et configurer le mode d’affichage des en-têtes de lignes et de colonnes. Le lien Options de format est disponible pour les types Disposition personnalisée et Disposition croisée dynamique.
seo-title: Mise en forme des en-têtes d'affichage
solution: Analytics
title: Mise en forme des en-têtes d'affichage
topic: Créateur de rapports
uuid: cd 0 e 167 b -9463-43 fd -87 b 2-724 d 1 c 79 de 68
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Mise en forme des en-têtes d'affichage

Vous pouvez attribuer un nom à votre rapport et configurer le mode d’affichage des en-têtes de lignes et de colonnes. Le lien Options de format est disponible pour les types Disposition personnalisée et Disposition croisée dynamique.

1. Créez une requête dans la fenêtre [!UICONTROL Assistant Requête : Étape 1].
1. Click **[!UICONTROL Next]**.
1. Sur le formulaire [!UICONTROL Assistant Requête : Étape 2], ajoutez des dimensions et des données de mesure à la requête, suivant vos besoins.
1. Click **[!UICONTROL Format Options]**.
1. Configurez les options d’[!UICONTROL affichage] : 

   | Élément | Description |
   |--- |--- |
   | Nom de rapport | Displays either the name of the report type you selected from the tree in the  Request Wizard: Step 1 (for example, [!DNL Traffic Report]), or the name you type in the [!DNL Name this Request] field. |
   | Paramètres des filtres | Affiche les filtres des dimensions (un filtre de recherche, par exemple). |
   | Segment | Affiche le paramètre de segment. |
   | récence des données | Affiche les paramètres de récence des données. Par exemple :    Data Recency: Page Views (1.5 hr ago), Exits (30 mins ago)  See [Options](../../../analyze/report-builder/options.md) for information about current data processing. |

   En ce qui concerne l’ordre d’affichage, si la grille [!UICONTROL Libellé de ligne] (Étape 2) contient un élément, il s’affiche en premier dans la requête. Dans le cas contraire, le système utilise le premier élément présent dans la grille [!UICONTROL Libellé de colonne]. S’il n’existe aucun élément de ligne ou de colonne, le premier élément de la grille [!UICONTROL Valeurs de mesure] est affiché.

   **Afficher les en-têtes des lignes et des colonnes** : ajoute une ligne et une colonne pour afficher ces éléments.

   Dans la version 3.11, vous pouviez afficher un en-tête pour chaque élément. La version 4, quant à elle, affiche soit l’ensemble des éléments, soit aucun. Si vous ouvrez, dans la version 4.x, une requête créée dans la version 3.11, le Créateur de rapports vous invite, au cours de l’étape 2 de l’Assistant, à mettre à jour la plage d’une cellule pour les éléments dépourvus d’un en-tête.

   **Modifier les en-têtes en filtres automatiques Excel** : ce paramètre est disponible uniquement si des en-têtes de lignes et de colonnes sont affichés. Il crée un filtre automatique Excel et l’ajoute aux données que le Créateur de rapports renvoie pour cette requête.

   >[!NOTE]
   >
   >Excel ne prend en charge qu'un filtre automatique par feuille de calcul. Si vous créez un filtre automatique dans une feuille de calcul qui en comporte déjà un, Excel ne vous avertit pas que le filtre existant va être remplacé.

   **Effectuer un synopsis automatique** : transforme la date renvoyée par le Créateur de rapports du mode Liste en mode Arborescence.

   **Donnez un nom à cette requête** : permet de saisir un nom personnalisé pour la requête ou d’utiliser le nom par défaut sélectionné à l’étape 1 de l’Assistant. Ce nom s’affiche comme nom de [!UICONTROL rapport] dans le [!UICONTROL Gestionnaire de requêtes]. Reportez-vous à la section [Nommer une requête](../../../analyze/report-builder/layout/name-a-request.md#concept_37277AFB63EA4541B6FD93A5B713D82D).

1. Cliquez sur **[!UICONTROL OK]**.
