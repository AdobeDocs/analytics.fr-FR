---
description: Activez les dimensions et les mesures à utiliser dans le suivi des applications mobiles.
title: Rapports d’application
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 20%

---

# Rapports d’application

L’interface de création de rapports d’applications vous permet d’activer les dimensions et les mesures de cycle de vie dédiées à l’utilisation dans le suivi des applications mobiles.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Gestion des applications]** > **[!UICONTROL Rapports d’applications]**

>[!IMPORTANT]
>
>Une fois l’une de ces fonctions activée, elle ne peut plus être désactivée. L’activation d’une fonction donnée rend ses dimensions et mesures respectives disponibles de manière permanente dans Analysis Workspace.

## [!UICONTROL Rapports d’application]

[!UICONTROL Rapports d’application] les dimensions et les mesures sont utilisées aux fins suivantes :

* **Acquisition**: suivi des URL de référence pour les campagnes de téléchargement d’applications.
* **Cycle de vie**: niveau de base des rapports fourni par la mesure envoyée à chaque lancement de l’application.
* **Actions de l’application**: rapports et cheminement basés sur les actions in-app.
* **Valeur de durée de vie**: comprenez la manière dont les utilisateurs exploitent la valeur au fil du temps à l’aide des indicateurs de performance clés des applications (achats, vues de publicités, vidéos terminées, partages sur les réseaux sociaux, chargements de photos, etc.).
* **Événements minutés**: mesurez le temps qui s’écoule (dans l’application et durée totale) entre les actions clés de l’application (comme le temps avant le premier achat).

Lorsque [!UICONTROL Rapports d’application], les dimensions suivantes sont disponibles :

* [!UICONTROL Nom de l’action] (avec [Entrée](/help/components/dimensions/entry-dimensions.md) et [Quitter](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL ID application]
* [!UICONTROL Contenu de l’acquisition]
* [!UICONTROL Support d’acquisition]
* [!UICONTROL Nom de l’acquisition]
* [!UICONTROL Source de l’acquisition]
* [!UICONTROL Terme de l’acquisition]
* [!UICONTROL Jour de la semaine (SDK)]
* [!UICONTROL Jours depuis la première utilisation]
* [!UICONTROL Jours depuis la dernière utilisation]
* [!UICONTROL Nom de l’appareil (SDK)]
* [!UICONTROL Heure du jour (SDK)]
* [!UICONTROL Date du premier lancement]
* [!UICONTROL Numéro de lancement]
* [!UICONTROL Valeur de durée de vie (eVar).]
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

[!UICONTROL Suivi de l’emplacement] Les dimensions sont utilisées aux fins suivantes :

* Suivi des données de latitude et de longitude
* Identifiez, créez et visualisez des points ciblés spécifiques. Les points ciblés doivent être définis dans le fichier de configuration du SDK mobile.
* d’effectuer le suivi des balises bluetooth (UUID, majeur, mineur et proximité).

Lorsque [!UICONTROL Suivi de l’emplacement], les dimensions suivantes sont disponibles :

* [!UICONTROL Balise majeure] (avec [Entrée](/help/components/dimensions/entry-dimensions.md) et [Quitter](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL Balise mineure] (avec [Entrée](/help/components/dimensions/entry-dimensions.md) et [Quitter](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL Proximité de la balise] (avec [Entrée](/help/components/dimensions/entry-dimensions.md) et [Quitter](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL UUID de balise] (avec [Entrée](/help/components/dimensions/entry-dimensions.md) et [Quitter](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL Lieu (jusqu’à 10 km)]
* [!UICONTROL Lieu (jusqu’à 100 m)]
* [!UICONTROL Lieu (jusqu’à 1 m)]
* [!UICONTROL Nom du point ciblé]
* [!UICONTROL Distance jusqu’au centre du point ciblé]
* [!UICONTROL Identifiant du point ciblé]

## [!UICONTROL Voix et chatbots]

[!UICONTROL Voix et chatbots] les dimensions et les mesures vous permettent de mesurer les assistants vocaux tels qu’Alexa ou Google Home. Il vous permet également de mesurer les robots de conversation locaux. Les propriétés de mesure incluent :

* **Cycle de vie**: niveau de base de la création de rapports pour toute application, tel que le nombre de lancements et le type de plateforme.
* **Conversations**: mesure les intentions, les réponses, ainsi que d’autres mesures et dimensions liées à la conversation.

Lorsque [!UICONTROL Voix et chatbots], les dimensions suivantes sont disponibles :

* [!UICONTROL Fonctionnalités des appareils vocaux] (avec [Entrée](/help/components/dimensions/entry-dimensions.md) et [Quitter](/help/components/dimensions/exit-dimensions.md) dimensions)
* [!UICONTROL Authentification vocale]
* [!UICONTROL Type d’erreur de voix]
* [!UICONTROL Intention de voix]
* [!UICONTROL Réponse de l’application vocale]
* [!UICONTROL Langue de la voix]

Les mesures suivantes sont disponibles :

* [!UICONTROL Session de fin de voix]
* [!UICONTROL Erreur de voix]
* [!UICONTROL Témoignages vocaux]

## Création de rapports et attribution héritées pour les accès en arrière-plan

Les rapports hérités signifient que les accès générés lorsqu’une application est en arrière-plan sont traités comme des accès de premier plan standard. Elles apparaissent dans les rapports et affectent l’attribution. Cette configuration héritée est généralement souhaitable pour maintenir la cohérence avec les implémentations héritées.

Adobe recommande de désactiver les rapports hérités afin que les accès en arrière-plan ne soient pas visibles. Si vous souhaitez inclure des accès en arrière-plan dans votre analyse, vous pouvez activer la variable [Suite de rapports virtuelle](/help/components/vrs/vrs-about.md) paramètre **[!UICONTROL Inclure les accès en arrière-plan]**.
