---
title: Vue d’ensemble des dimensions
description: Découvrez les dimensions et leur utilisation dans Adobe Analytics.
feature: Dimensions
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
TQID: https://experienceleague.adobe.com/WypIneraYlrSyIpXv3UQWIFn42A-Dxi0SxeJ2VbeubQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 37%

---

# Présentation des dimensions

Les dimensions sont des variables d’Adobe Analytics qui contiennent généralement des valeurs de chaîne. Les dimensions courantes comprennent [Page](page.md), [Domaine référent](referring-domain.md) ou une [eVar](evar.md). En revanche, les [mesures](../metrics/overview.md) contiennent des valeurs numériques liées à une dimension. Un rapport de base présente des lignes de valeurs de chaîne (dimension) en fonction d’une colonne de valeurs numériques (mesure).

Par exemple, si vous combinez la dimension **[!UICONTROL Page]** à la mesure **[!UICONTROL Visites]**, vous obtenez un rapport classant les pages les plus visitées :

| Page | Visites |
| --- | ---: |
| Page d’accueil | 800 |
| Page produit | 500 |
| Page d’achat | 100 |

{style="table-layout:fixed"}

Chaque dimension représente une partie ou une facette différente de votre site. Vous pouvez combiner l’une de ces dimensions avec une ou plusieurs mesures pour créer un rapport qui cous correspond.

## Ajouter des descriptions pour les dimensions

Les administrateurs et administratrices d’Analytics peuvent ajouter des descriptions pour les dimensions et d’autres composants dans la suite de rapports ou directement dans Analysis Workspace. Pour plus d’informations sur l’ajout de descriptions aux dimensions, voir [Ajouter des descriptions de composant](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Dimensions retirées

Les dimensions suivantes sont retirées. La plupart étaient des rapports Reports &amp; Analytics non disponibles dans Analysis Workspace. Ils sont documentés ici à titre de référence si vous les rencontrez dans des rapports hérités ou des données historiques.

* **Hiérarchie** : dimension personnalisée (`hier1`-`hier5`) utilisée pour capturer la structure hiérarchique d’un site à des fins de création de rapports. Il a été retiré et n’est pas disponible dans Analysis Workspace. Utilisez plutôt des [eVars](evar.md) et des classifications.
* **Page d’accueil** : indicateur signalant si la page en cours était la page d’accueil du navigateur du visiteur. C’est une dimension héritée sans équivalent moderne en raison des pratiques modernes de confidentialité des navigateurs.
* **Prise en charge de JavaScript** : indique si le navigateur du visiteur prend en charge JavaScript. Une dimension héritée qui n’a plus de sens pour les mesures modernes.
* **Version de JavaScript** : a signalé la version de JavaScript prise en charge par le navigateur du visiteur. Une dimension héritée qui n’est plus collectée.
* **Page suivante** : dimension de cheminement affichant la page suivante consultée par un visiteur. Utilisez la [visualisation des flux](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) dans Analysis Workspace pour les dimensions de cheminement actuelles.
* **Page précédente** : dimension de cheminement affichant la page précédente consultée par un visiteur. Utilisez la [visualisation des flux](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) dans Analysis Workspace pour les dimensions de cheminement actuelles.
* **Fuseau horaire** : fuseau horaire du visiteur, dérivé du décalage d’horodatage dans les demandes d’image AppMeasurement. Web SDK collecte le fuseau horaire à l’aide de [`placeContext`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/context).
* **Domaine de niveau supérieur** : domaine de niveau supérieur du point d’accès du visiteur. Rapport Reports &amp; Analytics hérité. Utilisez plutôt la dimension [Domaine](domain.md).
* **Numéro de page de la visite** : numéro de page d’une visite. Rapport Reports &amp; Analytics hérité. Utilisez plutôt la dimension [ Profondeur d’accès ](hit-depth.md).
* **État du visiteur** : état des États-Unis signalé à partir de la variable `s.state` . Elle est retirée au profit de la dimension [ États américains](us-states.md) qui utilise la géosegmentation.
