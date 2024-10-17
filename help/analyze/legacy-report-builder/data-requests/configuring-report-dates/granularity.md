---
description: 'Sur le formulaire Assistant Requête : Étape 1, vous avez la possibilité d’appliquer un niveau de granularité à la requête de données. La granularité définit le niveau des détails temporels inclus dans le rapport.'
title: Granularité
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 100%

---

# Granularité

{{legacy-arb}}

Sur le formulaire Assistant Requête : Étape 1, vous avez la possibilité d’appliquer un niveau de granularité à la requête de données. La granularité définit le niveau des détails temporels inclus dans le rapport.

Les valeurs acceptées sont Heure, Jour, Semaine, Mois, Trimestre, Année et Agrégé.

## Traitement de la granularité par le Report Builder

Supposons que vous choisissiez une plage de dates pour un mois avec la granularité [!UICONTROL Mois]. Les requêtes affichent les totaux de la mesure sur la base de l’équivalent d’un mois de données. Si la plage de données de votre requête couvre un trimestre, le rapport affiche trois chiffres : un pour chaque unité de mois ou partie de celle-ci. Si nous sommes aujourd’hui le 18 mars, la sélection du dernier trimestre renvoie un graphique pour la période allant du 1er au 31 janvier, un autre pour la période du 1er au 28 février et un dernier pour la période du 1er au 17 mars.
