---
description: Affiche le trafic des pages web et classe les pages vues en temps réel. Fournit des données pratiques pour vos prises de décision professionnelles.
title: Création de rapports en temps réel - Aperçu
topic-fix: Reports
feature: Real-time
exl-id: 056235bc-42ea-4118-aa54-bc7666044fe3
TQID: https://experienceleague.adobe.com/2QizNDKGlAUqX7IbHANm-nGMicLXDfKSnl7nYGkETxQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 633
ht-degree: 88%

---

# Création de rapports en temps réel - Aperçu

Les rapports en temps réel affichent le trafic des pages web et classe les pages vues en temps réel. Fournit des données pratiques pour vos prises de décision professionnelles.

>[!NOTE]
>
>Les rapports en temps réel ne nécessitent aucune mise en œuvre ni aucun balisage supplémentaire. Elle repose sur le déploiement existant d’Adobe Analytics. Pour configurer les rapports en temps réel, voir [Configuration des rapports en temps réel](/help/admin/tools/manage-rs/edit-settings/realtime/t-realtime-admin.md).

## Accès aux rapports en temps réel

1. Dans Analysis Workspace, sélectionnez l’onglet [!UICONTROL **Workspace**].

1. Sur le côté gauche de la page, sous **[!UICONTROL Modèles]**, sélectionnez [!UICONTROL **Modèles Adobe**].

1. Sélectionnez [!UICONTROL **Engagement**] > **[!UICONTROL Temps réel]**.

## Présentation des rapports en temps réel

Le rapport Temps réel répond aux questions suivantes : qu’est-ce qui est tendance sur mon site et pourquoi ? Il vous permet, en tant que spécialiste marketing, de réagir rapidement et de gérer de manière active les performances de vos contenus et campagnes marketing. Les données sont reportées en temps réel en moins de deux minutes et se mettent automatiquement à jour minute par minute.

![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report-realtime.png)

Le tableau de bord comprend des mesures Adobe Analytics haute fréquence et des analyses de site pour rapporter visuellement les tendances de trafic et de pages vues des sites web d’informations et de vente au détail. Le rapport Temps réel identifie les tendances de vos données minute par minute, dans les secondes qui suivent la collecte. Il collecte et diffuse les données dans une interface automatiquement mise à jour, en utilisant la corrélation du temps réel et le suivi du contenu et de certaines conversions.

Deux des scénarios les plus fréquents concernent des éditeurs qui aimeraient promouvoir/rétrograder des articles au fur et à mesure que l’activité des utilisateurs change, ainsi que les spécialistes marketing qui aimeraient effectuer un suivi sur le lancement d’une nouvelle gamme de produits.

En tant qu’administrateur, vous pouvez :

* Créer jusqu’à trois rapports en temps réel par suite de rapports, en utilisant les dimensions ou classifications et mesures existantes. Utiliser les dimensions secondaires pour établir une corrélation avec (ou une ventilation de) la dimension primaire.
* Ajouter trois dimensions (ou classifications) par rapport (une principale et deux secondaires), en sus d’une mesure à l’échelle du site.
* Utiliser tout événement personnalisé, événement de panier ou instance.
* Afficher jusqu’à 2 heures de données historiques de temps réel et modifier ce paramètre :

   * 15 dernières minutes : granularité d’une minute
   * 30 dernières minutes : granularité d’une minute
   * Dernière heure : granularité de deux minutes
   * 2 dernières heures : granularité de quatre minutes

* Comparer par exemple les valeurs de la semaine dernière à celles de l’année dernière (ainsi qu’au total d’aujourd’hui).

N’oubliez pas que les eVars (mesures de conversion) ne sont pas prises en charge, puisqu’il n’y a aucun concept de permanence. Même si vous pouvez sélectionner des mesures de conversion, elles fonctionnent uniquement si elles sont définies sur la même page que la ou les dimensions. Pour plus d’informations, voir le message d’avertissement capturé dans [Configuration de rapports en temps réel](/help/components/c-real-time-reporting/t-realtime-admin.md).

Seuls les administrateurs ou les utilisateurs des groupes d’autorisations Accès à tous les rapports et Création de rapports avancés peuvent configurer et afficher les rapports Temps réel. Toutefois, cette fonction respecte les autorisations. Si, par exemple, vous n’avez pas les droits permettant de consulter le revenu, vous ne pourrez pas consulter un rapport en temps réel qui inclut les données de revenu.

## Latence des données suite à la configuration d’A4T {#latency-a4t}

Une fois l’intégration A4T activée dans Adobe [!DNL Target], vous remarquerez une latence supplémentaire de 5 à 10 minutes dans Adobe Analytics. Cette augmentation de la latence permet aux données provenant d’Analytics et de [!DNL Target] d’être stockées sur le même accès, permettant de ventiler les tests par page et par section de site.

Cette augmentation se reflète dans tous les services et outils d’Adobe Analytics, notamment la diffusion en continu active et la création de rapports en temps réel, et s’applique dans les scénarios suivants :

* Pour la diffusion en direct, les rapports en temps réel et les requêtes d’API, ainsi que les données actives pour les variables de trafic, seuls les accès avec un ID de données supplémentaire sont retardés.
* Pour les données actives sur les mesures de conversion, les données finalisées et les flux de données, tous les accès sont retardés de 5 à 7 minutes supplémentaires.

Gardez à l’esprit que l’augmentation de latence débute une fois que vous avez implémenté le service d’identité, même si vous n’avez pas entièrement implémenté cette intégration.
