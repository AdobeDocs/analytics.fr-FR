---
title: Traitement des suites de rapports virtuelles et des projets
description: Découvrez comment traiter les composants et les projets des suites de rapports virtuelles
translation-type: tm+mt
source-git-commit: 8a662d03873d4699bf4166e825251f0f3e131537

---


# Traitement des suites de rapports virtuelles et des projets

Lorsque vous traitez des projets ou des suites de rapports virtuelles, vous excluez en fait les composants de façon à ce que l’audience voit uniquement les composants de projets/suites de rapports virtuelles (dimensions, mesures, segments et périodes) que vous voulez qu’elle utilise.

[!Note] :
>Les profils de produit sont le mécanisme principal qui détermine les composants qu’un utilisateur peut voir. They are managed through the [Admin Console](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles). Le traitement est un filtre secondaire.

Nous avons amélioré récemment l’expérience de traitement. Voici un aperçu de ce que révèle le bouton **[!UICONTROL Tout afficher]**, outre les composants traités déjà disponibles, dans différentes expériences traitées et par niveau d’autorisation :

| Type de traitement | Administrateurs | Propriétaires de projets non-administrateurs | Non-administrateurs |
|---|---|---|---|
| Suites de rapports virtuelles non traitées | Tous les composants de suites de rapports virtuelles non traités | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité | Tous les composants de projets non traités | Tous les composants de projets non traités | Composants de projets non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité dans une de suite de rapports virtuelle traitée | Tous les composants non traités ci-dessous **[!UICONTROL Non-Curated Project Components]**and**[!UICONTROL  Non-Curated VRS Components]** | Tous les composants de projets non traités ET les composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés | Composants de projets et de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |

[!IMPORTANT]
>Le traitement VRS est toujours appliqué avant le traitement du projet. Cela signifie que même si votre projet traité inclut certains composants, ils seront exclus si la suite de rapports virtuelle traitée ne les inclut pas.
