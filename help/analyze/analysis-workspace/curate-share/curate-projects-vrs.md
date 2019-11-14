---
title: Traitement des suites de rapports virtuelles et des projets
description: Découvrez comment traiter les composants et les projets des versions
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Traitement des suites de rapports virtuelles et des projets

Lorsque vous traitez des projets ou des suites de rapports virtuelles, vous excluez en fait les composants de façon à ce que l’audience voit uniquement les composants de projets/suites de rapports virtuelles (dimensions, mesures, segments et périodes) que vous voulez qu’elle utilise.

>[!Nnote]
>Les autorisations de composant sont le mécanisme principal qui détermine les composants qu’un utilisateur peut voir. Ils sont gérés par le biais des outils d’administration. Le traitement est un filtre secondaire.

Nous avons amélioré récemment l’expérience de traitement. Voici un aperçu de ce que révèle le bouton **[!UICONTROL Tout afficher], outre les composants traités déjà disponibles, dans différentes expériences traitées et par niveau d’autorisation :**

| Type de traitement | Administrateurs | Propriétaires de projets non-administrateurs | Non-administrateurs |
|---|---|---|---|
| Suites de rapports virtuelles non traitées | Tous les composants de suites de rapports virtuelles non traités | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité | Tous les composants de projets non traités | Tous les composants de projets non traités | Composants de projets non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité dans une de suite de rapports virtuelle traitée | Tous les composants non traités ci-dessous Composants **[de projet non traités]** UICONTROL et composants **[non traités VRS non traitésUICONTROL]** | Tous les composants de projet non traités ET les composants VRS non traités dont ce rôle est propriétaire ou qui ont été partagés avec eux | Composants de projets et de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |

>[!IMPORTANT]
>Le traitement VRS est toujours appliqué avant le traitement du projet. Ainsi, même si votre projet traité comprend certains composants, ils seront exclus si le traitement VRS traité ne les inclut pas.
