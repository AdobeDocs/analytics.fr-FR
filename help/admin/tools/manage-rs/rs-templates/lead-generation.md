---
description: Définit des paramètres courants pour un site Web qui fournit des informations sur des services et produits vendus généralement par le biais d’un engagement plus poussé.
title: Génération de pistes
feature: Report Suite Settings
exl-id: 4a629908-2bb4-4d61-a934-42906edff9df
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 100%

---

# Génération de pistes

Définit des paramètres courants pour un site web qui fournit des informations sur des services et produits vendus généralement par le biais d’un engagement plus poussé.

| Variables de conversion | Type | Sous-relations | Affectation | Expiration | Variable `s_code` |
|---|---|---|---|---|---|
| Promotion interne | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar1` |
| Termes de recherche internes | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar2` |
| Type d’événement en libre-service | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar3` |

Aucun événement de succès n’est configuré par ce modèle de suite de rapports.

| Variables Custom Insight | Variable `s_code` |
|---|---|
| Sécurisé / Non sécurisé | `prop1` |
| Propriété du trafic 2 à 5 | `prop2, prop3, prop4, prop5` |

Le tableau suivant contient une liste d’événements commerciaux standard. La configuration initiale de ces événements est identique dans tous les modèles de suite de rapports. Les événements dont la variable s_code est N/D ne doivent pas être définis ; ils sont fournis automatiquement.

| Événements commerciaux standard | Type | Variable `s_code` |
|---|---|---|
| Recettes | Compteur | `purchase` |
| Commandes | Compteur | `purchase` |
| Unités | Compteur | `purchase` |
| Paniers | Compteur | `scOpen` |
| Consultations du panier | Compteur | `scView` |
| Instances | Compteur | S.O. |
| Passages en caisse | Compteur | `scCheckout` |
| Ajouts au panier | Compteur | `scAdd` |
| Retraits du panier | Compteur | `scRemove` |
| Visites | Compteur (sans sous-relations) | S.O. |
| Pages vues | Compteur (sans sous-relations) | S.O. |
| Visiteurs uniques par jour | Compteur (sans sous-relations) | S.O. |
| Visiteurs uniques | Compteur (sans sous-relations) | S.O. |
