---
description: L’identification des visiteurs sur plusieurs appareils vous aide à connecter des visiteurs sur plusieurs appareils. La fonction d’identification des visiteurs sur plusieurs périphériques utilise la variable d’identifiant visiteur, s.visitorID, pour associer des visiteurs.
keywords: Analytics Implementation
subtopic: Visitors
title: Connexion des utilisateurs à l’ensemble des appareils
topic: Developer and implementation
uuid: 6243957b-5cc1-49ef-aa94-5b5ec4eac313
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# Connexion des utilisateurs à l’ensemble des appareils

> [!IMPORTANT] Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la section Analyses [](/help/components/cda/cda-home.md) sur plusieurs périphériques dans le guide de l’utilisateur Composants.

L’identification des visiteurs sur plusieurs appareils vous aide à connecter des visiteurs sur plusieurs appareils. Cross-device visitor identification uses the `visitorID` variable to associate a user across devices. La `visitorID` variable a la priorité la plus élevée lors de l’identification des visiteurs uniques.

Lorsque vous envoyez un accès avec un ID de visiteur personnalisé, Adobe recherche les profils de visiteurs qui possèdent un ID de visiteur correspondant. S’il en existe un, le profil du visiteur déjà présent dans le système est utilisé à partir de ce moment et le profil du visiteur précédent n’est plus utilisé.

Setting the `visitorID` variable is typically set after authentication, or after a visitor performs some other action that allows you to uniquely identify them independently of the device that is used. Les identifiants efficaces comprennent un hachage de leur nom d’utilisateur, de leur adresse électronique ou d’un ID interne qui ne contient aucune information d’identification personnelle.

Une fois que le client s’est connecté à partir de chaque périphérique, il est lié au même profil utilisateur. Si le visiteur se déconnecte ultérieurement sur un périphérique, il continue d’appartenir au même profil du visiteur, car Adobe reconnaît que le cookie du navigateur sur chaque périphérique appartient au même profil du visiteur. Adobe recommande d’utiliser la `visitorID` variable chaque fois que cela est possible, au cas où le cookie du navigateur serait supprimé.

## Limites

L’utilisation de votre propre identifiant visiteur personnalisé vous permet de mieux contrôler la manière dont les visiteurs sont identifiés, mais ses limites s’appliquent.

* **La déduplication des visiteurs n’est pas rétroactive**: Si un visiteur accède à votre site pour la première fois, puis s’authentifie, deux visiteurs uniques sont comptabilisés. Un visiteur unique compte pour l’identifiant Analytics générique généré automatiquement et un autre compte pour l’identifiant visiteur personnalisé lorsqu’il se connecte. Cette duplication des visiteurs uniques est présente à chaque fois qu’un visiteur utilise un nouvel appareil ou efface ses cookies.
* **Incompatibilité avec le service** d’ID Experience Cloud : Depuis l’introduction de l’identification des visiteurs sur plusieurs périphériques, Adobe a publié des méthodes plus puissantes et plus fiables pour suivre les visiteurs sur différents périphériques. Ces nouvelles méthodes d’identification ne sont pas compatibles avec le remplacement de l’identifiant visiteur personnalisé. Si vous prévoyez d’utiliser le service d’ID, Analytics sur plusieurs périphériques (CDA) ou la coopération de périphériques, Adobe recommande vivement de ne pas utiliser la `visitorID` variable.
