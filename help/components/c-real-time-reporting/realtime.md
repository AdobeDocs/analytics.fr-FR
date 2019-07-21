---
description: Affiche le trafic des pages web et classe les pages vues en temps réel. Fournit des données pratiques pour vos prises de décision professionnelles.
seo-description: Affiche le trafic des pages web et classe les pages vues en temps réel. Fournit des données pratiques pour vos prises de décision professionnelles.
seo-title: Présentation des rapports en temps réel
solution: Analytics
title: Présentation des rapports en temps réel
topic: Présentation
uuid: ff 832952-c 507-4 c 63-9437-25 d 9 c 44 c 44 d 1
translation-type: tm+mt
source-git-commit: 5c13b8d8fa2fca85d89d0c22f6142a83a87d9975

---


# Présentation des rapports en temps réel

La création de rapports en temps réel affiche le trafic des pages Web et classe les pages vues en réel - temps. Fournit des données pratiques pour vos prises de décision professionnelles.

>[!NOTE]
>
>Le rapport Réel - Le rapport temporel ne nécessite aucune mise en œuvre ou aucun balisage supplémentaire. Elle repose sur le déploiement existant d’Adobe Analytics. Pour configurer les rapports en temps réel, voir [Configuration des rapports en temps réel](../../components/c-real-time-reporting/t-realtime-admin.md#task_1CD03E9B6BDB48B08E9E612183557F40).

**[!UICONTROL Mesures du site]** &gt; **[!UICONTROL Réel - Temps]**

Le rapport Temps réel répond aux questions suivantes : qu’est-ce qui est tendance sur mon site et pourquoi ? Il vous permet, en tant que marketeur, de réagir rapidement et de gérer de manière active les performances de vos contenus et campagnes marketing. Les données sont reportées en temps réel en moins de deux minutes et se mettent automatiquement à jour minute par minute.

![](assets/report-realtime.png)

Le tableau de bord comprend des mesures Adobe Analytics haute fréquence et des analyses de site pour rapporter visuellement les tendances de trafic et de pages vues des sites web d’informations et de vente au détail. Le rapport Temps réel identifie les tendances de vos données minute par minute, dans les secondes qui suivent la collecte. Il collecte et diffuse les données dans une interface automatiquement mise à jour, en utilisant la corrélation du temps réel et le suivi du contenu et de certaines conversions.

Deux des scénarios les plus fréquents concernent des éditeurs qui aimeraient promouvoir/rétrograder des articles au fur et à mesure que l’activité des utilisateurs change, ainsi que les marketeurs qui aimeraient effectuer un suivi sur le lancement d’une nouvelle gamme de produits.

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

N’oubliez pas que les eVars (mesures de conversion) ne sont pas prises en charge, puisqu’il n’y a aucun concept de permanence. Même si vous pouvez sélectionner des mesures de conversion, elles fonctionnent uniquement si elles sont définies sur la même page que la ou les dimensions. Pour en savoir plus, voir le message d’avertissement capturé dans la [Définition - Up Real - Time Reports](../../components/c-real-time-reporting/t-realtime-admin.md#task_1CD03E9B6BDB48B08E9E612183557F40).

Seuls les administrateurs ou les utilisateurs des groupes d’autorisations Accès à tous les rapports et Création de rapports avancés peuvent configurer et afficher les rapports Temps réel. Toutefois, cette fonction respecte les autorisations. Si, par exemple, vous n’avez pas les droits permettant de consulter le revenu, vous ne pourrez pas consulter un rapport en temps réel qui inclut les données de revenu.

## Latence des données suite à la configuration d’A4T {#section_806CE36354FC4C539A0DED9266A5C704}

After the A4T integration is enabled in Adobe [!DNL Target], you will experience an additional 5-10 minutes of latency in Adobe Analytics. This latency increase allows data from Analytics and [!DNL Target] to be stored on the same hit, allowing you to break down tests by page and site section.

Cette augmentation se reflète dans tous les services et outils d’Adobe Analytics, notamment la diffusion en continu active et la création de rapports en temps réel, et s’applique dans les scénarios suivants :

* Pour la diffusion en continu active, les rapports en temps réel, les requêtes d’API et les données actives pour les variables de trafic, seuls les accès avec un ID supplémentaire sont retardés.
* Pour les données actives sur les mesures de conversion, les données finalisées et les flux de données, tous les accès sont retardés de 5 à 7 minutes supplémentaires.

Notez que l'augmentation de latence commence après la mise en œuvre du service d'identité, même si vous n'avez pas entièrement implémenté cette intégration.
