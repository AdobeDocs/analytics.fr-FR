---
description: How Workspace totals are calculated.
seo-description: Learn how Workspace totals are calculated.
seo-title: How Workspace totals are calculated.
title: Workspace totals
translation-type: tm+mt
source-git-commit: b2e76715a2bab0931b1ddf8c612c29eea530ce6c

---


# Workspace totals

In Freeform tables, a total row appears at each breakdown level and can show two totals:

* **[!UICONTROL Grand Total (gray 'out of' number) - this total represents all hits that have been collected, sometimes referred to as 'report suite total'.]** When a segment is applied either at the panel level or within the freeform table, this total adjusts to reflect all hits that match the segment criteria.
* **[!UICONTROL Table Total (black number) - this total is typically equal to or a subset of the Grand Total.]** Elle reflète les filtres de tableau appliqués dans le tableau à structure libre, y compris l’option [!UICONTROL Inclure aucun] .

![](assets/total-row.png)

## Afficher le paramètre total

Sous Paramètres **[!UICONTROL de]** colonne, vous pouvez **[!UICONTROL afficher les totaux]** et **[!UICONTROL afficher le total]** général. If these settings are unchecked, totals will be removed from the table. Cela peut être souhaité dans les cas où les totaux n’ont pas de sens, par exemple, dans certains scénarios [de mesures](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetrics-reference/cm-totals.html)calculées.

![](assets/column-settings-total.png)

## Paramètres Total des lignes statiques

[Les totaux des lignes](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.html) statiques se comportent différemment et sont contrôlés sous Paramètres **[!UICONTROL de]** ligne.

* **[!UICONTROL Afficher la somme des lignes actuelles sous forme de total]** : affiche la somme des lignes côté client du tableau, ce qui signifie que le total ne dédupliquera **pas** les mesures comme les visites ou les visiteurs.
* **[!UICONTROL Afficher le total]** général : indique une somme côté serveur, ce qui signifie que le total dédupliquera les mesures comme les visites ou les visiteurs.

![](assets/static-rows.png)

## Questions fréquentes

| Questions | Réponse |
|---|---|
| Sur quel "total" sont basés les pourcentages des colonnes grises ? | Cela dépend de la sélection du paramètre **[!UICONTROL Pourcentages]** sous Paramètres **[!UICONTROL de]** ligne :<ul><li>Calculer les pourcentages par colonne - Il s'agit du paramètre par défaut. Les pourcentages seront basés sur le total du tableau.</li><li>Calculer les pourcentages par ligne : les pourcentages seront basés sur le total général.</li></ul> |
| Comment le paramètre **[!UICONTROL Inclure non spécifié (Aucun)]** définit-il les totaux d’impact ? | Si le paramètre **[!UICONTROL Inclure non spécifié (Aucun)]** n’est pas coché, la ligne Aucun/Non spécifié sera supprimée du tableau, le Total du tableau et sera répercutée sur toutes les mesures calculées qui utilisent les types de mesures ["Total".](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/m-metric-type-alloc.html) |
| Lorsque des filtres de tableau personnalisés sont appliqués à un tableau à structure libre, est-ce que toutes mes mesures calculées et mon compte de mise en forme conditionnelle sont associés au filtre ? | Pas actuellement. **[!UICONTROL Inclure non spécifié (Aucun)]** sera pris en compte, mais les filtres de tableau personnalisés n’auront aucun impact sur les éléments suivants :<ul><li>La plage max/min de la colonne utilisée par la mise en forme conditionnelle s’appliquera à toutes les données.</li><li>Mesures calculées qui utilisent les types de mesures **[!UICONTROL Total]** général.</li><li>Mesures calculées avec des fonctions qui calculent sur les lignes d’un tableau à structure libre - c’est-à-dire Somme de colonne, Max de colonne, Min de colonne, Moyenne, Moyenne, Percentile, Quartile, Nombre de lignes, Écart type, Variance, Cumulative, Moyenne cumulée, Variantes de régression, Score en T, Test Z, Test.</li></ul> |
| Dans Mesures calculées, que reflète le type de mesure Total **[!UICONTROL général]** ? | **[!UICONTROL Le Total]** général continue de faire référence au Total **** général et ne reflète pas les filtres appliqués à un tableau ou au Total **[!UICONTROL du]** tableau. |
| Quel est le total affiché lorsque les données sont copiées et collées à partir d’un tableau à structure libre ou téléchargées au format CSV ? | La ligne totale reflète uniquement le total **[!UICONTROL du]** tableau et respecte le paramètre **[!UICONTROL Afficher les totaux]** de la colonne. |

