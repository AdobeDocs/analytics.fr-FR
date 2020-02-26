---
description: Définit des paramètres courants pour les banques et autres institutions qui fournissent un accès à des services en ligne.
title: Services financiers
topic: Admin tools
uuid: a321b409-24a4-4d9f-9aac-65761261e991
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Services financiers

Définit des paramètres courants pour les banques et autres institutions qui fournissent un accès à des services en ligne.

| Variables de conversion (eVars) | Type | Sous-relations | Attribution | Expiration | Variable `s_code` |
|---|---|---|---|---|---|
| Promotion interne | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar1` |
| Termes de recherche internes | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar2` |
| Type d’événement en libre-service | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar3` |

Aucun événement de succès n’est configuré par ce modèle de suite de rapports.

| Variables Aperçu personnalisé | Variable `s_code` |
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
| Achats | Compteur | `scCheckout` |
| Ajouts au panier | Compteur | `scAdd` |
| Retraits du panier | Compteur | `scRemove` |
| Visites | Compteur (sans sous-relations) | S.O. |
| Pages vues | Compteur (sans sous-relations) | S.O. |
| Visiteurs uniques par jour | Compteur (sans sous-relations) | S.O. |
| Visiteurs uniques | Compteur (sans sous-relations) | S.O. |

