---
description: Découvrez comment nommer votre rapport et comment afficher les en-têtes de lignes et de colonnes.
title: Formatage des en-têtes d’affichage
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
source-git-commit: d218d07ec16e981d7e148092b91fbbd5711e840f
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 71%

---

# Mise en forme des en-têtes d’affichage

Vous pouvez attribuer un nom à votre rapport et configurer le mode d’affichage des en-têtes de lignes et de colonnes. Le lien Options de format est disponible pour les types Disposition personnalisée et Disposition croisée dynamique.

1. Créez une requête dans la fenêtre [!UICONTROL Assistant Requête : Étape 1].
1. Cliquez sur **[!UICONTROL Suivant]**.
1. Sur le formulaire [!UICONTROL Assistant Requête : Étape 2], ajoutez des dimensions et des données de mesure à la requête, suivant vos besoins.
1. Cliquez sur **[!UICONTROL Options de format]**.
1. Configurez les options d’[!UICONTROL affichage] :

   | Élément | Description |
   |--- |--- |
   | Nom de rapport | Affiche soit le nom du type de rapport sélectionné dans l’arborescence du formulaire Assistant Requête : Étape 1 (par exemple, [!DNL Traffic Report]) ou le nom saisi dans le champ [!DNL Name this Request]. |
   | Paramètres des filtres | Affiche les filtres des dimensions (un filtre de recherche, par exemple). |
   | Segment | Affiche le paramètre de segment. |
   | récence des données | Affiche les paramètres de récence des données. Par exemple :    Récence des données : Pages vues (il y a 1,5 heure), Sorties (il y a 30 minutes) Voir [Options](/help/analyze/report-builder/options.md) pour plus d’informations sur le traitement des données actives. |

   En ce qui concerne l’ordre d’affichage, si la grille [!UICONTROL Libellé de ligne] (Étape 2) contient un élément, il s’affiche en premier dans la requête. Dans le cas contraire, le système utilise le premier élément présent dans la grille [!UICONTROL Libellé de colonne]. S’il n’existe aucun élément de ligne ou de colonne, le premier élément de la grille [!UICONTROL Valeurs de mesure] est affiché.

   **Afficher les en-têtes des lignes et des colonnes** : ajoute une ligne et une colonne pour afficher ces éléments.

   Dans la version 3.11, vous pouviez afficher un en-tête pour chaque élément. La version 4, quant à elle, affiche soit l’ensemble des éléments, soit aucun. Si vous avez créé une requête dans la version 3.11 et que vous l’ouvrez dans la version 4.x, Report Builder vous invite, à l’étape 2, à mettre à jour la plage d’une cellule pour les éléments qui ne comportent pas d’en-tête.

   **Modifier les en-têtes en filtres automatiques Excel** : ce paramètre est disponible uniquement si des en-têtes de lignes et de colonnes sont affichés. Ce paramètre crée un filtre automatique Excel et l’ajoute aux retours de Report Builder de données pour cette requête.

   >[!NOTE]
   >
   >Excel ne prend en charge qu’un seul filtre automatique par feuille de calcul. Si vous créez un filtre automatique dans une feuille de calcul qui en comporte déjà un, Excel ne vous avertit pas que le filtre existant va être remplacé.

   **Effectuer un synopsis automatique :** Transforme la date renvoyée par Report Builder du mode Liste en mode Arborescence.

   **Donnez un nom à cette requête** : permet de saisir un nom personnalisé pour la requête ou d’utiliser le nom par défaut sélectionné à l’étape 1 de l’Assistant. Ce nom s’affiche comme nom de [!UICONTROL rapport] dans le [!UICONTROL Gestionnaire de requêtes]. Voir [Nommer une requête](/help/analyze/report-builder/layout/name-a-request.md).

1. Cliquez sur **[!UICONTROL OK]**.
