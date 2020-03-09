---
description: Décrit les étapes d’application de filtres à un rapport de cheminement.
title: Filtrage d’un rapport de cheminement à l’aide de l’Assistant Requête
topic: Report builder
uuid: 9b22d5b5-7ae8-49a2-90ae-0c1075562bbe
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Filtrage d’un rapport de cheminement à l’aide de l’Assistant Requête

Décrit les étapes d’application de filtres à un rapport de cheminement.

Cet exemple utilise Chemins > Section Site.

1. Dans le Report Builder d’Adobe, cliquez sur **[!UICONTROL Créer]** pour ouvrir l’Assistant Requête.
1. Sélectionnez la suite de rapports appropriée.
1. Dans l’arborescence de gauche, sélectionnez **[!UICONTROL Chemins]** > **[!UICONTROL Section Site]** > **[!UICONTROL Section Site - Tracés]**.

   ![](assets/site_section_path_1.png)

1. Indiquez la ou les dates appropriée(s).
1. Cliquez sur **[!UICONTROL Suivant]**.
1. À l’étape 2 de l’Assistant, sous **[!UICONTROL Libellés de lignes]**, cliquez sur le lien **[!UICONTROL Premiers 1-10 (modèle appliqué)]**. Dans un rapport de cheminement, un modèle est appliqué par défaut.

   ![](assets/site_section_path_2.png)

1. Sélectionnez l’option **[!UICONTROL Filtrer]**.

   ![](assets/filter_option.png)

1. Dans la boîte de dialogue **[!UICONTROL Définir le schéma de tracé de « Chemins > Section Site »]**, vous pouvez indiquer
   1. l’ordre de classement de début du premier rapport ;
   1. le nombre d’entrées que vous souhaitez afficher dans ce rapport.
1. Cliquez sur **[!UICONTROL Modifier]** pour définir un modèle de chemin.
1. Si vous souhaitez un modèle personnalisé, faites glisser-déposer n’importe quel **[!UICONTROL Objet modèle]** dans la liste de gauche vers le **[!UICONTROL Canevas du Créateur de modèles (Pattern Build Canvas)]** à droite.

   ![](assets/custom_pattern.png)

1. Vous pouvez également sélectionner un modèle prédéfini dans la liste déroulante **[!UICONTROL Sélectionner un modèle]** et le modifier. Vous trouverez ci-dessous les motifs disponibles :

   ![](assets/select_a_pattern.png)

   Certains de ces motifs sont spécifiques au Créateur de rapports : Modèle Élément suivant du chemin d’entrée, Modèle Élément précédent du chemin de sortie, Modèle Élément suivant.
1. Pour modifier un modèle prédéfini,
   1. sélectionnez-le. Par exemple, sélectionnez le **[!UICONTROL Modèle de site de sortie]** : ![](assets/exited_site_pattern.png)

   1. Maintenant, vous devez définir le chemin de la section du site que l’utilisateur suit avant de sortir. Cliquez sur **[!UICONTROL Éléments(s) particulier(s) : 0 sélectionné(s)]**. Vous pouvez définir ce chemin en effectuant une sélection à partir d’une plage de cellules (si vous modifiez une requête existante) ou en effectuant une sélection depuis une liste de sections.
   1. Pour effectuer une sélection depuis une plage de cellules d’une requête précédente, sélectionnez **[!UICONTROL À partir de la plage de cellules]** et cliquez sur l’icône de sélecteur de cellules. Puis, sélectionnez les cellules depuis le rapport. ![](assets/choose_site_section_paths.png)

   1. Pour effectuer la sélection depuis une liste de sections de site, sélectionnez **[!UICONTROL À partir de la liste]** et cliquez sur **[!UICONTROL Ajouter]**.
   1. Déplacez des éléments de la colonne **[!UICONTROL Éléments disponibles]** vers la colonne **[!UICONTROL Éléments sélectionnés]** en les sélectionnant et en cliquant sur la flèche orange. Puis, cliquez sur **[!UICONTROL OK]**. ![](assets/move_site_section_elements.png)

   1. Pour enregistrer le modèle que vous venez de définir, cliquez sur **[!UICONTROL Enregistrer]**.
   1. Cliquez à trois reprises sur **[!UICONTROL OK]**, puis cliquez sur **[!UICONTROL Terminer]**. La requête de chemin filtrée est à présent générée.
