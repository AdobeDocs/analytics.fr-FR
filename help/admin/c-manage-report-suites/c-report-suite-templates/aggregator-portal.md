---
description: Définit des paramètres courants pour un site web qui regroupe du contenu, tel qu’un portail d’actualités.
seo-description: Définit des paramètres courants pour un site web qui regroupe du contenu, tel qu’un portail d’actualités.
seo-title: Portail d'agrégation
solution: Analytics
title: Portail d'agrégation
topic: Outils d’administration
uuid: d 227 c 209-4 d 88-4 eff-b 126-994 b 2 a 179 c 51
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Portail d'agrégation

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
| Passage en caisse | Compteur | `scCheckout` |
| Ajouts au panier | Compteur | `scAdd` |
| Retraits du panier | Compteur | `scRemove` |
| Visites | Compteur (sans sous-relations) | N/D |
| Pages vues | Compteur (sans sous-relations) | N/D |
| Visiteurs uniques par jour | Compteur (sans sous-relations) | N/D |
| Visiteurs uniques | Compteur (sans sous-relations) | N/D |

