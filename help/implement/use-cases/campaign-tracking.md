---
title: Workflow du suivi des campagnes
description: Utilisez Adobe Analytics pour effectuer le suivi de vos efforts marketing.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 1%

---

# Workflow du suivi des campagnes

Si votre entreprise souhaite effectuer le suivi des performances et du taux de clics publicitaires des efforts marketing, vous pouvez utiliser le processus suivant. Chacune de ces étapes comporte des sections dédiées ci-dessous qui contiennent plus de détails.

1. [Créer un processus de génération de code de suivi](#establish-a-tracking-code-generation-process)
1. [Ajoutez le code de suivi souhaité à l’email.](#add-the-desired-tracking-code-to-the-email)
1. [Configurer ou ajuster votre mise en oeuvre Adobe Analytics pour inclure des données de code de suivi](#include-campaign-variables-in-your-implementation)
1. [Affichage des rapports dans Analysis Workspace](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/products/campaign/adobe-campaign.html) Vous pouvez simplifier chacune de ces étapes afin de tirer le meilleur parti de vos efforts marketing. Pour plus d’informations, contactez votre représentant commercial d’Adobe.

## Créer un processus de génération de code de suivi

Chaque organisation a des besoins différents en codes de suivi. Certaines organisations peuvent avoir des besoins minimaux lorsque les codes de suivi créés manuellement sont plus que suffisants. D’autres organisations peuvent souhaiter un meilleur contrôle sur le suivi et avoir plusieurs systèmes en place pour créer les codes de suivi souhaités. Si votre entreprise utilise des Google Analytics en plus d’Adobe Analytics, votre entreprise dispose peut-être déjà d’un `utm` modèle de code de suivi établi.

Quelle que soit la manière dont vous choisissez de créer ou de générer des codes de suivi, la mise en place d’un système cohérent facilite beaucoup la tâche de votre entreprise lorsque vous souhaitez regrouper les codes de suivi pour la création de rapports. Les codes de suivi structurés de manière cohérente vous permettent de créer des [Règles de classification](/help/components/classifications/crb/classification-rule-builder.md) afin d’obtenir des informations sur les performances catégoriques.

## Ajoutez le code de suivi souhaité à une URL.

Une fois que vous disposez de la valeur de code de suivi souhaitée, vous pouvez l’ajouter à tous les liens que vous publiez en ligne, tels que les publicités, les médias sociaux ou les e-mails. L’ajout de ces codes de suivi se fait généralement dans la chaîne de requête d’un lien. Le paramètre de chaîne de requête que vous utilisez dépend des exigences de suivi de votre entreprise. Un paramètre de chaîne de requête commun est `cid` (abrégé pour l’identifiant de campagne). Certaines organisations qui utilisent également des Google Analytics peuvent déjà avoir plusieurs paramètres de chaîne de requête de campagne, tels que `utm_source`, `utm_medium`, etc.

L’ajout de chaînes de requête à un lien dans un email ressemble à ce qui suit :

```text
https://example.com?cid=EM989027
```

## Inclure des variables de campagne dans votre implémentation

Adobe Analytics dispose d’un [Code de suivi](/help/components/dimensions/tracking-code.md) dimension que vous pouvez utiliser pour mesurer divers efforts marketing dans l’ensemble de votre organisation. Toutefois, différentes organisations peuvent avoir des exigences de suivi différentes. Il est important de référencer la variable [Document de conception de solution](../prepare/solution-design.md) pour effectuer un suivi cohérent des valeurs appropriées dans les variables appropriées.

Si votre organisation n’a pas encore configuré le suivi de campagne, vous pouvez ajuster votre mise en oeuvre pour définir la variable [`campaign`](/help/implement/vars/page-vars/campaign.md) Variable . Voir [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) pour savoir comment collecter des valeurs de paramètre de chaîne de requête spécifiques à l’implémentation de votre entreprise.

Si votre organisation collecte des données `utm` chaînes de requête, vous pouvez choisir :

* Envoyer tout `utm` chaînes de requête dans la dimension Code de suivi sous forme de valeurs concaténées. Vous pouvez ensuite utiliser [Règles de classification](/help/components/classifications/crb/classification-rule-builder.md) pour créer des dimensions supplémentaires qui se concentrent sur chaque `utm` . Cette méthode a une courbe d’apprentissage plus complexe, mais n’utilise aucune eVar supplémentaire.
* Envoyer chaque `utm` chaîne de requête dans une chaîne distincte [eVar](/help/components/dimensions/evar.md). Cette méthode est plus simple à mettre en oeuvre, mais nécessite l’utilisation d’eVars supplémentaires.

## Affichage des rapports dans Analysis Workspace

Une fois que vous avez correctement configuré votre implémentation pour collecter les données de code de suivi, vous pouvez afficher des rapports dans Analysis Workspace.

1. Connectez-vous au [Adobe Experience Cloud](https://experience.adobe.com) et sélectionnez [!UICONTROL Adobe Analytics].
1. Créez un [Projet Workspace](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. Dans la liste des composants sur la gauche, faites glisser le [Code de suivi](/help/components/dimensions/tracking-code.md) dans le canevas de l’espace de travail.
1. Faites glisser la mesure souhaitée, par exemple [Visites](/help/components/metrics/visits.md) ou [Commandes](/help/components/metrics/orders.md) sur le côté droit du canevas de l’espace de travail.

![Rapport de suivi de campagne](../assets/campaign-tracking-report.png)
