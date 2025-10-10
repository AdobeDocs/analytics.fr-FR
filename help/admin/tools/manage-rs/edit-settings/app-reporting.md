---
description: Activez les dimensions et les mesures à utiliser dans le suivi des applications mobiles.
title: Rapports d’application
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '537'
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
* [!UICONTROL Medium d’acquisition]
* [!UICONTROL Nom de l’acquisition]
* [!UICONTROL Source d’acquisition]
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

Les mesures suivantes sont disponibles :

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

Les mesures suivantes sont disponibles :

* [!UICONTROL Session de fin vocale]
* [!UICONTROL Erreur vocale]
* [!UICONTROL Émissions de voix]

## Rapports et attribution hérités pour les accès en arrière-plan

Les rapports hérités signifient que les accès générés lorsqu’une application est en arrière-plan sont traités comme des accès de premier plan standard. Elles s’affichent dans les rapports et affectent l’attribution. Cette configuration héritée est généralement préférable pour maintenir la cohérence avec les implémentations héritées.

Adobe recommande de désactiver les rapports hérités afin que les accès en arrière-plan ne soient pas visibles. Si vous souhaitez inclure des accès en arrière-plan dans votre analyse, vous pouvez activer le paramètre [Suite de rapports virtuelle](/help/components/vrs/vrs-about.md) **[!UICONTROL Inclure des accès en arrière-plan]**.
