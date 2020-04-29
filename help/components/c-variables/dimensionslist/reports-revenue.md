---
description: Mesure le volume des revenus générés par tous les produits sur une période donnée.
title: Recettes
topic: Reports
uuid: e5b72798-f5c7-440d-a62d-376bfd115ac8
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Recettes

Mesure le volume des revenus générés par tous les produits sur une période donnée.

Utilisez les recettes pour afficher le succès et la tendance généraux de votre site. Vous pouvez également l’utiliser pour choisir des périodes particulièrement prospères pour votre site, pour identifier la source et pour utiliser ces informations pour des campagnes ultérieures.

## Propriétés générales du rapport {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* Il convient de respecter certaines exigences pour que ce rapport puisse collecter correctement des données. Les conditions suivantes doivent être réunies au sein de la même demande d’image :

   * Un [!UICONTROL purchase] doit se déclencher dans la `s.events` variable.

   * Une `products`valeur numérique doit être renseignée dans le champ de prix de la variable .
   * Dans l’exemple ci-dessous, la somme de 35,99 $ est transmise dans le rapport de recettes :

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* Lorsque plusieurs produits sont présents dans la variable [!UICONTROL s.products], tous sont pris en compte dans le rapport de recettes. Par exemple, [!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] transmet la somme de 9 $ en recettes dans le cadre de la création de rapports.

   >[!NOTE]
   >
   >Les recettes ne sont pas multipliées en cas d’augmentation de la quantité d’un seul produit. Par exemple, [!DNL s.products="Womens;Socks;5;4.50"] ne transmet pas 22,50 $ à la fonction de création de rapports, mais 4,50 $. Assurez-vous que votre implémentation transmet le total des recettes pour la quantité répertoriée ( [!DNL s.products="Womens;Socks;5;22.50"]).

* [!UICONTROL Revenue] arrondit le montant total d’une période à la valeur monétaire la plus proche. Elle n’arrondit pas chaque accès ou produit individuellement.
* Comme Analytics arrondit chaque jour à la valeur monétaire entière la plus proche, la comparaison de la somme journalière par rapport au montant mensuel fait apparaître un très léger écart. Cela est dû au fait que le total mensuel ne correspond pas à la somme de chaque jour arrondi. Il s’agit de la somme absolue arrondie à la valeur monétaire entière la plus proche.
* Vous pouvez créer un rapport qui n’arrondit pas les recettes à la valeur monétaire entière la plus proche en utilisant une  [mesure calculée](https://docs.adobe.com/content/help/fr-FR/analytics/components/calculated-metrics/cm-overview.html).
* L’actualisation de la page peut entraîner une augmentation exagérée des recettes, dans la mesure où ces données sont envoyées à plusieurs reprises à Adobe ; sauf si la variable `purchaseID` est utilisée.
* Les ventilations horaires sont basées sur le fuseau horaire de la suite de rapports.
* Ce rapport ne contient pas d’éléments. Il ne peut être affiché que sous la forme d’un rapport de tendance.
* Vous pouvez appliquer une granularité horaire, quotidienne, hebdomadaire, mensuelle, trimestrielle et annuelle. Ces niveaux de granularité sont disponibles en fonction de la plage de dates des rapports.
* Ce rapport peut être ventilé selon les rapports suivants (en fonction des paramètres de la suite de rapports et de l’entreprise) :

   * [!UICONTROL Time Spent per Visit] rapport.
   * [!UICONTROL Pages and Site Sections] rapport.
   * [!UICONTROL Videos] rapport.
   * [!UICONTROL Page Depth and Entry Pages] rapport.
   * La plupart des [!UICONTROL Traffic Sources]rapports, y compris [!UICONTROL Search Keywords], [!UICONTROL Search Engines]et [!UICONTROL Referring Domains] les rapports.

   * [!UICONTROL Tracking Code] et tous les rapports de classification associés.
   * [!UICONTROL Products variable] et tous les rapports de classification associés. Rapports également [!UICONTROL Categories] .

   * Presque tous les [!UICONTROL Visitor Profile] rapports, à l’exception [!UICONTROL GeoSegmentation] des rapports.

   * Toutes les [!UICONTROL Custom Conversion] variables génèrent des rapports avec des sous-relations de base.

* Les ventilations ne sont pas disponibles par heure.

## Propriétés propres aux produits  {#section_ED87FFD020634453AABE86B0248BE69B}

* Ce rapport est accessible sous **[!UICONTROL Conversion]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* [!UICONTROL Traffic Sources] les ventilations se trouvent sous [!UICONTROL Finding Methods].

* Ce rapport est accessible sous **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* Outre toutes les ventilations répertoriées précédemment, [!UICONTROL First and Last Touch Marketing Channel] des ventilations sont disponibles.

* Vous pouvez également accéder à ce rapport sous **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* In addition to the previously mentioned breakdowns, [!UICONTROL List]variables and the current [!UICONTROL Video] variables can be used.

* Ce rapport peut utiliser des segments.

* Vous pouvez ventiler chaque élément du rapport selon tous les autres rapports et variables. Vous pouvez ainsi visualiser les ventilations selon la granularité de votre choix.
* Vous pouvez utiliser toutes les [!UICONTROL conversion] mesures et [!UICONTROL traffic] les mesures en même temps [!UICONTROL Revenue]. Une attribution différente peut être utilisée avec toutes les mesures de [!UICONTROL conversion].

* Ce rapport peut utiliser plusieurs segments très avancés.

Si ce rapport n’est pas disponible à l’emplacement indiqué, contactez votre administrateur. Il a peut-être modifié la structure de menus ou le nom par défaut afin de mieux répondre aux besoins de votre entreprise.
