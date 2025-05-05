---
description: Activez les dimensions et les mesures à utiliser dans le suivi des applications mobiles.
title: Rapports d’application
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 13%

---

# Rapports d’application

L’interface de création de rapports d’applications vous permet d’activer les dimensions et les mesures de cycle de vie dédiées à l’utilisation dans le suivi des applications mobiles.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Gestion des applications]** > **[!UICONTROL Création de rapports d’applications]**

>[!IMPORTANT]
>
>Une fois l’une de ces fonctions activée, elle ne peut plus être désactivée. L’activation d’une fonction donnée rend ses dimensions et mesures respectives disponibles de manière permanente dans Analysis Workspace.

## [!UICONTROL Rapports d’applications]

Les dimensions et mesures [!UICONTROL Rapports d’applications] sont utilisées aux fins suivantes :

* **Acquisition** : suivi des URL de référence pour les campagnes de téléchargement d’applications.
* **Cycle de vie** : niveau de base des rapports fourni par la mesure envoyée à chaque lancement de l’application.
* **Actions de l’application** : rapports et cheminement basés sur les actions in-app.
* **Valeur de durée de vie** : comprendre comment les utilisateurs exploitent la valeur au fil du temps à l’aide des indicateurs de performance clés des applications (tels que les achats, vues de publicités, vidéos terminées, partages sur les réseaux sociaux, chargements de photos).
* **Événements minutés** : mesurez le temps qui s’écoule (dans l’application et durée totale) entre les actions clés de l’application (comme le temps avant le premier achat).

Lorsque vous activez les [!UICONTROL rapports d’application], les dimensions suivantes sont disponibles :

* [!UICONTROL Nom de l’action] (avec les dimensions [Entry](/help/components/dimensions/entry-dimensions.md) et [Exit](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL ID D’Application]
* [!UICONTROL Contenu de l’acquisition]
* [!UICONTROL Medium d’acquisition]
* [!UICONTROL Nom de l’acquisition]
* [!UICONTROL Source d’acquisition]
* [!UICONTROL Terme d’acquisition]
* [!UICONTROL Jour de la semaine (SDK)]
* [!UICONTROL Jours depuis la première utilisation]
* [!UICONTROL Jours depuis la dernière utilisation]
* [!UICONTROL Nom de l’appareil (SDK)]
* [!UICONTROL Heure de la journée (SDK)]
* [!UICONTROL Date du premier lancement]
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

* Suivi des données de latitude et de longitude
* Identifiez, créez et visualisez des points ciblés spécifiques. Les points ciblés doivent être définis dans le fichier de configuration du SDK mobile.
* d’effectuer le suivi des balises bluetooth (UUID, majeur, mineur et proximité).

Lorsque vous activez le [!UICONTROL suivi de l’emplacement], les dimensions suivantes sont disponibles :

* [!UICONTROL Balise majeure] (avec les dimensions [Entrée](/help/components/dimensions/entry-dimensions.md) et [Sortie](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Balise mineure] (avec les dimensions [Entrée](/help/components/dimensions/entry-dimensions.md) et [Sortie](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Proximité de la balise] (avec les dimensions [Entrée](/help/components/dimensions/entry-dimensions.md) et [Sortie](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL UID de balise &#x200B;] (avec les dimensions [Entrée](/help/components/dimensions/entry-dimensions.md) et [Sortie](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Lieu (jusqu’à 10 km)]
* [!UICONTROL Lieu (jusqu’à 100 m)]
* [!UICONTROL Lieu (jusqu’à 1 m)]
* [!UICONTROL Nom du point ciblé]
* [!UICONTROL Distance jusqu’au centre du point ciblé]
* [!UICONTROL ID de point ciblé]

## [!UICONTROL Voix et chatbots]

Les dimensions et mesures [!UICONTROL Voix et robots] vous permettent de mesurer les assistants vocaux tels que Alexa ou Google Home. Il vous permet également de mesurer les robots de conversation locaux. Les propriétés de mesure incluent :

* **Cycle de vie** : niveau de base de la création de rapports pour n’importe quelle application, comme le nombre de lancements et le type de plateforme.
* **Conversations** : mesure les intentions, les réponses, ainsi que d’autres mesures et dimensions liées à la conversation.

Lorsque vous activez [!UICONTROL Voix et Chatbots], les dimensions suivantes sont disponibles :

* [!UICONTROL Fonctionnalités de périphérique voix] (avec les dimensions [Entrée](/help/components/dimensions/entry-dimensions.md) et [Sortie](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Authentification vocale]
* [!UICONTROL Type d’erreur de voix]
* [!UICONTROL Mode voix]
* [!UICONTROL Réponse de l’application vocale]
* [!UICONTROL Langue de la voix]

Les mesures suivantes sont disponibles :

* [!UICONTROL Session de fin de voix]
* [!UICONTROL Erreur de voix]
* [!UICONTROL Audiences vocales]

## Création de rapports et attribution héritées pour les accès en arrière-plan

Les rapports hérités signifient que les accès générés lorsqu’une application est en arrière-plan sont traités comme des accès de premier plan standard. Elles apparaissent dans les rapports et affectent l’attribution. Cette configuration héritée est généralement souhaitable pour maintenir la cohérence avec les implémentations héritées.

Adobe recommande de désactiver les rapports hérités afin que les accès en arrière-plan ne soient pas visibles. Si vous souhaitez inclure des accès en arrière-plan dans votre analyse, vous pouvez activer le paramètre [Suite de rapports virtuelle](/help/components/vrs/vrs-about.md) **&#x200B;**&#x200B;avec accès en arrière-plan.
