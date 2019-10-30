---
description: Définit des paramètres courants pour les banques et autres institutions qui fournissent un accès à des services en ligne.
seo-description: Définit des paramètres courants pour les banques et autres institutions qui fournissent un accès à des services en ligne.
seo-title: Services financiers
solution: Analytics
title: Services financiers
topic: Outils d’administration
uuid: a321b409-24a4-4d9f-9aac-65761261e991
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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
| Achats | Compteur | `scCheckout` |
| Ajouts au panier | Compteur | `scAdd` |
| Retraits du panier | Compteur | `scRemove` |
| Visites | Compteur (sans sous-relations) | N/D |
| Pages vues | Compteur (sans sous-relations) | N/D |
| Visiteurs uniques par jour | Compteur (sans sous-relations) | N/D |
| Visiteurs uniques | Compteur (sans sous-relations) | N/D |

