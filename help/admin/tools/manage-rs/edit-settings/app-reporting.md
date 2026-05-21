---
description: Activez les dimensions et les mesures à utiliser dans le suivi des applications mobiles.
title: Rapports d’application
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
TQID: https://experienceleague.adobe.com/oF-tETs2-MWjSLoo5bVUmrr2nS4N1o2shD4DkMDAVLU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: c77ba355-6681-41fe-b719-563d3f507fdb
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 543
ht-degree: 13%

---

# Rapports d’application

L’interface de création de rapports d’application vous permet d’activer les dimensions et mesures de cycle de vie dédiées à une utilisation dans le suivi des applications mobiles.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Gestion des applications]** > **[!UICONTROL Reporting des applications]**

>[!IMPORTANT]
>
>Une fois que l’une de ces fonctionnalités est activée, elle ne peut pas être désactivée. L’activation d’une fonctionnalité donnée rend ses dimensions et mesures respectives disponibles en permanence dans Analysis Workspace.

## [!UICONTROL Rapports d’application]

Les dimensions et mesures [!UICONTROL Rapports d’application] sont utilisées aux fins suivantes :

* **Acquisition** : suivez les URL de référence pour les campagnes de téléchargement d’applications.
* **Cycle de vie** : niveau de base de création de rapports fourni par les mesures envoyées à chaque lancement d’application.
* **Actions de l’application** : rapports et cheminement basés sur des actions in-app.
* **Valeur de durée de vie** : comprenez comment les utilisateurs exploitent la valeur au fil du temps en utilisant des indicateurs clés de performance des applications tels que les achats, vues de publicités, vidéos terminées, partages sur les réseaux sociaux, chargements de photos.
* **Événements programmés** : mesurez le temps écoulé (temps in-app et temps total) entre les actions principales de l’application (par exemple, le temps avant le premier achat).

Lorsque vous activez [!UICONTROL Rapports d’application], les dimensions suivantes sont disponibles :

* [!UICONTROL &#x200B; Nom de l’action &#x200B;] (avec les dimensions [Entrée](/help/components/dimensions/entry-dimensions.md) et [Sortie](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL ID de l’application]
* [!UICONTROL Contenu d’acquisition]
* Medium d’acquisition
* [!UICONTROL Nom de l’acquisition]
* Source d’acquisition
* [!UICONTROL Terme d’acquisition]
* [!UICONTROL Jour de la semaine (SDK)]
* [!UICONTROL Jours depuis la première utilisation]
* [!UICONTROL Jours depuis la dernière utilisation]
* [!UICONTROL Nom de l’appareil (SDK)]
* [!UICONTROL Heure de la journée (SDK)]
* [!UICONTROL Première date de lancement]
* [!UICONTROL Numéro de lancement]
* [!UICONTROL Valeur de durée de vie (evar)]
* [!UICONTROL Version du système d’exploitation (SDK)]
* [!UICONTROL Résolution (SDK)]

Les mesures suivantes sont disponibles :

* [!UICONTROL Durée de l’action dans l’application]
* [!UICONTROL Durée totale de l’action]
* [!UICONTROL Blocages]
* [!UICONTROL Premiers lancements]
* [!UICONTROL Lancements]
* [!UICONTROL Valeur de durée de vie (événement)]
* [!UICONTROL Durée totale de la session]
* [!UICONTROL Mises à niveau]

## [!UICONTROL Suivi de l’emplacement]

Les dimensions [!UICONTROL Suivi de l’emplacement] sont utilisées aux fins suivantes :

* Suivre les données de latitude et de longitude
* Identifiez, créez et visualisez des points ciblés spécifiques. Les points ciblés doivent être définis dans le fichier de configuration de Mobile SDK.
* d’effectuer le suivi des balises bluetooth (UUID, majeur, mineur et proximité).

Lorsque vous activez le [!UICONTROL suivi de l’emplacement], les dimensions suivantes sont disponibles :

* [!UICONTROL Balise principale] (avec les dimensions [Entrée](/help/components/dimensions/entry-dimensions.md) et [Sortie](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Balise mineure] (avec les dimensions [Entrée](/help/components/dimensions/entry-dimensions.md) et [Sortie](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL &#x200B; Proximité de la balise &#x200B;] (avec les dimensions [Entrée](/help/components/dimensions/entry-dimensions.md) et [Sortie](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL UUID de balise] (avec dimensions [Entrée](/help/components/dimensions/entry-dimensions.md) et [Sortie](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Lieu (jusqu’à 10 km)]
* [!UICONTROL Lieu (jusqu’à 100 m)]
* [!UICONTROL Lieu (jusqu’à 1 m)]
* [!UICONTROL Nom du point ciblé]
* [!UICONTROL Distance jusqu’au centre du point ciblé]
* [!UICONTROL ID du point ciblé]

## [!UICONTROL Voix et chatbots]

[!UICONTROL Voix et robots de conversation] les dimensions et les mesures vous permettent de mesurer les assistants vocaux tels qu’Alexa ou Google Home. Il vous permet également de mesurer les robots de conversation développés sur place. Les propriétés de la mesure sont les suivantes :

* **Cycle de vie** : niveau de base de création de rapports pour toute application, comme le nombre de lancements et le type de plateforme.
* **Conversations** : mesures des intentions, des réponses et d’autres mesures et dimensions liées à la conversation.

Lorsque vous activez [!UICONTROL Voix et robots de conversation], les dimensions suivantes sont disponibles :

* [!UICONTROL Fonctionnalités des appareils vocaux] (avec les dimensions [Entrée](/help/components/dimensions/entry-dimensions.md) et [Sortie](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Authentification vocale]
* [!UICONTROL Type d’erreur vocale]
* [!UICONTROL Intention vocale]
* [!UICONTROL Réponse de l’application vocale]
* [!UICONTROL Langue vocale]

Les mesures suivantes sont disponibles :

* [!UICONTROL Session de fin vocale]
* [!UICONTROL Erreur vocale]
* [!UICONTROL Émissions de voix]

## Création de rapports et attribution héritées pour les accès en arrière-plan

Les rapports hérités signifient que les accès générés lorsqu’une application est en arrière-plan sont traités comme des accès de premier plan standard. Elles s’affichent dans les rapports et affectent l’attribution. Cette configuration héritée est généralement préférable pour maintenir la cohérence avec les implémentations héritées.

Adobe recommande de désactiver les rapports hérités afin que les accès en arrière-plan ne soient pas visibles. Si vous souhaitez inclure des accès en arrière-plan dans votre analyse, vous pouvez activer le paramètre [Suite de rapports virtuelle](/help/components/vrs/vrs-about.md) **[!UICONTROL Inclure des accès en arrière-plan]**.
