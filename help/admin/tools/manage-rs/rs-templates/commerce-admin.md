---
description: Définit des paramètres courants pour le site Web de commerce électronique.
title: Commerce
feature: Report Suite Settings
exl-id: 90e5d446-10b8-4d40-8bd0-8b13e1c2f603
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 100%

---

# Commerce

Définit des paramètres courants pour le site web de commerce électronique.

| Variables de conversion | Type | Sous-relations | Affectation | Expiration | Variable `s_code` |
|---|---|---|---|---|---|
| Promotions internes | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar1` |
| Termes de recherche internes | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar2` |
| Catégorie de marchandisage | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar3` |
| Variable de commerce 4 | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar4` |
| Variable de commerce 5 | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar5` |

| Événements de succès | Type | Variable `s_code` |
|---|---|---|
| Inscriptions | Compteur (sans sous-relations) | `event1` |
| Événements personnalisés 1-5 | Compteur (sans sous-relations) | `event1, event2, event3, event4, event5` |

| Variables Custom Insight | Variable `s_code` |
|---|---|
| Propriété du trafic 1 à 5 | `prop1, prop2, prop3, prop4, prop5` |

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
