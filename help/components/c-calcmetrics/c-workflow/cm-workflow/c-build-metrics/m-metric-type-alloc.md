---
description: En savoir plus sur
title: Type de mesure et attribution
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 21c4d1b591daf7229bd36845e42e2dec473e792f
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 98%

---

# Type de mesure et attribution {#metric-type-attribution}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modèle"
>abstract="Sélectionnez un modèle d’attribution pour la mesure."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Dernière touche"
>abstract="100 % du crédit est attribué à la dernière valeur de dimension vue par un visiteur ou une visiteuse."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Première touche"
>abstract="100 % du crédit est attribué à la première valeur de dimension vue par un visiteur ou une visiteuse."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Linéaire"
>abstract="Le crédit est réparti uniformément sur toutes les valeurs de dimension."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Participation"
>abstract="Crédit 100 % à chaque valeur de dimension vue par un visiteur ou une visiteuse.<br/>Les totaux des colonnes sont surestimés."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Même touche"
>abstract="Le crédit est attribué uniquement aux valeurs de dimension survenant sur le même événement que la conversion."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Même touche"
>abstract="Le crédit est attribué uniquement aux valeurs de dimension survenant sur le même événement que la conversion."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="En forme de U"
>abstract="40 % du crédit à la première valeur de dimension, 40 % à la dernière, 20 % partagés par le milieu."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="En forme de J"
>abstract="60 % du crédit à la dernière valeur de dimension, 20 % à la première, 20 % partagés par le milieu."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="En forme de J"
>abstract="60 % du crédit à la dernière valeur de dimension, 20 % à la première, 20 % partagés par le milieu."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="En forme de J inversé"
>abstract="60 % du crédit à la première valeur de dimension, 20 % à la dernière, 20 % partagés par le milieu."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="En forme de J inversé"
>abstract="60 % du crédit à la première valeur de dimension, 20 % à la dernière, 20 % partagés par le milieu."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Décroissance temporelle"
>abstract="Les valeurs de dimension les plus proches dans le temps d’une conversion obtiennent le plus de crédit."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Personnalisé"
>abstract="Définissez votre propre pondération d’attribution basée sur la position."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Personnalisé"
>abstract="Définissez votre propre pondération d’attribution basée sur la position."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algorithmique"
>abstract="Le crédit est déterminé dynamiquement à l’aide d’un algorithme statistique."


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Conteneur"
>abstract="Sélectionnez un conteneur pour définir la portée souhaitée pour l’attribution."


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Intervalle de recherche en amont"
>abstract="Ce paramètre détermine la fenêtre d’attribution des données qui sera appliquée à chaque conversion."

Lors de la [création d’une mesure calculée](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), vous pouvez spécifier le type de mesure et le modèle d’attribution.

## Type de mesure

Pour spécifier le type de mesure lors de la création d’une mesure calculée, procédez comme suit :

1. Sélectionnez l’icône en forme d’engrenage en regard de la mesure dont vous souhaitez sélectionner le type.

   ![](assets/cm_type_alloc.png)

1. Choisissez l’une des options suivantes :

   | Type de mesure | Définition |
   |---|---|
   | Standard | Ces mesures sont les mêmes mesures que celles utilisées dans la création de rapports standard [!DNL Analytics]. Si une formule est composée d’une seule mesure standard, elle affiche des données identiques à sa contrepartie de mesure non calculée. Les mesures standard sont utiles pour créer des mesures calculées spécifiques à chaque ligne. Par exemple, [Commandes] / [Visites] utilise des commandes pour cette ligne spécifique et la divise par le nombre de visites correspondant à cette ligne spécifique. |
   | Total général | Utilisez le total général correspondant à la période de création de rapports de chaque ligne. Si une formule est composée d’une seule mesure Total général, elle affiche le même nombre total sur chaque élément de ligne. Les mesures Total général s’avèrent utiles pour créer des mesures calculées qui sont comparées au nombre total de données du site. Par exemple, [Commandes] / [Nombre total de visites] affiche la proportion des commandes par rapport à TOUTES les visites sur votre site, et non juste les visites sur l’élément de ligne spécifique. |

## Fonctionnement de l’affectation linéaire

L’[Attribution](/help/analyze/analysis-workspace/attribution/overview.md) a revu la manière dont les modèles dʼaffectation dans les mesures calculées sont évalués.

Pour obtenir la liste complète des modèles dʼattribution et des intervalles de recherche en amont autres que par défaut pris en charge, voir [Modèles dʼattribution et intervalles de recherche en amont](/help/analyze/analysis-workspace/attribution/models.md).

L’exemple suivant explique comment les mesures calculées avec l’affectation linéaire fonctionnent dans les rapports :

| | Accès 1 | Accès 2 | Accès 3 | Accès 4 | Accès 5 | Accès 6 | Accès 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Données envoyées dans | PROMO A | - | PROMO A | PROMO B | - | PROMO C | $10 |
| eVar de dernière touche | PROMO A | PROMO A | PROMO A | PROMO B | PROMO B | PROMO C | $10 |
| eVar de première touche | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | PROMO A | $10 |
| Exemple de Prop | PROMO A | - | PROMO A | PROMO B | - | PROMO C | $10 |

Dans cet exemple, les valeurs A, B et C ont été envoyées dans une variable aux accès 1, 3, 4 et 6 avant la réalisation d’un achat de 10 $ à l’accès 7. Dans la deuxième ligne, ces valeurs persistent dans les accès sur une base de visite de dernière touche. La troisième ligne représente une persistance de visite de première touche. Enfin, la dernière ligne indique comment les données seraient enregistrées pour une Prop qui ne présente pas de persistance.

