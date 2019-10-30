---
description: Définit des paramètres courants pour un site web qui regroupe du contenu, tel qu’un portail d’actualités.
seo-description: Définit des paramètres courants pour un site web qui regroupe du contenu, tel qu’un portail d’actualités.
seo-title: Portail d’agrégation
solution: Analytics
title: Portail d’agrégation
topic: Outils d’administration
uuid: d227c209-4d88-4eff-b126-994b2a179c51
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Portail d’agrégation

Définit des paramètres courants pour un site web qui regroupe du contenu, tel qu’un portail d’actualités.

| Variables de conversion | Type | Sous-relations | Attribution | Expiration | `s_code` la variable |
|---|---|---|---|---|---|
| Campagne interne | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar1` |
| Termes de recherche internes | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar2` |
| Catégorie de renvoi | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar3` |

| Événements de succès | Type | `s_code` la variable |
|---|---|---|
| Connexion | Compteur (sans sous-relations) | `event1` |
| Vue de renvoi | Compteur (sans sous-relations) | `event2` |
| Clics de renvoi | Compteur (sans sous-relations) | `event3` |

| Variables Aperçu personnalisé | `s_code` la variable |
|---|---|
| Propriété du trafic 1 à 5 | `prop1, prop2, prop3, prop4, prop5` |

Le tableau suivant contient une liste d’événements commerciaux standard. La configuration initiale de ces événements est identique dans tous les modèles de suite de rapports. Les événements dont la variable s_code est N/D ne doivent pas être définis ; ils sont fournis automatiquement.

| Événements commerciaux standard | Type | `s_code` la variable |
|---|---|---|
| Recettes | Compteur | `purchase` |
| Commandes | Compteur | `purchase` |
| Unités | Compteur | `purchase` |
| Paniers | Compteur | `scOpen` |
| Consultations du panier | Compteur | `scView` |
| Instances | Compteur | N/D |
| Achats | Compteur | `scCheckout` |
| Ajouts au panier | Compteur | `scAdd` |
| Retraits du panier | Compteur | `scRemove` |
| Visites | Compteur (sans sous-relations) | N/D |
| Pages vues | Compteur (sans sous-relations) | N/D |
| Visiteurs uniques par jour | Compteur (sans sous-relations) | N/D |
| Visiteurs uniques | Compteur (sans sous-relations) | N/D |

