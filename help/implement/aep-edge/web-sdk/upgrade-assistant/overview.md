---
title: Assistant de mise à niveau de Web SDK
description: Planifiez et exécutez la migration de votre extension Adobe Analytics tags vers Adobe Experience Platform Web SDK.
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
source-git-commit: 212d38950264a33b925b7281c241992cadca2bfb
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 3%
---
# Assistant de mise à niveau de Web SDK

L’assistant de mise à niveau de Web SDK vous permet de planifier et d’exécuter la migration de votre extension Adobe Analytics Tags vers Adobe Experience Platform Web SDK. La migration s’effectue alors dans un seul espace de travail guidé. Vous pouvez ainsi migrer de votre implémentation de balises existante vers Web SDK de manière structurée et facile à suivre.

## Fonctionnement de l’assistant de mise à niveau {#how-it-works}

Chaque migration fonctionne avec l’implémentation d’Adobe Analytics dans une propriété de balises. L’assistant de mise à niveau ajoute des actions Web SDK à vos règles existantes sans supprimer leurs actions Adobe Analytics. Votre implémentation continue donc à envoyer des données à Adobe Analytics avec la SDK Web.

L’assistant de mise à niveau convertit uniquement les composants Adobe Analytics. Vous pouvez inclure des composants provenant d’autres extensions, telles qu’Adobe Target, Adobe Audience Manager ou des extensions tierces, mais l’assistant de mise à niveau ne les convertit pas en SDK Web.

L’assistant de mise à niveau vous guide tout au long des étapes suivantes, chacune d’elles reposant sur les décisions prises lors de la précédente :

1. **[Sélection de composant](component-selection.md)** : sélectionnez les règles, les éléments de données et les extensions à inclure dans la migration.
1. **[Résultats d’audit](audit-findings.md)** : consultez les recommandations de nettoyage facultatives pour les composants que vous avez sélectionnés.
1. **[Préparation du mappeur](mapper-prep.md)** : passez en revue les variables Analytics dans vos suites de rapports et choisissez celles à reporter.
1. **[Mappage XDM](xdm-mapping.md)** : mappez vos variables Analytics aux champs d’un schéma XDM.
1. **[Implémentation de Web SDK](web-sdk-implementation.md)** : passez en revue les actions de Web SDK que l’assistant de mise à niveau ajoute à vos règles.
1. **[Révision finale](final-review.md)** : sélectionnez un sandbox Experience Platform, vérifiez les éléments créés par la migration et finalisez la migration.

Chaque étape configure une partie de la migration et vous pouvez revenir aux étapes terminées pour les examiner ou les modifier aussi souvent que vous le souhaitez. L’assistant de mise à niveau ne modifie pas votre propriété de balises et ne crée rien dans Experience Platform tant que la migration n’est pas terminée. Lorsque vous le finalisez, l’assistant de mise à niveau crée tout en même temps et ajoute les modifications de balises à une nouvelle bibliothèque. Vous testez ensuite cette bibliothèque et la publiez en production à l’aide du flux de publication des balises.

>[!IMPORTANT]
>
>L’assistant de mise à niveau utilise l’intelligence artificielle (IA) pour générer des recommandations telles que les mappages de champs XDM et les configurations de règles Web SDK. Ces recommandations peuvent ne pas être exactes ou complètes. Vérifiez-les avant de publier vos modifications dans la production.

## Conditions préalables {#prerequisites}

Avant de créer une migration, vérifiez que vous disposez des éléments suivants :

* Autorisations [ requises par ](#permissions)’assistant de mise à niveau.
* Propriété de balises qui utilise l’extension Adobe Analytics.
* Bibliothèque dans cette propriété qui contient l’implémentation à migrer. La bibliothèque peut être dans n’importe quel état, y compris publiée. Voir [Bibliothèques](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/libraries) dans le guide d’utilisation des balises.

### Autorisations {#permissions}

L&#39;assistant de mise à niveau requiert l&#39;accès suivant. Contactez l’administrateur ou l’administratrice de produit Experience Platform de votre organisation pour obtenir toutes les autorisations qui vous manquent.

| Type d’accès | Obligatoire |
| --- | --- |
| [Autorisations Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home#permissions) | <ul><li>[!UICONTROL Affichage des schémas]</li><li>[!UICONTROL Gestion des schémas]</li><li>[!UICONTROL Affichage des jeux de données]</li><li>[!UICONTROL Gestion des jeux de données]</li><li>[!UICONTROL Affichage des espaces de noms d’identité]</li></ul> |
| Accès aux produits | <ul><li>Collecte de données (balises)</li><li>Adobe Analytics</li></ul> |
| [ Droits des balises ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/administration/user-permissions) | [!UICONTROL Gérer les propriétés] |

Lorsque vous êtes prêt, [créez une migration](manager.md#create).
