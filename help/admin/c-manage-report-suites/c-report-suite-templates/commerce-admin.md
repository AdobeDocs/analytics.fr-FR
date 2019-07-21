---
description: Définit des paramètres courants pour le site web de commerce électronique.
seo-description: Définit des paramètres courants pour le site Web de commerce électronique.
seo-title: Commerce
solution: Analytics
title: Commerce
topic: Outils d’administration
uuid: 85 fc 235 d -0180-4245-b 831-0243 ebe 3 c 40 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Commerce

Définit des paramètres courants pour le site web de commerce électronique.

| Variables de conversion | Type | Sous-relations | Attribution | Expiration | `s_code` la variable |
|---|---|---|---|---|---|
| Promotions internes | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar1` |
| Termes de recherche internes | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar2` |
| Catégorie de marchandisage | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar3` |
| Variable de commerce 4 | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar4` |
| Variable de commerce 5 | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar5` |

| Événements de succès | Type | `s_code` la variable |
|---|---|---|
| Inscriptions | Compteur (sans sous-relations) | `event1` |
| Événements personnalisés 1-5 | Compteur (sans sous-relations) | `event1, event2, event3, event4, event5` |

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

