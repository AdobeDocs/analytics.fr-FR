---
description: Vous pouvez attribuer un nom à votre rapport et configurer le mode d’affichage des en-têtes de lignes et de colonnes. Le lien Options de format est disponible pour les types Disposition personnalisée et Disposition croisée dynamique.
title: Mise en forme des en-têtes d’affichage
topic: Report builder
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mise en forme des en-têtes d’affichage

Vous pouvez attribuer un nom à votre rapport et configurer le mode d’affichage des en-têtes de lignes et de colonnes. Le lien Options de format est disponible pour les types Disposition personnalisée et Disposition croisée dynamique.

1. Créez une requête sur le [!UICONTROL Request Wizard: Step 1].
1. Cliquez sur **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2] form, add dimensions and metrics data to the request, as desired.
1. Cliquez sur **[!UICONTROL Format Options]**.
1. Configure the [!UICONTROL Display] options:

   | Élément | Description |
   |--- |--- |
   | Nom de rapport | Affiche soit le nom du type de rapport sélectionné dans l’arborescence du formulaire Assistant Requête : Étape 1 (par exemple, [!DNL Traffic Report]) ou le nom saisi dans le champ [!DNL Name this Request]. |
   | Paramètres des filtres | Affiche les filtres des dimensions (un filtre de recherche, par exemple). |
   | Segment | Affiche le paramètre de segment. |
   | récence des données | Affiche les paramètres de récence des données. Par exemple :    Récence des données : Pages vues (il y a 1,5 heure), Sorties (il y a 30 minutes)  Voir la section [Options](/help/analyze/report-builder/options.md) pour plus d’informations sur le traitement des données actives. |

   Regarding display order, if the [!UICONTROL Row Label] grid (on Step 2) contains an item, it is displayed first in the request. If not, the system uses the first item present in the [!UICONTROL Column Label] grid. If no row or column items exist, the first item in the [!UICONTROL Metrics] grid is displayed.

   **Afficher les en-têtes des lignes et des colonnes** : ajoute une ligne et une colonne pour afficher ces éléments.

   Dans la version 3.11, vous pouviez afficher un en-tête pour chaque élément. La version 4, quant à elle, affiche soit l’ensemble des éléments, soit aucun. Si vous ouvrez, dans la version 4.x, une requête créée dans la version 3.11, le Créateur de rapports vous invite, au cours de l’étape 2 de l’Assistant, à mettre à jour la plage d’une cellule pour les éléments dépourvus d’un en-tête.

   **Modifier les en-têtes en filtres automatiques Excel** : ce paramètre est disponible uniquement si des en-têtes de lignes et de colonnes sont affichés. Il crée un filtre automatique Excel et l’ajoute aux données que le Créateur de rapports renvoie pour cette requête.

   >[!NOTE]
   >
   >Excel ne prend en charge qu’un seul filtre automatique par feuille de calcul. Si vous créez un filtre automatique dans une feuille de calcul qui en comporte déjà un, Excel ne vous avertit pas que le filtre existant va être remplacé.

   **Effectuer un synopsis automatique** : transforme la date renvoyée par le Créateur de rapports du mode Liste en mode Arborescence.

   **Donnez un nom à cette requête** : permet de saisir un nom personnalisé pour la requête ou d’utiliser le nom par défaut sélectionné à l’étape 1 de l’Assistant. Ce nom apparaît comme [!UICONTROL Report] nom dans la [!UICONTROL Request Manager]. See [Name a Request](/help/analyze/report-builder/layout/name-a-request.md).

1. Cliquez sur **[!UICONTROL OK]**.
