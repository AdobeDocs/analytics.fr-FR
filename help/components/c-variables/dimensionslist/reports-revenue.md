---
description: Mesure le volume des revenus générés par tous les produits sur une période donnée.
seo-description: Mesure le volume des revenus générés par tous les produits sur une période donnée.
seo-title: Recettes
solution: Analytics
title: Recettes
topic: Présentation
uuid: e 5 b 72798-f 5 c 7-440 d-a 62 d -376 bfd 115 ac 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Recettes

Mesure le volume des revenus générés par tous les produits sur une période donnée.

Utilisez les recettes pour afficher le succès et la tendance généraux de votre site. Vous pouvez également l’utiliser pour choisir des périodes particulièrement prospères pour votre site, pour identifier la source et pour utiliser ces informations pour des campagnes ultérieures.

## Propriétés générales du rapport {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* Il convient de respecter certaines exigences pour que ce rapport puisse collecter correctement des données. Les conditions suivantes doivent être réunies au sein de la même demande d’image :

   * Un événement d’[!UICONTROL achat] doit être déclenché dans la variable `s.events` la variable.

   * Une valeur numérique doit être renseignée dans le champ de prix de la variable `products`.
   * Dans l’exemple ci-dessous, la somme de 35,99 $ est transmise dans le rapport de recettes :

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* Lorsque plusieurs produits sont présents dans la variable [!UICONTROL s.products], tous sont pris en compte dans le rapport de recettes. For example, [!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] would pass $9 in revenue to reporting.

   >[!NOTE]
   >
   >Les recettes n'augmentent pas si la quantité augmente dans un seul produit. For example, [!DNL s.products="Womens;Socks;5;4.50"] does not pass $22.50 into reporting, it passes $4.50. Make sure your implementation passes the total revenue for the quantity listed ( [!DNL s.products="Womens;Socks;5;22.50"]).

* Les [!UICONTROL Recettes] arrondissent le montant total d’une période à la valeur monétaire la plus proche. Elle n’arrondit pas chaque accès ou produit individuellement.
* Comme Analytics arrondit chaque jour à la valeur monétaire entière la plus proche, la comparaison de la somme journalière par rapport au montant mensuel fait apparaître un très léger écart. Cela est dû au fait que le total mensuel ne correspond pas à la somme de chaque jour arrondi. Il s’agit de la somme absolue arrondie à la valeur monétaire entière la plus proche.
* Vous pouvez créer un rapport qui n’arrondit pas les recettes à la valeur monétaire entière la plus proche en utilisant une [mesure calculée](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/).
* L’actualisation de la page peut entraîner une augmentation exagérée des recettes, dans la mesure où ces données sont envoyées à plusieurs reprises à Adobe ; sauf si la variable `purchaseID` est utilisée.
* Les ventilations horaires sont basées sur le fuseau horaire de la suite de rapports.
* Ce rapport ne contient pas d’éléments. Il ne peut être affiché que sous la forme d’un rapport de tendance.
* Vous pouvez appliquer une granularité horaire, quotidienne, hebdomadaire, mensuelle, trimestrielle et annuelle. Ces niveaux de granularité sont disponibles en fonction de la plage de dates des rapports.
* Ce rapport peut être ventilé selon les rapports suivants (en fonction des paramètres de la suite de rapports et de l’entreprise) :

   * Rapport [!UICONTROL Durée de la visite].
   * Rapport [!UICONTROL Pages et sections du site].
   * Rapport [!UICONTROL Vidéos].
   * Rapport [!UICONTROL Profondeur de page et Pages d’entrée].
   * La plupart des rapports [!UICONTROL Sources de trafic], y compris [!UICONTROL Mots-clés de la recherche], [!UICONTROL Moteurs de recherche] et [!UICONTROL Domaines référents].

   * Rapport [!UICONTROL Code de suivi] et tous les rapports de classification associés.
   * Rapport [!UICONTROL Variable Produits] et tous les rapports de classification associés. Également les rapports [!UICONTROL Catégories].

   * Presque tous les rapports [!UICONTROL Profil du visiteur], à l’exception des rapports de [!UICONTROL géosegmentation].

   * Tous les rapports sur les variables [!UICONTROL Conversion personnalisée] avec des sous-relations de base.

* Les ventilations ne sont pas disponibles par heure.

## Propriétés propres aux produits {#section_ED87FFD020634453AABE86B0248BE69B}

* This report can be accessed by going to **[!UICONTROL Conversion]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* Les ventilations [!UICONTROL Sources de trafic] sont disponibles sous [!UICONTROL Méthodes de recherche].

* This report can be accessed by going to **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* Outre les ventilations susmentionnées, des ventilations [!UICONTROL Canal marketing Première touche et Dernière touche] sont disponibles.

* This report can also be accessed by going to **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Purchases]** &gt; **[!UICONTROL Revenue]**.

* Outre les ventilations susmentionnées, vous pouvez utiliser les variables [!UICONTROL Liste] et les variables [!UICONTROL Vidéo] en cours.

* Ce rapport peut utiliser des segments.

* Vous pouvez ventiler chaque élément du rapport selon tous les autres rapports et variables. Vous pouvez ainsi visualiser les ventilations selon la granularité de votre choix.
* Vous pouvez utiliser toutes les mesures de [!UICONTROL conversion] et de [!UICONTROL trafic] avec [!UICONTROL Recettes]. Une attribution différente peut être utilisée avec toutes les mesures de [!UICONTROL conversion].

* Ce rapport peut utiliser plusieurs segments très avancés.

Si ce rapport n’est pas disponible à l’emplacement indiqué, contactez votre administrateur. Il a peut-être modifié la structure de menus ou le nom par défaut afin de mieux répondre aux besoins de votre entreprise.
