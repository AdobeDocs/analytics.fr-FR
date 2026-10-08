---
title: Mappage XDM dans l’assistant de mise à niveau de Web SDK
description: Mappez vos variables Adobe Analytics aux champs d’un schéma XDM dans le cadre d’une migration de Web SDK.
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
source-wordcount: '419'
ht-degree: 3%
---
# Mappage XDM

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping"
>title="Mappage XDM"
>abstract="Mappez les variables Analytics sélectionnées aux champs d’un schéma XDM. L’assistant de mise à niveau peut créer un schéma avec des mappages suggérés par l’IA ou vous pouvez mapper des variables à un schéma que vous possédez déjà. Passez en revue tous les mappages avant de continuer."

<!-- markdownlint-enable MD034 -->

Le SDK Web envoie des données à l’aide des champs [Modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/home) de sorte que chaque variable Analytics que vous transférez à partir de la [vérification de la suite de rapports](rs-verification.md) nécessite un champ correspondant dans un schéma XDM. Au cours de cette étape, vous choisissez un schéma et mappez vos variables à ses champs.

## Choisir un schéma {#schema}

Vous pouvez créer le mappage de l’une des deux façons suivantes :

* **Création d’un schéma** : l’assistant de mise à niveau analyse vos variables Analytics et suggère un champ XDM pour chacune d’elles, puis génère un schéma à partir de ces suggestions, que vous pouvez examiner.
* **Utiliser un schéma existant** : sélectionnez un schéma déjà existant dans Experience Platform, puis mappez vous-même chaque variable à un champ.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping_fieldgroups"
>title="Préférence de groupe de champs"
>abstract="Choisissez le type de groupe de champs favorisé par l’assistant de mise à niveau lors de la création de votre schéma. Les groupes de champs standard sont définis par Adobe. Les groupes de champs personnalisés sont définis par votre organisation."

<!-- markdownlint-enable MD034 -->

Lorsque vous créez un schéma, vous choisissez également si l’assistant de mise à niveau favorise les groupes de champs standard ou personnalisés. Les groupes de champs standard sont définis par Adobe, tandis que les groupes de champs personnalisés sont définis par votre organisation. Voir [Groupe de champs](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/schema/composition#field-group) dans la documentation XDM.

## Vérifier le mappage {#review}

Le mappage répertorie chaque variable Analytics avec le champ XDM auquel elle est mappée, avec un aperçu du schéma complet en regard. Sélectionnez une partie du schéma pour filtrer la liste selon les variables qui lui sont associées. Vous pouvez ajuster à la fois les mappages individuels et le schéma lui-même.

L’assistant de mise à niveau utilise l’IA pour suggérer des mappages et les résultats peuvent ne pas être exacts ou complets. Passez en revue chaque mappage avant de continuer. L’assistant de mise à niveau ne crée le schéma dans Experience Platform que lorsque vous avez [finalisé la migration](final-review.md#finalize).

Lorsque vous avez terminé, sélectionnez **[!UICONTROL Enregistrer et continuer]** pour enregistrer le mappage et accédez à [Implémentation de Web SDK](web-sdk-implementation.md). Pour modifier le mappage après l’avoir enregistré, sélectionnez **[!UICONTROL Modifier]**, apportez vos modifications, puis sélectionnez **[!UICONTROL Enregistrer et continuer]**. Les modifications que vous n’enregistrez pas de cette manière ne sont pas incluses lorsque vous finalisez la migration.
