---
description: Définit des paramètres courants pour un site web qui regroupe du contenu, tel qu’un portail d’actualités.
title: Portail d’agrégation
feature: Report Suite Settings
exl-id: 48f57f27-289c-4e26-9fb2-e34d48c1f2e6
source-git-commit: 9057cc83881a72fa039e9398ed3daaf4259ef2bf
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 100%

---

# Portail d’agrégation

Définit des paramètres courants pour un site Web qui regroupe du contenu, tel qu’un portail d’actualités.

| Variables de conversion | Type | Sous-relations | Affectation | Expiration | Variable `s_code` |
|---|---|---|---|---|---|
| Campagne interne | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar1` |
| Termes de recherche internes | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar2` |
| Catégorie de renvoi | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar3` |

| Événements de succès | Type | Variable `s_code` |
|---|---|---|
| Connexion | Compteur (sans sous-relations) | `event1` |
| Vue de renvoi | Compteur (sans sous-relations) | `event2` |
| Clics de renvoi | Compteur (sans sous-relations) | `event3` |

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
| Achats | Compteur | `scCheckout` |
| Ajouts au panier | Compteur | `scAdd` |
| Retraits du panier | Compteur | `scRemove` |
| Visites | Compteur (sans sous-relations) | S.O. |
| Pages vues | Compteur (sans sous-relations) | S.O. |
| Visiteurs uniques par jour | Compteur (sans sous-relations) | S.O. |
| Visiteurs uniques | Compteur (sans sous-relations) | S.O. |
