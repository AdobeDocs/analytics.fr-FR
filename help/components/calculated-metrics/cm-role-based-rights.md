---
description: Les droits des mesures calculées diffèrent entre les utilisateurs administrateur et non administrateur.
title: Droits basés sur les rôles
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
TQID: https://experienceleague.adobe.com/M2ZwpkhpvhavBOwrVsDxcEYsS9kAFGAcuCl5TSUzxXU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 244
ht-degree: 75%

---

# Droits basés sur les rôles

Les droits des mesures calculées diffèrent entre les utilisateurs administrateur et non administrateur.

|  | Créez | Partager | Consulter/Gérer | Approuver | Appliquer |
|--- |--- |--- |--- |--- |--- |
| Utilisateurs de niveau administrateur | Pour limiter les droits de création de mesures calculées des utilisateurs, les administrateurs peuvent créer des mesures calculées ainsi que des profils de produits dans lʼAdmin Console. | Peuvent effectuer un partage avec l’ensemble de l’entreprise, avec des groupes d’utilisateurs et avec des utilisateurs individuels. | Report Builder : peut afficher/modifier/supprimer, etc. ses propres mesures calculées et celles qui sont partagées avec lui. | Peuvent approuver les mesures calculées comme étant canoniques. | Peuvent appliquer toute mesure calculée à l’échelle de l’entreprise. |
| Utilisateurs et utilisatrices ne disposant pas de droits d’administration | Par défaut, les utilisateurs peuvent créer des mesures calculées. Ces droits peuvent être toutefois limités par les administrateurs. | Peuvent effectuer un partage avec des utilisateurs individuels uniquement. | Peuvent afficher/modifier/supprimer, etc. uniquement leurs propres mesures calculées. Les utilisateurs non-administrateurs doivent avoir accès à tous les événements de composant pour pouvoir afficher des mesures partagées (les autorisations dans Admin Console sont toujours appliquées).  Si un tableau de bord ou un rapport planifié est partagé avec un utilisateur non administrateur et que la mesure n’est pas partagée avec les utilisateurs non administrateurs, le rapport s’exécute avec la mesure appliquée (en présumant qu’ils disposent des autorisations de consultation des événements). Néanmoins, les utilisateurs non administrateurs ne pourront pas consulter la définition ou modifier la mesure. | Ne peuvent utiliser que les mesures calculées approuvées ; ne peuvent pas les marquer comme approuvées. | Peuvent appliquer leurs propres mesures calculées et les segments qui ont été partagés avec eux. |
