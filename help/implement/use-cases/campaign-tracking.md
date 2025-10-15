---
title: Workflow du suivi de campagne
description: Utilisez Adobe Analytics pour suivre vos efforts marketing.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 100%

---

# Workflow du suivi de campagne

Si votre entreprise souhaite suivre les performances et le taux de clics publicitaires des efforts marketing, vous pouvez utiliser le processus suivant. Chacune de ces étapes comporte des sections dédiées ci-dessous qui contiennent plus de détails.

1. [Établir un processus de génération de code de suivi](#establish-a-tracking-code-generation-process)
1. [Ajouter le code de suivi souhaité à l’e-mail](#add-the-desired-tracking-code-to-the-email)
1. [Configurer ou ajuster votre mise en œuvre Adobe Analytics pour inclure des données de code de suivi](#include-campaign-variables-in-your-implementation)
1. [Afficher les rappports dans Analysis Workspace](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/fr/products/campaign/adobe-campaign.html) peut simplifier chacune de ces étapes afin de tirer le meilleur parti de vos efforts marketing. Pour plus dʼinformations, contactez votre personne représentante commerciale Adobe.

## Établir un processus de génération de code de suivi

Chaque organisation a des besoins différents en matière de codes de suivi. Certaines peuvent avoir des besoins minimaux où les codes de suivi créés manuellement sont plus que suffisants. D’autres peuvent souhaiter un meilleur contrôle sur le suivi et avoir plusieurs systèmes en place pour créer les codes de suivi souhaités. Si votre organisation utilise Google Analytics en plus d’Adobe Analytics, elle dispose peut-être déjà d’un modèle établi de code de suivi `utm`.

Quelle que soit la manière dont vous choisissez de créer ou de générer des codes de suivi, la mise en place d’un système cohérent facilite beaucoup la tâche de votre organisation lorsque vous souhaitez regrouper les codes de suivi pour la création de rapports. Les codes de suivi structurés de manière cohérente vous permettent de créer des [Règles de classification](/help/components/classifications/crb/classification-rule-builder.md) afin d’obtenir des informations sur les performances catégoriques.

## Ajouter le code de suivi souhaité à une URL

Une fois que vous disposez de la valeur de code de suivi souhaitée, vous pouvez l’ajouter à tous les liens que vous publiez en ligne, tels que les publicités, les médias sociaux ou les e-mails. L’ajout de ces codes de suivi se fait généralement dans la chaîne de requête d’un lien. Le paramètre de chaîne de requête que vous utilisez dépend des exigences de suivi de votre organisation. Parmi les paramètres de chaîne de requête communs, il y a `cid` (abréviation d’identifiant de campagne). Certaines organisations qui utilisent également Google Analytics peuvent déjà avoir plusieurs paramètres de chaîne de requête de campagne, tels que `utm_source`, `utm_medium`, etc.

L’ajout de chaînes de requête à un lien dans un e-mail ressemble à ce qui suit :

```text
https://example.com?cid=EM989027
```

## Inclure des variables de campagne dans votre implémentation

Adobe Analytics dispose d’une dimension de [Code de suivi](/help/components/dimensions/tracking-code.md) que vous pouvez utiliser pour mesurer divers efforts marketing dans l’ensemble de votre organisation. Toutefois, différentes organisations peuvent avoir des exigences de suivi différentes. Il est important de référencer le [Document de conception de solution](../prepare/solution-design.md) de votre organisation pour suivre de façon cohérente les valeurs appropriées dans les variables appropriées.

Si votre organisation n’a pas encore configuré le suivi de campagne, vous pouvez ajuster votre mise en œuvre pour définir la variable [`campaign`](/help/implement/vars/page-vars/campaign.md). Consultez la méthode [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) pour savoir comment collecter des valeurs de paramètre de chaîne de requête spécifiques à l’implémentation de votre organisation.

Si votre organisation collecte des chaînes de requête `utm`, vous pouvez choisir :

* Envoyer toutes les chaînes de requête `utm` dans la dimension de Code de suivi sous forme de valeurs concaténées. Vous pouvez ensuite utiliser les [Règles de classification](/help/components/classifications/crb/classification-rule-builder.md) pour créer des dimensions supplémentaires qui se concentrent sur chaque paramètre `utm`. Cette méthode a une courbe d’apprentissage plus complexe, mais n’utilise aucune eVar supplémentaire.
* Envoyer chaque chaîne de requête `utm` dans une [eVar](/help/components/dimensions/evar.md) distincte. Cette méthode est plus simple à mettre en œuvre, mais nécessite l’utilisation d’eVars supplémentaires.

## Afficher les rappports dans Analysis Workspace

Une fois que vous avez correctement configuré votre implémentation pour collecter les données de code de suivi, vous pouvez afficher des rapports dans Analysis Workspace.

1. Connectez-vous à [Adobe Experience Cloud](https://experience.adobe.com) et sélectionnez [!UICONTROL Adobe Analytics].
1. Créez un [projet Workspace](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. Dans la liste des composants sur la gauche, faites glisser la dimension de [Code de suivi](/help/components/dimensions/tracking-code.md) dans la zone de travail de workspace.
1. Faites glisser la mesure souhaitée, par exemple [Visites](/help/components/metrics/visits.md) ou [Commandes](/help/components/metrics/orders.md), sur le côté droit de la zone de travail de workspace.

![Rapport de suivi de campagne](../assets/campaign-tracking-report.png)
