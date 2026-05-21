---
description: Définit les paramètres courants d’un site Web d’e-commerce.
title: Commerce
feature: Report Suite Settings
exl-id: 90e5d446-10b8-4d40-8bd0-8b13e1c2f603
TQID: https://experienceleague.adobe.com/l1-8tv-5dvKi4rx9-2tRoN4hK9ROr-ajWgKm0uFggrI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 69%

---

# Commerce

Définit les paramètres courants d’un site Web d’e-commerce.

| Variables de conversion | Type | Sous-relations | Affectation | Expiration | Variable `s_code` |
|---|---|---|---|---|---|
| Promotions internes | Chaîne | De base | Le dernier | Visite | `evar1` |
| Termes de recherche internes | Chaîne | De base | Le dernier | Visite | `evar2` |
| Catégorie de marchandisage | Chaîne | De base | Le dernier | Visite | `evar3` |
| Variable Commerce 4 | Chaîne | De base | Le dernier | Visite | `evar4` |
| Variable Commerce 5 | Chaîne | De base | Le dernier | Visite | `evar5` |

| Événements de succès | Type | Variable `s_code` |
|---|---|---|
| Enregistrements | Compteur (sans sous-relations) | `event1` |
| Événements personnalisés 1 à 5 | Compteur (sans sous-relations) | `event1, event2, event3, event4, event5` |

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
