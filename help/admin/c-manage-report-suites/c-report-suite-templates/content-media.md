---
description: Définit des paramètres courants pour un site Web qui développe le contenu d’origine et affiche des articles et des vidéos.
title: Contenu et média
feature: Outils d’administration
uuid: 281b0bf8-59dc-46dc-b5d5-5e42827b785d
exl-id: 9983ff86-9341-4b01-b4f3-41042874a9fb
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 100%

---

# Contenu et média

Définit des paramètres courants pour un site web qui développe le contenu d’origine et affiche des articles et des vidéos.

| Variables de conversion | Type | Sous-relations | Attribution | Expiration | Variable `s_code` |
|---|---|---|---|---|---|
| Campagne interne | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar1` |
| Termes de recherche internes | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar2` |
| Variable de commerce 3 | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar3` |
| Variable de commerce 4 | Chaîne | Élémentaire | Le plus récent (Dernier) | Visite | `evar4` |

| Événements de succès | Type | Variable `s_code` |
|---|---|---|
| Inscriptions | Compteur (sans sous-relations) | `event1` |
| Enregistrements de courriel | Compteur (sans sous-relations) | `event2` |
| Abonnements | Compteur (sans sous-relations) | `event3` |
| Pages vues | Compteur (sans sous-relations) | `event4` |
| Impressions publicitaires | Compteur (sans sous-relations) | `event5` |
| Clics publicitaires | Compteur (sans sous-relations) | `event6` |

| Variables Aperçu personnalisé | Variable `s_code` |
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
