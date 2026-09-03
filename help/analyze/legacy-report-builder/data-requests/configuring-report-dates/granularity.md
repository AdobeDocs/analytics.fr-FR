---
description: 'Sur le formulaire Assistant Requête : Étape 1, vous avez la possibilité d’appliquer un niveau de granularité à la requête de données. La granularité spécifie le niveau de détail temporel inclus dans le rapport.'
title: Granularité
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
TQID: https://experienceleague.adobe.com/26j4Fernl4bfuYeyuVVzw1K5hZvNSD6pDUVOfEc0J8s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 14%

---

# Granularité

{{legacy-arb}}

Dans l’Assistant Requête : étape 1, vous pouvez appliquer un niveau de granularité à la requête de données. La granularité spécifie le niveau de détail temporel inclus dans le rapport.

Les valeurs valides sont Heure, Jour, Semaine, Mois, Trimestre, Année et Agrégé.

## Traitement de la granularité par le Report Builder

Supposons que vous choisissiez une période d’un mois avec une granularité [!UICONTROL Mois]. Les demandes affichent des totaux pour la mesure en fonction de l’équivalent d’un mois de données exactement. Si la période de votre requête s’étend sur un trimestre, le rapport affiche trois chiffres : un pour chaque unité de mois, ou fraction de celle-ci. Si nous sommes aujourd&#39;hui le 18 mars, le choix du dernier trimestre renvoie un chiffre pour la période du 1er au 31 janvier, un autre chiffre pour la période du 1er au 28 février et un dernier chiffre pour la période du 1er au 17 mars.
