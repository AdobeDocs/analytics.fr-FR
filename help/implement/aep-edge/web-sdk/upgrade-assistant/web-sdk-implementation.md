---
title: Implémentation de Web SDK dans l’assistant de mise à niveau de Web SDK
description: Examinez les actions de Web SDK que l’assistant de mise à niveau ajoute à vos règles de balises existantes.
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
source-wordcount: '311'
ht-degree: 0%
---
# Implémentation de Web SDK

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_websdkimplementation"
>title="Implémentation de Web SDK"
>abstract="Passez en revue les actions de Web SDK que l’assistant de mise à niveau ajoute à vos règles. Vos actions Adobe Analytics restent en place. Sélectionnez un composant pour comparer ses configurations actuelle et SDK Web côte à côte. Seuls les composants mis en file d’attente sont ajoutés à la migration."

<!-- markdownlint-enable MD034 -->

À l’aide des composants que vous avez sélectionnés et de votre [mappage XDM](xdm-mapping.md), l’assistant de mise à niveau ajoute les actions Web SDK à vos règles, directement après chaque action Adobe Analytics. Les actions Analytics restent en place. Par conséquent, ces règles envoient des données à Adobe Analytics et à Web SDK. La plupart des éléments de données sont transférés inchangés et les règles continuent de les référencer par leur nom.

La colonne **[!UICONTROL Modifier le type]** indique l’impact de la finalisation de la migration sur chaque composant :

* **[!UICONTROL Actions Web SDK ajoutées]** : l’assistant de mise à niveau ajoute les actions Web SDK à la règle.
* **[!UICONTROL Aucune modification]** : le composant est reporté sans modification.
* **[!UICONTROL Bloqué]** : le composant doit être examiné avant que l’assistant de mise à niveau puisse y ajouter des actions Web SDK. Sélectionnez le composant pour voir ce qui le bloque.

Sélectionnez un composant pour comparer sa configuration actuelle à sa configuration Web SDK côte à côte. Si vous avez besoin de plus de contexte, l’assistant de mise à niveau crée un lien vers le composant dans l’interface utilisateur des balises.

Les composants mis en file d’attente sont ajoutés à la migration. Pour mettre un composant en file d’attente, sélectionnez-le dans la liste ou sélectionnez **[!UICONTROL File d’attente]** dans ses détails. Pour le retirer, sélectionnez **[!UICONTROL Supprimer de la file d’attente]**. L’assistant de mise à niveau ne modifie pas votre propriété de balises tant que vous n’avez pas [finalisé la migration](final-review.md#finalize).

L’assistant de mise à niveau utilise l’IA pour générer les actions de Web SDK et les résultats peuvent ne pas être exacts ou complets. La génération des actions ne vérifie pas leur comportement sur votre site. Testez-les donc avant de publier la bibliothèque.
