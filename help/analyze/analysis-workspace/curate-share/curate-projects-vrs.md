---
title: Traitement des suites de rapports virtuelles et des projets
seo-title: Traiter les projets et les suites de rapports virtuelles dans Analysis Workspace
description: Découvrez comment traiter les composants et les projets de la suite de rapports virtuelle
seo-description: Traiter les suites de rapports virtuelles et traiter les projets
translation-type: tm+mt
source-git-commit: 0b56838e966aaf4cfa5c2685dd8335adbbbf11a7

---


# Traitement des suites de rapports virtuelles et des projets

Lorsque vous traitez des projets ou des suites de rapports virtuelles, vous excluez en fait les composants de façon à ce que l’audience voit uniquement les composants de projets/suites de rapports virtuelles (dimensions, mesures, segments et périodes) que vous voulez qu’elle utilise.

>[!Note]
>Les autorisations des composants constituent le mécanisme principal qui régit les composants visibles par un utilisateur. Ils sont gérés via les outils d'administration. Le traitement est un filtre secondaire.

Nous avons amélioré récemment l’expérience de traitement. Voici un aperçu de ce que révèle le bouton **[!UICONTROL Tout afficher], outre les composants traités déjà disponibles, dans différentes expériences traitées et par niveau d’autorisation :**

| Type de traitement | Administrateurs | Propriétaires de projets non-administrateurs | Non-administrateurs |
|---|---|---|---|
| Suites de rapports virtuelles non traitées | Tous les composants de suites de rapports virtuelles non traités | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité | Tous les composants de projets non traités | Tous les composants de projets non traités | Composants de projets non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité dans une de suite de rapports virtuelle traitée | Tous les composants non traités ci-dessous **[Composants de projet UICONTR]** et **[composants UICONTR non traités]** | Tous les composants de projet non traités ET les composants virtuels non organisés que ce rôle détient ou qui ont été partagés avec eux | Composants de projets et de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |

>[!IMPORTANT]
>La fonction de traitement des suites de rapports virtuelles est toujours appliquée avant la traitement du projet. De ce fait, même si votre projet traité inclut certains composants, ils seront filtrés si la suite de rapports virtuelle traitée ne les inclut pas.
