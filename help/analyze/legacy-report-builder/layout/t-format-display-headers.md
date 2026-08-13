---
description: Découvrez comment nommer votre rapport et configurer l’affichage des en-têtes de ligne et de colonne.
title: Comment formater les en-têtes d’affichage
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
TQID: https://experienceleague.adobe.com/n9LlAH6wZ87xQTOO7SLYSpKudcHxuqqielFv6hJXAYw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 415
ht-degree: 49%

---

# Mise en forme des en-têtes d’affichage

{{legacy-arb}}

Vous pouvez nommer votre rapport et configurer l’affichage des en-têtes de ligne et de colonne. Le lien Options de format est disponible pour les types de disposition Pivot et Personnalisé.

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
   | récence des données | Affiche les paramètres de récence des données. Par exemple : Récence des données : Pages vues (il y a 1,5 heure), Sorties (il y a 30 minutes) Consultez [Options](/help/analyze/legacy-report-builder/options.md) pour plus d’informations sur le traitement des données en cours. |

   En ce qui concerne l’ordre d’affichage, si la grille [!UICONTROL Libellé de ligne] (Étape 2) contient un élément, il s’affiche en premier dans la requête. Dans le cas contraire, le système utilise le premier élément présent dans la grille [!UICONTROL Libellé de colonne]. S’il n’existe aucun élément de ligne ou de colonne, le premier élément de la grille [!UICONTROL Mesures] s’affiche.

   **Afficher les en-têtes des lignes et des colonnes** : ajoute une ligne et une colonne pour afficher ces éléments.

   Dans la version 3.11, vous pouvez afficher un en-tête pour chaque élément. La version 4 affiche tous ces éléments ou aucun d’entre eux. Si vous avez créé une requête dans la version 3.11 et que vous l’ouvrez dans la version 4.x, Report Builder vous invite, à l’étape 2, à mettre à jour la plage d’une cellule pour les éléments auxquels il manque un en-tête.

   **Modifier les en-têtes en filtres automatiques Excel** : ce paramètre est disponible uniquement si des en-têtes de lignes et de colonnes sont affichés. Ce paramètre crée un filtre automatique Excel et l’ajoute aux données renvoyées par Report Builder pour cette requête.

   >[!NOTE]
   >
   >Excel ne prend en charge qu’un seul filtre automatique par feuille de calcul. Si vous créez un filtre automatique dans une feuille de calcul qui en comporte déjà un, Excel ne vous avertit pas que le filtre existant va être remplacé.

   **Effectuer le contour automatique :** transforme la date renvoyée par Report Builder d’une vue de liste en vue d’arborescence.

   **Donnez un nom à cette requête** : permet de saisir un nom personnalisé pour la requête ou d’utiliser le nom par défaut sélectionné à l’étape 1 de l’Assistant. Ce nom apparaît comme le nom [!UICONTROL Rapport] dans le [!UICONTROL Gestionnaire de requêtes]. Voir [Nom d’une requête](/help/analyze/legacy-report-builder/layout/name-a-request.md).

1. Cliquez sur **[!UICONTROL OK]**.
