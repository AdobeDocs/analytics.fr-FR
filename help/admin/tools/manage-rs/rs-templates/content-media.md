---
description: Définit des paramètres courants pour un site web qui développe du contenu original et affiche des articles et des vidéos.
title: Contenu et média
feature: Report Suite Settings
exl-id: 9983ff86-9341-4b01-b4f3-41042874a9fb
TQID: https://experienceleague.adobe.com/AASIeik0YkTmYjhAff09KB38tsBsYXiKgIawb5e5tAc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 215
ht-degree: 66%

---

# Contenu et média

Définit des paramètres courants pour un site web qui développe du contenu original et affiche des articles et des vidéos.

| Variables de conversion | Type | Sous-relations | Affectation | Expiration | Variable `s_code` |
|---|---|---|---|---|---|
| Campagne interne | Chaîne | De base | Le dernier | Visite | `evar1` |
| Termes de recherche internes | Chaîne | De base | Le dernier | Visite | `evar2` |
| Variable Commerce 3 | Chaîne | De base | Le dernier | Visite | `evar3` |
| Variable Commerce 4 | Chaîne | De base | Le dernier | Visite | `evar4` |

| Événements de succès | Type | Variable `s_code` |
|---|---|---|
| Enregistrements | Compteur (sans sous-relations) | `event1` |
| Enregistrements par e-mail | Compteur (sans sous-relations) | `event2` |
| Abonnements | Compteur (sans sous-relations) | `event3` |
| Pages vues | Compteur (sans sous-relations) | `event4` |
| Impressions publicitaires | Compteur (sans sous-relations) | `event5` |
| Clics publicitaires | Compteur (sans sous-relations) | `event6` |

| Variables Custom Insight | Variable `s_code` |
|---|---|
| Propriété du trafic 1 à 5 | `prop1, prop2, prop3, prop4, prop5` |

Le tableau suivant répertorie les événements commerciaux standard. La configuration initiale de ces événements est identique dans tous les modèles de suite de rapports. Les événements dont la variable s_code est N/D ne doivent pas être définis ; ils sont fournis automatiquement.

| Événements Commerce standard | Type | Variable `s_code` |
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
