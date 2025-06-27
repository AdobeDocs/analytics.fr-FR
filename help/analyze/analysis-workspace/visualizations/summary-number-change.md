---
description: Utilisez les visualisations Synthèse des chiffres et Synthèse des changements pour afficher des points de données importants dans un projet.
title: Synthèse Des Chiffres Et Synthèse Des Modifications
uuid: 177c1b89-6d98-473d-8447-6b4cdc479565
feature: Visualizations
role: User, Admin
exl-id: d6a08201-ca3a-48ff-983a-3ec6b989deda
source-git-commit: 978bd8642011dd2c8e43564c90303f194689a64e
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 98%

---

# [!UICONTROL Synthèse des chiffres] et [!UICONTROL Synthèse des modifications]

_Cet article documente les visualisations Synthèse des chiffres et Synthèse des modifications dans_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Voir [Synthèse des chiffres et Synthèse des modifications](https://experienceleague.adobe.com/fr/docs/analytics-platform/using/cja-workspace/visualizations/summary-number-change) pour la_ version ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics** de cet article._


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visualisations Synthèse des chiffres et Synthèse des modifications](https://video.tv.adobe.com/v/3416888/?quality=12&captions=fre_fr){target=&#34;_blank&#34;} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


## Visualisation [!UICONTROL Synthèse des chiffres] {#summary-number}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_summarynumber_button"
>title="Synthèse des chiffres"
>abstract="Créez une visualisation qui affiche les totaux et les sous-totaux."

<!-- markdownlint-enable MD034 -->


Utilisez la visualisation ![MoveUpDown](/help/assets/icons/MoveUpDown.svg) **[!UICONTROL Synthèse des modifications]** pour afficher le delta (modification) entre deux chiffres. <!-- This is applicable for AA, not CJA: The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/success-event.html?lang=fr) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=fr) option.-->

<!--
The green and red color of the Summary Change can be controlled through [custom event polarity](https://experienceleague.adobe.com/docs/analytics/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) or a calculated metric's [Show Upward Trend As](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=fr) option.
-->

Cette visualisation fonctionne comme suit :

* Si aucune cellule n’est sélectionnée, les valeurs de deux premières cellules de la colonne sont comparées.
* Si une seule cellule est sélectionnée, 0 s’affiche, car la valeur de la cellule est comparée à elle-même.
* Si deux cellules sont sélectionnées, la première cellule sélectionnée sert de numérateur, la deuxième de dénominateur.
* Si plus de deux cellules sont sélectionnées, seules les deux premières sont prises en compte pour la comparaison.
* Si une rangée de cellules est sélectionnée, la première et la dernière cellules de la rangée sont comparées.
* Si la colonne est sélectionnée, la première valeur est comparée à elle-même ; 0 s’affiche.


![Visualisation Synthèse des modifications montrant le delta entre deux nombres.](assets/summary-change.png)


Dans le cadre des paramètres de visualisation, des options spécifiques **[!UICONTROL Synthèse des modifications]** sont disponibles.

| Option | Définition |
|--- |--- |
| **[!UICONTROL Afficher le pourcentage de modification]** | Affichez le pourcentage de modification entre les 2 chiffres. |
| **[!UICONTROL Afficher la différence brute]** | Affichez la différence brute entre 2 nombres. Vous pouvez également abréger des valeurs et afficher jusqu’à 3 chiffres après la virgule avec cette option. |
| **[!UICONTROL Abréger la valeur]** | Sélectionnez **[!UICONTROL Abréger la valeur]** pour abréger intelligemment la valeur modifiée. Lorsque cette option est sélectionnée, saisissez un nombre pour définir le montant de l’abréviation. Par exemple :<br/><table><tr><td>**Valeur d’origine**</td><td>**Valeur de l’abréviation**</td><td>**Résultat**</td></tr><tr><td>12 011 141,25 $</td><td>Non sélectionné</td><td  align="right">12 011 141,25 $</td></tr><tr><td>12 011 141,25 $</td><td>Sélectionné, défini sur `0`</td><td align="right">12 M $</td></tr><tr><td>12 011 141,25 $</td><td> Sélectionné, défini sur `1`</td><td  align="right">12,0 M $</td></tr><tr><td>12 011 141,25 $</td><td>Sélectionné, défini sur `2`</td><td align="right">12,01 M $</td></tr><tr><td>12 011 141,25 $</td><td>Sélectionné, défini sur `3`</td><td align="right">12,011 M $</td></tr></table> |

>[!MORELIKETHIS]
>
>[Ajouter une visualisation à un panneau](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Paramètres de visualisation](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Menu contextuel de visualisation](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>
