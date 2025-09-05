---
description: Les droits des mesures calculées diffèrent entre les utilisateurs administrateur et non administrateur.
title: Droits basés sur les rôles
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 81%

---

# Droits basés sur les rôles

Les droits des mesures calculées diffèrent entre les utilisateurs administrateur et non administrateur.

|  | Créez | Partager | Consulter/Gérer | Approuver | Appliquer |
|--- |--- |--- |--- |--- |--- |
| Utilisateurs de niveau administrateur | Pour limiter les droits de création de mesures calculées des utilisateurs, les administrateurs peuvent créer des mesures calculées ainsi que des profils de produits dans lʼAdmin Console. | Peuvent effectuer un partage avec l’ensemble de l’entreprise, avec des groupes d’utilisateurs et avec des utilisateurs individuels. | Report Builder : peut afficher/modifier/supprimer, etc. ses propres mesures calculées et celles partagées avec lui. | Peuvent approuver les mesures calculées comme étant canoniques. | Peuvent appliquer toute mesure calculée à l’échelle de l’entreprise. |
| Utilisateurs et utilisatrices ne disposant pas de droits d’administration | Par défaut, les utilisateurs peuvent créer des mesures calculées. Ces droits peuvent être toutefois limités par les administrateurs. | Peuvent effectuer un partage avec des utilisateurs individuels uniquement. | Peuvent afficher/modifier/supprimer, etc. uniquement leurs propres mesures calculées. Les utilisateurs non-administrateurs doivent avoir accès à tous les événements de composant pour pouvoir afficher des mesures partagées (les autorisations dans Admin Console sont toujours appliquées).  Si un tableau de bord ou un rapport planifié est partagé avec un utilisateur non administrateur et que la mesure n’est pas partagée avec les utilisateurs non administrateurs, le rapport s’exécute avec la mesure appliquée (en présumant qu’ils disposent des autorisations de consultation des événements). Néanmoins, les utilisateurs non administrateurs ne pourront pas consulter la définition ou modifier la mesure. | Ne peuvent utiliser que les mesures calculées approuvées ; ne peuvent pas les marquer comme approuvées. | Peuvent appliquer leurs propres mesures calculées et les segments qui ont été partagés avec eux. |
