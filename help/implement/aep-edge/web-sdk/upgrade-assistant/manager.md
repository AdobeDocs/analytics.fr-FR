---
title: Gestion des migrations dans l’assistant de mise à niveau de Web SDK
description: Créez, affichez et ouvrez les migrations dans l’assistant de mise à niveau de Web SDK.
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
source-wordcount: '397'
ht-degree: 0%
---
# Gestion des migrations

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_migrations"
>title="Migrations"
>abstract="Chaque migration met à niveau l’implémentation d’Adobe Analytics dans une propriété de balises vers le SDK web. Ouvrez une migration pour continuer là où vous vous êtes arrêté, ou sélectionnez « Nouveau » pour en démarrer une."

La page **[!UICONTROL Migrations]** est le point de départ de l’assistant de mise à niveau de Web SDK. Il répertorie les migrations de votre organisation, y compris la progression et le statut de chaque migration, ainsi que son auteur. Utilisez cette page pour créer une migration ou pour ouvrir une migration existante.

## Création d’une migration {#create}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_newmigration"
>title="Nouvelle migration"
>abstract="Sélectionnez la propriété de balises à migrer, ainsi qu’une bibliothèque dans cette propriété. L’assistant de mise à niveau prend un instantané de la bibliothèque lorsque vous créez la migration. Les modifications apportées à la bibliothèque après un instantané de migration ne sont pas incluses. Votre propriété de balises ne change pas tant que vous n’avez pas finalisé la migration."

<!-- markdownlint-enable MD034 -->

Avant de créer une migration, assurez-vous de respecter les [ conditions préalables ](overview.md#prerequisites).

1. Sur la page **[!UICONTROL Migrations]**, sélectionnez **[!UICONTROL Nouveau]**.
1. Saisissez un nom pour la migration et, éventuellement, une description.
1. Sélectionnez la propriété de balises à migrer.
1. Sélectionnez une bibliothèque de balises. Lorsque vous créez la migration, l’assistant de mise à niveau prend un instantané de votre implémentation telle qu’elle existe dans cette bibliothèque. Les modifications que vous apportez à la bibliothèque par la suite ne sont pas répercutées dans la migration.
1. Sélectionnez **[!UICONTROL Créer]**.

La nouvelle migration apparaît dans la liste. Ouvrez-le pour commencer [sélection de composant](component-selection.md).

## Ouvrir une migration {#open}

Sélectionnez le nom d’une migration pour l’ouvrir. Les étapes de la migration s’affichent dans le volet de navigation de gauche. Vous pouvez revenir à n’importe quelle étape terminée pour la réviser ou la modifier aussi souvent que vous le souhaitez, mais les étapes que vous n’avez pas encore atteintes ne sont pas disponibles.

L’assistant de mise à niveau enregistre votre progression au fur et à mesure que vous passez d’une étape à l’autre, afin que vous puissiez laisser une migration et y revenir ultérieurement. Rien de ce que vous configurez ne prend effet tant que vous n’avez pas [finalisé la migration](final-review.md#finalize). Une fois que vous l’avez finalisée, la migration devient en lecture seule. Vous pouvez toujours l’ouvrir pour voir ce qu’il a créé, mais vous ne pouvez pas le modifier.

## Autres actions de migration {#actions}

Sélectionnez la ligne d’une migration pour afficher les actions disponibles :

* **[!UICONTROL Continuer]** : ouvre la migration.
* **[!UICONTROL Dupliquer l’exécution]** : crée une copie de la migration.
* **[!UICONTROL Renommer]** : modifie le nom et la description de la migration.
* **[!UICONTROL Archiver]** : redéfinit le statut de la migration sur **[!UICONTROL Archivé]**.
* **[!UICONTROL Supprimer la migration]** : supprime définitivement la migration. Vous ne pouvez pas annuler ceci.
