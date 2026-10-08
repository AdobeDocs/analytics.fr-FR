---
title: Sélection de composants dans l’assistant de mise à niveau de Web SDK
description: Choisissez les règles de balises, les éléments de données et les extensions à inclure dans une migration Web SDK.
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
source-wordcount: '401'
ht-degree: 0%
---
# Sélection de composant

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection"
>title="Sélection de composant"
>abstract="Choisissez les règles, les éléments de données et les extensions à inclure dans cette migration. Les composants qui contribuent activement à votre implémentation d’Adobe Analytics sont sélectionnés par défaut. Les étapes suivantes ne fonctionnent qu’avec les composants que vous sélectionnez ici."

La sélection des composants est la première étape d’une migration. Utilisez-le pour choisir les règles, éléments de données et extensions de votre propriété de balises à inclure dans la migration.

L’assistant de mise à niveau organise les composants de votre propriété de balises dans les onglets **[!UICONTROL Règles]**, **[!UICONTROL Éléments de données]** et **[!UICONTROL Extensions]**. Chaque onglet répertorie tous les composants de la propriété de ce type, en fonction de l’instantané de la bibliothèque pris par l’assistant de mise à niveau lorsque vous [avez créé la migration](manager.md#create). Par défaut, seuls les composants qui contribuent activement à votre implémentation d’Adobe Analytics sont sélectionnés. Vous pouvez sélectionner ou effacer n’importe quel composant.

La colonne **[!UICONTROL Publié]** indique si chaque composant fait partie de la bibliothèque que vous avez sélectionnée. Les composants qui ne font pas partie de la bibliothèque existent dans la propriété des balises, mais pas dans cette bibliothèque. Pour filtrer la liste selon ce critère, utilisez le filtre **&#x200B;**.

Vous pouvez inclure des composants qui ne sont pas liés à Adobe Analytics, tels que des composants pour Adobe Target, Adobe Audience Manager ou des extensions tierces, mais l’assistant de mise à niveau ne les convertit pas dans le SDK Web.

Les composants que vous sélectionnez déterminent les étapes suivantes qui fonctionnent. Par exemple, vous pouvez inclure des éléments de données auxquels rien ne fait référence afin que [les résultats de l’audit](audit-findings.md) puissent les marquer pour nettoyage.

## Affichage des détails du composant {#details}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_tagsusage"
>title="Utilisation des balises"
>abstract="Règles, éléments de données et extensions qui utilisent ce composant. L’utilisation de l’extension couvre uniquement les paramètres de configuration de l’extension. L’utilisation dans une règle s’affiche sous Utilisation des règles."

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_analyticsusage"
>title="Utilisation d’Analytics"
>abstract="Variables Adobe Analytics auxquelles ce composant est affecté, regroupées par type de variable."

<!-- markdownlint-enable MD034 -->

Sélectionnez le nom d’un composant pour ouvrir un panneau qui affiche sa configuration et son emplacement d’utilisation :

* **[!UICONTROL Utilisation des balises]** : règles, éléments de données et extensions qui utilisent le composant. L’**[!UICONTROL utilisation de l’extension]** couvre uniquement les paramètres de configuration de l’extension. L’utilisation dans une règle apparaît sous **[!UICONTROL Utilisation des règles]**.
* **[!UICONTROL Utilisation d’Analytics]** : variables Adobe Analytics auxquelles le composant est affecté, regroupées par type de variable.

Pour afficher le composant dans l’interface utilisateur des balises, sélectionnez son nom dans la partie supérieure du panneau.

Lorsque vous avez terminé, sélectionnez **[!UICONTROL Enregistrer et continuer]** pour accéder à [conclusions de l’audit](audit-findings.md).