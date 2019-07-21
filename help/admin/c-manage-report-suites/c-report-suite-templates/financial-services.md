---
description: Définit des paramètres courants pour les banques et autres institutions qui fournissent un accès à des services en ligne.
seo-description: Définit des paramètres courants pour les banques et autres institutions qui fournissent un accès à des services en ligne.
seo-title: Services financiers
solution: Analytics
title: Services financiers
topic: Outils d’administration
uuid: a 321 b 409-24 a 4-4 d 9 f -9 aac -65761261 e 991
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Services financiers

Définit des paramètres courants pour les banques et autres institutions qui fournissent un accès à des services en ligne.

| Variables de conversion (eVars) | Type | Sous-relations | Attribution | Expiration | `s_code` la variable |
|---|---|---|---|---|---|
| Promotion interne | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar1` |
| Termes de recherche internes | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar2` |
| Type d’événement en libre-service | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar3` |

Aucun événement de succès n’est configuré par ce modèle de suite de rapports.

| Variables Aperçu personnalisé | `s_code` la variable |
|---|---|
| Sécurisé / Non sécurisé | `prop1` |
| Propriété du trafic 2 à 5 | `prop2, prop3, prop4, prop5` |

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

