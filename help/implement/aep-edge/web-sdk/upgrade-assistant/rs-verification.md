---
title: Vérification des suites de rapports dans l’assistant de mise à niveau de Web SDK
description: Examinez les variables Analytics dans vos suites de rapports et choisissez celles à transférer dans le mappage XDM.
feature: Implementation Basics
role: Admin, Developer, Leader
badge: Beta
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 629efca210346d32b8555c60f7db15d1d8285b20
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 0%
---
# Vérification de la suite de rapports

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_rsverification"
>title="Vérification de la suite de rapports"
>abstract="Examinez les variables Analytics que votre propriété de balises envoie à chaque suite de rapports. Les variables que vous sélectionnez ici sont transférées vers le mappage XDM. Utilisez les onglets pour rechercher des données récentes, trouver des variables en double et comparer les paramètres entre les suites de rapports."

<!-- markdownlint-enable MD034 -->

L’assistant de mise à niveau identifie les suites de rapports auxquelles votre propriété de balises envoie des données, puis compare les variables Analytics de votre implémentation à la configuration et aux données récentes de chaque suite de rapports. Utilisez cette étape pour décider quelles variables sont transférées vers le [mappage XDM](xdm-mapping.md).

L’assistant de mise à niveau utilise vos suites de rapports pour comprendre quelles variables votre implémentation définit et comment elles sont configurées. Les données d’activité couvrent les 90 derniers jours.

## Activité variable {#variable-activity}

L’onglet **[!UICONTROL Activité de variable]** répertorie les variables Analytics de la suite de rapports que vous avez choisie de mapper dans [Analyse des variables](#variable-analysis) et indique si chacune d’elles a collecté des données au cours des 90 derniers jours.

Les variables que vous sélectionnez sont transférées vers le mappage XDM. Pensez à effacer les variables qui ne collectent plus de données ou dont vous n’avez pas besoin dans votre implémentation de Web SDK. Une variable sans activité récente peut toujours être en cours d’utilisation, par exemple si elle est saisonnière ou si son trafic est faible. Confirmez donc que vous n’en avez pas besoin avant de l’effacer.

Pour chaque variable de liste et prop de liste que vous transférez, saisissez le délimiteur qui sépare ses valeurs. L’assistant de mise à niveau ne peut pas obtenir de délimiteurs depuis Adobe Analytics et vous ne pouvez pas continuer tant que chacun d’eux ne comporte pas de délimiteur.

## Analyse des variables {#variable-analysis}

Si votre propriété Balises envoie des données à plusieurs suites de rapports, choisissez d’abord la suite de rapports à mapper. L’onglet **[!UICONTROL Analyse des variables]** indique ensuite les variables qui peuvent nécessiter une décision avant de les mapper :

* Variables qui semblent collecter les mêmes données. Vérifiez qu’elles capturent les mêmes informations, puis décidez de les fusionner en une seule variable ou de les conserver séparées.
* Variables qui n’ont pas collecté de données récemment.
* Variables dont les valeurs sont toutes « Non spécifiées ».

## Comparaison de suites de rapports {#compare}

Si votre propriété de balises envoie des données à plusieurs suites de rapports, l’onglet **[!UICONTROL Comparer les suites de rapports]** compare les paramètres de chaque variable dans trois de ces suites de rapports au maximum. Utilisez-la pour rechercher des variables configurées différemment entre les suites de rapports avant de les mapper à un schéma.

## Mettre à jour les données d’une suite de rapports {#refresh}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_rsverification_refresh"
>title="Actualiser les données d’une suite de rapports"
>abstract="Vérifie à nouveau les suites de rapports liées à cette propriété de balises, y compris leurs paramètres de variable et les données récentes, puis exécute à nouveau l’analyse de variable. Si l’assistant de mise à niveau n’a pas encore trouvé de suite de rapports, il les recherche d’abord dans la propriété des balises. Vos sélections et décisions sont conservées."

<!-- markdownlint-enable MD034 -->

Vous pouvez modifier les suites de rapports que l’assistant de mise à niveau analyse au cours de cette étape. Si la configuration de votre suite de rapports change alors qu’une migration est en cours, sélectionnez **[!UICONTROL Actualiser les données de la suite de rapports]** pour réexécuter l’analyse. L’assistant de mise à niveau conserve vos sélections et décisions existantes.

Lorsque vous avez terminé, sélectionnez **[!UICONTROL Enregistrer et continuer]** pour accéder au [mappage XDM](xdm-mapping.md).
