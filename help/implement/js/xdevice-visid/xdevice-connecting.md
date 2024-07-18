---
description: L’identification des visiteurs sur plusieurs appareils vous aide à connecter des visiteurs sur plusieurs appareils. La fonction d’identification des visiteurs sur plusieurs appareils utilise la variable d’identifiant visiteur, s.visitorID, pour associer des visiteurs.
keywords: Mise en œuvre d’Analytics
subtopic: Visitors
title: Connexion des utilisateurs à l’ensemble des appareils
feature: Implementation Basics
exl-id: dfe278db-01de-4bba-b07a-66d52de1dbe2
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 95%

---

# Connexion des utilisateurs à l’ensemble des appareils

>[!IMPORTANT]
>
>Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la section [Analytics sur l’ensemble des appareils](/help/components/cda/overview.md) dans le guide d’utilisation des composants.

L’identification des visiteurs sur plusieurs appareils vous aide à connecter des visiteurs sur plusieurs appareils. La fonction d’identification des visiteurs sur plusieurs appareils utilise la variable `visitorID` pour associer des visiteurs. La variable `visitorID` a la priorité la plus élevée lors de l’identification des visiteurs uniques.

Lorsque vous envoyez un accès avec un identifiant de visiteur personnalisé, Adobe recherche les profils de visiteurs qui possèdent un identifiant de visiteur correspondant. Le cas échéant, le profil du visiteur qui figure déjà dans le système est utilisé à partir de ce moment et le profil précédent est abandonné.

En règle générale, l’identifiant visiteur `visitorID` est défini après l’authentification ou après qu’un visiteur a effectué une autre action vous permettant de l’identifier de manière unique, indépendamment de l’appareil utilisé. Les identifiants efficaces comprennent un hachage de leur nom d’utilisateur, de leur adresse e-mail ou d’un identifiant interne qui ne contient aucune information d’identification personnelle.

Une fois que le client s’est connecté à partir de chaque appareil, il est lié au même profil utilisateur. Si le visiteur se déconnecte ultérieurement sur un appareil, il continue d’appartenir au même profil du visiteur, car Adobe reconnaît que le cookie du navigateur sur chaque appareil appartient au même profil du visiteur. Adobe recommande d’utiliser la variable `visitorID` chaque fois que cela est possible, au cas où le cookie du navigateur serait supprimé.

## Limites

L’utilisation de votre propre identifiant visiteur personnalisé vous permet de mieux contrôler la manière dont les visiteurs sont identifiés, mais ses limites s’appliquent.

* **La déduplication des visiteurs n’est pas rétroactive** : si un visiteur accède à votre site pour la première fois, puis s’authentifie, deux visiteurs uniques sont comptabilisés. Un visiteur unique compte pour l’identifiant Analytics générique généré automatiquement et un autre compte pour l’identifiant visiteur personnalisé lorsqu’il se connecte. Cette duplication des visiteurs uniques est présente à chaque fois qu’un visiteur utilise un nouvel appareil ou efface ses cookies.
* **Incompatibilité avec le service Experience Cloud ID :** depuis l’introduction de l’identification des visiteurs sur plusieurs appareils, Adobe a publié des méthodes plus puissantes et plus fiables pour suivre les visiteurs sur différents appareils. Ces nouvelles méthodes d’identification ne sont pas compatibles avec le remplacement de l’identifiant visiteur personnalisé. Si vous prévoyez d’utiliser le service d’ID ou Analytics sur l’ensemble des appareils (CDA), Adobe recommande vivement de ne pas utiliser la variable `visitorID`.
