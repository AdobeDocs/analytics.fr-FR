---
description: La version 5.2 du Créateur de rapports prend en charge les mesures calculées unifiées d’Adobe Analytics. Entre autres innovations, toutes les mesures calculées sont désormais dotées d’un identifiant global ; elles ne sont plus limitées à une seule suite de rapports.
seo-description: La version 5.2 du Créateur de rapports prend en charge les mesures calculées unifiées d’Adobe Analytics. Entre autres innovations, toutes les mesures calculées sont désormais dotées d’un identifiant global ; elles ne sont plus limitées à une seule suite de rapports.
seo-title: Mesures calculées
title: Mesures calculées
uuid: c 9814894-cda 6-40 ff -8 ec 4-3 ab 2 c 1908 ebc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Mesures calculées

La version 5.2 du Créateur de rapports prend en charge les mesures calculées unifiées d’Adobe Analytics. Entre autres innovations, toutes les mesures calculées sont désormais dotées d’un identifiant global ; elles ne sont plus limitées à une seule suite de rapports.

>[!NOTE]
>
>Les classeurs existants peuvent pointer vers des demandes avec des identifiants de mesure hérités. Lorsque vous utilisez la version 5.2 du Créateur de rapports, ces identifiants de mesure hérités sont convertis en nouvel identifiant global. Si vous partagez ce classeur avec un utilisateur de la version 5.1 ou antérieure du Créateur de rapports, il ne verra pas les mesures calculées.

Pour en savoir plus sur la manière de créer et de gérer des mesures calculées à l’aide du nouveau créateur et gestionnaire de mesures calculées, reportez-vous au guide des [mesures calculées](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics).

À la deuxième étape de l’Assistant Requête, vous pouvez filtrer et appliquer les mesures calculées.

## Filtrage des mesures calculées {#section_376E986D3E684999A7CDB08E53854159}

**Filtrez** les mesures calculées en cliquant sur l'icône Filtrer : ![](assets/segment_filter.png)

. La boîte de dialogue Filtres avancés est renseignée avec les mesures standard et calculées.

Les filtres disponibles incluent :

![](assets/advanced_filters_(2).png)

| Nom du filtre | Description |
|---|---|
| Balises | Permet de filtrer les mesures calculées selon des balises spécifiques. Notez que les filtres de type balise utilisent l’opérateur ET. Si vous cochez deux balises, le panneau de droite répertorie les mesures qui ont été marquées avec **les deux** balises. |
| Suites de rapports | If you apply the "Only *report suite name*" filter in the Calculated Metric Builder in [!DNL Reports & Analytics], and then display the Advanced Filter in [!DNL Report Builder], the Advanced filter will display the calculated metrics for the selected report suite only. |
| Propriétaires | Permet de filtrer les mesures par propriétaire. Notez que les filtres de type propriétaire utilisent l’opérateur OU. Si vous cochez deux propriétaires, le panneau de droite répertorie les mesures détenues par **n’importe quel** propriétaire. |
| Autres filtres &gt; Approuvés | Affiche toutes les mesures   officiellement approuvées. |
| Autres filtres &gt; Favoris | Affiche toutes les mesures que vous avez marquées comme Favoris. |
| Autres filtres &gt; À moi | Affiche toutes les mesures que vous possédez. |
| Autres filtres &gt; Partagé avec moi | Affiche toutes les mesures que d’autres ont partagées avec vous. |

## Appliquer les mesures calculées {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

Après avoir sélectionné les filtres, cliquez sur **[!UICONTROL Appliquer]pour les appliquer à votre demande.** Les mesures sélectionnées sont maintenant ajoutées à la disposition des rapports.

![](assets/filtering_for_metric.png)

