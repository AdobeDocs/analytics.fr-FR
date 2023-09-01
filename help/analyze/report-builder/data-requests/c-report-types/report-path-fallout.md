---
description: Décrit la manière dont Report Builder prend en charge les rapports de cheminement et d’abandons et dont l’implémentation diffère de Reports & Analytics.
title: Rapports Chemin et Abandon de chemin dans le Report Builder
feature: Report Builder
role: User, Admin
exl-id: 211b0e76-2895-401d-a5a5-73e459a486e2
source-git-commit: d218d07ec16e981d7e148092b91fbbd5711e840f
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 86%

---

# Rapports Chemin et Abandon de chemin dans le Report Builder

Décrit la manière dont Report Builder prend en charge les rapports de cheminement et d’abandons et dont l’implémentation diffère de Reports &amp; Analytics.

| Nom du rapport Chemin dans Reports &amp; Analytics (Chemins > dimension >) | Pris en charge dans le Report Builder ? |
|--- |--- |
| Flux de dimension suivant/précédent | Non fourni en tant que rapport autonome. Peut être reproduit avec plusieurs requêtes avec la dimension Chemin et en utilisant un filtre. |
| Suivant/Précédent dimension  | Non fourni en tant que rapport autonome. Peut être reproduit avec un rapport de cheminement et en utilisant un filtre. |
| Abandon | Pris en charge et fourni en tant que rapport autonome (Chemins > dimension > Abandon). |
| Chemins complets | Non pris en charge. |
| PathFinder | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport de cheminement utilisant un filtre. |
| Longueur de chemin | Pris en charge uniquement pour la dimension Page. |
| Analyse de page > Résumé des dimensions | Non fourni en tant que rapport autonome. Peut être reproduit avec plusieurs requêtes avec la dimension Chemin et en utilisant un filtre. |
| Analyse de page > Actualisations | Non fourni en tant que rapport autonome. Peut être reproduit avec un rapport Dimension utilisant la mesure Actualisations. |
| Analyse de page > Profondeur de dimension | Pris en charge uniquement pour la dimension Page. |
| Analyse de page > Durée de consultation de la dimension | Non pris en charge. |
| Entrées et sorties > Pages d’entrée | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport de cheminement utilisant le filtre prédéfini Site d’entrée. |
| Entrées et sorties > Pages d’entrée originales | Pris en charge uniquement pour la dimension Page. |
| Entrées et sorties > Visites sur une seule page | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport de cheminement utilisant un filtre prédéfini. |
| Entrées et sorties > Quitter la dimension | Non fourni en tant que rapport autonome. Peut être reproduit en tant que rapport Chemin utilisant le filtre prédéfini Site de sortie. |
