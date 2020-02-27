---
title: Traitement des suites de rapports virtuelles et des projets
description: Découvrez comment traiter les composants et les projets des suites de rapports virtuelles
translation-type: ht
source-git-commit: db983980a6ec3db4d60bbc8fc3ba57a4e1219287

---


# Traitement des suites de rapports virtuelles et des projets

Lorsque vous traitez des projets ou des suites de rapports virtuelles, vous excluez en fait les composants de façon à ce que l’audience voit uniquement les composants de projets/suites de rapports virtuelles (dimensions, mesures, segments et périodes) que vous voulez qu’elle utilise.

>[!NOTE]
>
>Les profils de produit constituent le principal mécanisme contrôlant ce que voit un utilisateur. Ils sont gérés au moyen d’[Admin Console](https://helpx.adobe.com/fr/enterprise/using/manage-products-and-profiles.html#createproductprofiles). Le traitement est un filtre secondaire.

Nous avons amélioré récemment l’expérience de traitement. Voici un aperçu de ce que révèle le bouton **[!UICONTROL Tout afficher]**, outre les composants traités déjà disponibles, dans différentes expériences traitées et par niveau d’autorisation :

| Type de traitement | Administrateurs | Propriétaires de projets non-administrateurs | Non-administrateurs |
|---|---|---|---|
| Suites de rapports virtuelles non traitées | Tous les composants de suites de rapports virtuelles non traités | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés | Composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité | Tous les composants de projets non traités | Tous les composants de projets non traités | Composants de projets non traités possédés par ce rôle ou avec lequel ils ont été partagés |
| Projet traité dans une de suite de rapports virtuelle traitée | Tous les composants non traités ci-dessous  **[!UICONTROL Composants de projets non traités]** et **[!UICONTROL Composants de suites de rapports virtuelles non traités]** | Tous les composants de projets non traités ET les composants de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés | Composants de projets et de suites de rapports virtuelles non traités possédés par ce rôle ou avec lequel ils ont été partagés |

>[!IMPORTANT]
>
>Le traitement des suites de rapports virtuelles est toujours appliqué avant le traitement du projet. Cela signifie que même si votre projet traité inclut certains composants, ils seront exclus si la suite de rapports virtuelle traitée ne les inclut pas.
