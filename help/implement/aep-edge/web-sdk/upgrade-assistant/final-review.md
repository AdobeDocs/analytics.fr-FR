---
title: Révision finale dans l’assistant de mise à niveau de Web SDK
description: Passez en revue et finalisez une migration de Web SDK, puis publiez la bibliothèque de balises résultante en production.
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
source-wordcount: '469'
ht-degree: 0%
---
# Révision finale

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_finalreview"
>title="Révision finale"
>abstract="Sélectionnez le sandbox Experience Platform à utiliser, puis passez en revue tout ce que cette migration crée ou modifie. Rien ne change tant que vous n’avez pas terminé la migration. Lorsque vous le finalisez, l’assistant de mise à niveau crée tout en même temps, ajoute les modifications de balises à une nouvelle bibliothèque et effectue cette migration en lecture seule. Vous publiez ensuite cette bibliothèque vous-même en production."

<!-- markdownlint-enable MD034 -->

L’examen final est la dernière étape d’une migration. Elle affiche tout ce que la migration crée ou modifie dans Experience Platform et dans votre propriété de balises.

## Examiner les éléments créés par la migration {#review}

Tout d’abord, sélectionnez le sandbox Experience Platform dans lequel la migration crée ses ressources. Vous ne pouvez pas finaliser la migration tant que vous n’avez pas sélectionné un sandbox.

L’assistant de mise à niveau répertorie ensuite tout ce que la finalisation de la migration crée ou modifie :

* **[!UICONTROL XDM]** : un nouveau schéma nommé en fonction de votre mappage XDM, ainsi que les groupes de champs personnalisés dont il a besoin. Les groupes de champs standard existent déjà. Le schéma les utilise donc tels quels. Cette section s’affiche uniquement si vous avez choisi de créer un schéma dans [mapping XDM](xdm-mapping.md#schema).
* **[!UICONTROL Jeux de données]** : deux jeux de données, un pour le développement et un pour la production. Chaque est nommé en fonction de la migration (`My migration - Development`, par exemple).
* **[!UICONTROL Flux de données]** : deux flux de données, l’un pour le développement et l’autre pour la production, nommés de la même manière que les jeux de données.
* **[!UICONTROL Adobe Tags]** : nouvelle bibliothèque nommée en fonction de la migration, telle que `Library - "My migration"`. La bibliothèque contient les règles et les éléments de données que la migration modifie, ainsi que la configuration d’extension dont les actions Web SDK ont besoin.

## Finalisation de la migration {#finalize}

Tant que vous n’avez pas terminé la migration, l’assistant de mise à niveau ne modifie pas votre propriété de balises et ne crée rien dans Experience Platform.

>[!IMPORTANT]
>
>Une fois la migration terminée, elle devient en lecture seule. Vous pouvez toujours l’ouvrir à partir de la page **[!UICONTROL Migrations]** pour voir ce qu’elle a créé, mais vous ne pouvez pas la modifier ni la finaliser à nouveau. Comme la nouvelle bibliothèque est toujours en cours de développement, vous pouvez modifier ou supprimer les modifications apportées aux balises dans l’interface utilisateur des balises avant de publier la bibliothèque.

1. Sélectionnez **[!UICONTROL Créer des artefacts]**.
1. Dans la boîte de dialogue **[!UICONTROL Vérifier ces recommandations]**, sélectionnez **[!UICONTROL Continuer]**.
1. Dans l’**[!UICONTROL Finaliser cette migration ?]** , sélectionnez **[!UICONTROL Finaliser]**.

L’assistant de mise à niveau crée tout en même temps et affiche sa progression. Il ajoute les modifications apportées aux balises à la nouvelle bibliothèque, mais ne la publie pas.

## Publier vos modifications {#publish}

Une fois la migration terminée, déplacez la nouvelle bibliothèque dans le flux de publication des balises :

1. Créez et testez la bibliothèque dans votre environnement de développement pour vous assurer que votre implémentation de Web SDK envoie les données attendues.
1. Envoyez la bibliothèque pour approbation et testez-la dans votre environnement d’évaluation.
1. Approuvez la bibliothèque et publiez-la en production.

Voir [Flux de publication](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/publishing-flow) dans le guide d’utilisation des balises.
