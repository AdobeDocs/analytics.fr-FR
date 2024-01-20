---
description: Décrit la façon de définir les autorisations ainsi que les dimensions disponibles dans Analytics.
title: Création de rapports Activity Map dans Analytics
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 78%

---

# Création de rapports Activity Map dans Analytics

Décrit la façon de définir les autorisations ainsi que les dimensions disponibles dans Analytics.

## Définition des autorisations {#permissions}

Pour que les utilisateurs puissent créer des rapports sur les dimensions Activity Map, vous devez, en tant qu’administrateur :

* [Ajout d’utilisateurs au profil de produit Accès des Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* Personnaliser l’accès des utilisateurs aux dimensions. Voir la section suivante.

## Dimensions du Activity Map Analytics {#dimensions}

Vous pouvez [personnaliser l’accès des utilisateurs aux dimensions](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) à un niveau granulaire. Les dimensions Activity Map suivantes sont disponibles dans Analytics :

| Dimension | Description |
|---|---|
| Page Activity Map | Répertorie les pages sur lesquelles un utilisateur a cliqué sur un lien. |
| Région d’Activity Map | Répertorie toutes les régions de lien collectées sur l’ensemble du site web. Notez que si une région apparaît sur plusieurs pages, la mesure sera intégrée à chacune d’entre elles. |
| Liens d’Activity Map | Répertorie tous les liens collectés sur l’ensemble du site web. |
| Liens et région d’Activity Map | Répertorie tous les liens collectés avec leur région sur l’ensemble du site web. |
| Coordonnées d’Activity Map | Non utilisée |

* Ces dimensions doivent être disponibles dans Analysis Workspace et Report Builder, à condition que votre mise en oeuvre Analytics soit [activé pour Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* Dans Analysis Workspace, extrayez les dimensions liées à Activitymap dans un rapport.
* Pour consulter un lien ou une région d’une page spécifique, il suffit de créer une répartition à partir de la page Activity Map souhaitée dans Liens et région d’Activity Map.
