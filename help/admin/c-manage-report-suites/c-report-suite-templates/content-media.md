---
description: Définit des paramètres courants pour un site web qui développe le contenu d’origine et affiche des articles et des vidéos.
seo-description: Définit des paramètres courants pour un site Web qui développe le contenu d’origine et affiche des articles et des vidéos.
seo-title: Contenu et média
solution: Analytics
title: Contenu et média
topic: Outils d’administration
uuid: 281 b 0 bf 8-59 dc -46 dc-b 5 d 5-5 e 42827 b 785 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Contenu et média

Définit des paramètres courants pour un site web qui développe le contenu d’origine et affiche des articles et des vidéos.

| Variables de conversion | Type | Sous-relations | Attribution | Expiration | `s_code` la variable |
|---|---|---|---|---|---|
| Campagne interne | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar1` |
| Termes de recherche internes | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar2` |
| Variable de commerce 3 | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar3` |
| Variable de commerce 4 | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar4` |

| Événements de succès | Type | `s_code` la variable |
|---|---|---|
| Inscriptions | Compteur (sans sous-relations) | `event1` |
| Enregistrements de courriel | Compteur (sans sous-relations) | `event2` |
| Abonnements | Compteur (sans sous-relations) | `event3` |
| Pages vues | Compteur (sans sous-relations) | `event4` |
| Impressions publicitaires | Compteur (sans sous-relations) | `event5` |
| Clics publicitaires | Compteur (sans sous-relations) | `event6` |

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

