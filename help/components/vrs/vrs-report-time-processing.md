---
description: Le traitement de la période de rapport est un paramètre des suites de rapports virtuelles qui permet aux données d’être traitées de façon rétroactive et non destructrice.
title: Traitement de la période de rapport
role: Admin
solution: Analytics
feature: VRS
exl-id: 3742b9d1-f1fb-4690-bd44-b4719ff9d9bc
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 68%

---

# Traitement de la période de rapport

Le [!UICONTROL traitement de la période de rapport] est un paramètre des suites de rapports virtuelles qui permet aux données d’Analysis Workspace d’être traitées de manière rétroactive et non destructive.

Le [!UICONTROL traitement de la période de rapport] affecte uniquement les données de la suite de rapports virtuelle et n’a aucune incidence sur les données ou la collecte de données dans la suite de rapports de base. La différence entre le [!UICONTROL traitement de la période de rapport] et le traitement Analytics classique est plus facile à comprendre à l’aide du diagramme suivant :

![Pipeline de traitement traditionnel](assets/google1.jpg)

Lors du traitement des données Analytics, les données circulent dans le pipeline de collecte de données et dans une étape de prétraitement qui prépare les données pour la création de rapports. Cette étape de prétraitement applique une logique d’expiration de visite et une logique de persistance des eVars (entre autres) aux données lors de leur collecte. Le principal inconvénient de ce modèle de prétraitement est qu’il nécessite une configuration préalable, avant la collecte des données. Cela signifie, qu’à partir de ce moment-là, les modifications apportées aux paramètres de prétraitement s’appliquent uniquement aux nouvelles données. Cela pose problème si les données n’arrivent pas dans l’ordre ou si les paramètres ont été mal configurés.

Le [!UICONTROL traitement de la période de rapport] est une manière fondamentalement différente de traiter les données Analytics pour la création de rapports. Au lieu de prédéterminer la logique de traitement avant la collecte des données, Analytics ignore le jeu de données pendant l’étape de prétraitement et applique cette logique chaque fois qu’un rapport est exécuté :

![Pipeline de traitement de la période de rapport](assets/google2.jpg)

Cette architecture de traitement offre des options de création de rapports beaucoup plus flexibles. Par exemple, vous pouvez modifier la période de temporisation de la visite sur la durée de votre choix de manière non destructive. Ces modifications se reflètent dans la persistance de l’eVar et dans les conteneurs de segments pour la période de création de rapports complète. En outre, vous pouvez créer un nombre illimité de suites de rapports virtuelles, chacune avec des options de traitement de la période de rapport différentes, basées sur la même suite de rapports de base (parente), sans modifier les données de cette dernière.

[!UICONTROL Traitement de la période de rapport] permet également à Analytics d’empêcher les accès en arrière-plan de démarrer de nouvelles visites et permet au [SDK Adobe Experience Platform Mobile](https://experienceleague.adobe.com/docs/mobile.html?lang=fr) de démarrer une nouvelle visite chaque fois qu’un événement de lancement d’application est déclenché.

## Options de configuration

Les options de configuration suivantes sont actuellement disponibles pour les suites de rapports virtuelles pour lesquelles le traitement de la période de rapport est activé :

* **[!UICONTROL Délai de visite] :** le paramètre Délai de visite définit le délai d’inactivité d’un visiteur unique avant qu’une nouvelle visite ne soit lancée automatiquement. Par défaut, il est fixé à 30 minutes. Par exemple, si vous définissez le délai de visite sur 15 minutes, un nouveau groupe de visites est créé pour chaque séquence d’accès collectés, séparé par 15 minutes d’inactivité. Ce paramètre impacte non seulement le nombre de visites, mais également la manière dont les conteneurs de segments de visite sont évalués, ainsi que la logique d’expiration de la visite pour les eVars expirant lors de la visite. La réduction du délai de visite augmentera probablement le nombre total de visites dans les rapports, tandis que l’augmentation du délai de visite réduira probablement le nombre total de visites dans les rapports.
* **[!UICONTROL Paramètres de visite pour les applications mobiles] :** pour les suites de rapports contenant des données générées par des applications mobiles via les [SDK Adobe Mobile](https://experienceleague.adobe.com/docs/mobile.html?lang=fr), des paramètres de visite supplémentaires sont disponibles. Ces paramètres sont non destructifs et affectent uniquement les accès collectés via les SDK Mobile. Ces paramètres n’ont aucun impact sur les données collectées en dehors du SDK Mobile.
* **[!UICONTROL Empêcher les accès en arrière-plan de commencer une nouvelle visite] :** les accès en arrière-plan sont collectés par les SDK mobiles lorsque l’application est en arrière-plan.
* **[!UICONTROL Démarrer de nouvelles visites à chaque lancement d’une application] :** en plus du délai de visite, vous pouvez forcer une visite à démarrer chaque fois qu’un événement de lancement d’application est enregistré depuis les SDK Mobile, quelle que soit la fenêtre d’inactivité. Ce paramètre affecte la mesure des visites et le conteneur de segments de visite, ainsi que la logique d’expiration de visite des eVars.
* **[!UICONTROL Démarrer une nouvelle visite avec un événement] :** une nouvelle session démarre lorsqu’un événement est déclenché, qu’une session ait expiré ou non. La session nouvellement créée inclut l’événement à l’origine de son démarrage. De plus, vous pouvez utiliser plusieurs événements pour démarrer une session. Une nouvelle session se déclenche alors si l’un de ces événements est observé dans les données. Ce paramètre aura un impact sur le nombre de visites, sur le conteneur de segmentation des visites et sur la logique d’expiration de visite des eVars.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Démarrage d’une nouvelle visite avec l’événement](https://video.tv.adobe.com/v/23129?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]



## Limites du traitement de la période de rapport

Le traitement de la période de rapport ne prend pas en charge toutes les mesures et dimensions disponibles dans la création de rapports Analytics traditionnelle. Les suites de rapports virtuelles utilisant le report de traitement du temps sont accessibles uniquement dans Analysis Workspace. Elles ne sont pas accessibles dans le Data Warehouse, le Report Builder, les flux de données ou l’API de création de rapports.

En outre, le traitement de la période de rapport traite uniquement les données comprises dans la plage de dates de création de rapports (appelée « fenêtrage de dates » ci-dessous). Cela signifie que les valeurs eVar définies sur « ne jamais expirer » pour un visiteur antérieurement à la plage de dates de création de rapports ne sont pas conservées dans les fenêtres de création de rapports et n’apparaissent pas dans les rapports. Cela signifie également que les mesures de fidélisation des clients sont basées exclusivement sur les données présentes dans la plage de dates de création de rapports et non sur l’ensemble de l’historique antérieurement à la plage de dates de création de rapports.

Les dimensions et mesures suivantes ne sont pas prises en charge avec le traitement de la période de rapport :

* **Analytics for Target**
* **Dimensions/mesures Analytics for Advertising Cloud**
* **eVars de compteur**
* [**Jours Avant Le Premier Achat**](/help/components/dimensions/days-before-first-purchase.md)
* [**Jours Depuis Le Dernier Achat**](/help/components/dimensions/days-since-last-purchase.md)
* [**Jours Depuis La Dernière Visite**](/help/components/dimensions/days-since-last-visit.md)
* **Page d’entrée originale**
* **eVars d’affectation linéaire**
* **Vars de liste**
* [**Dimensions Canaux marketing**](/help/components/dimensions/marketing-channel.md)
* [**Domaine référent d’origine**](/help/components/dimensions/original-referring-domain.md)
* [**Fréquence de retour**](/help/components/dimensions/return-frequency.md)
* [**Accès unique**](/help/components/metrics/single-access.md)
* **Sources de données des ID de transaction**
* [**Nombre de visites**](/help/components/dimensions/visit-number.md)

## Dimensions et mesures affectées

Vous trouverez ci-dessous une liste des dimensions et des mesures affectées en fonction des paramètres de traitement de la période de rapport sélectionnés :

* Si l’option « Empêcher les accès en arrière-plan de commencer une nouvelle visite » est activée, les modifications suivantes se produisent. Voir [Session contextuelle](vrs-mobile-visit-processing.md) pour plus d’informations.
   * [**Rebonds**](/help/components/metrics/bounces.md) / [**Taux de rebond :**](/help/components/metrics/bounce-rate.md) les accès en arrière-plan qui ne sont pas suivis d’un accès au premier plan ne sont pas considérés comme des rebonds et ne contribuent pas au taux de rebond.
   * [**Durée de la visite en secondes**](/help/components/metrics/time-spent-per-visit.md) : seules les visites qui incluent des accès de premier plan sont incluses dans cette mesure.
   * **Durée de la visite** : seules les visites qui incluent des accès de premier plan sont incluses dans cette mesure.
   * [**Mesure d’entrée**](/help/components/metrics/entries.md) / [**Mesure de sortie :**](/help/components/metrics/exits.md) seules les entrées et les sorties des visites avec des accès en premier plan apparaissent dans cette dimension.
   * [**Dimension d’entrée**](/help/components/dimensions/entry-dimensions.md) / [**Dimensions de sortie :**](/help/components/dimensions/exit-dimensions.md) seules les entrées et les sorties des visites avec des accès au premier plan apparaissent dans cette dimension.
   * [**Mesure Visiteurs uniques**](/help/components/metrics/unique-visitors.md) : les visiteurs uniques n’incluent pas les visiteurs qui n’ont eu que des accès en arrière-plan dans la plage de dates de création de rapports.
* [**Visites**](/help/components/metrics/visits.md) : les visites reflètent les paramètres configurés par la suite de rapports virtuelle, qui peuvent différer de ceux de la suite de rapports de base.
* **Événements sérialisés avec identifiant d’événement** : les événements qui utilisent la sérialisation des événements avec un identifiant d’événement ne sont dédupliqués que pour les événements qui se produisent dans la plage de dates de création de rapports pour un visiteur. Ces événements ne sont pas dédupliqués de manière globale entre toutes les dates ou tous les visiteurs en raison du fenêtrage de dates de l’option Traitement de la période de rapport.
* **Achats** / [**Chiffre d’affaires**](/help/components/metrics/revenue.md) / [**Commandes**](/help/components/metrics/orders.md) / [**Unités :**](/help/components/metrics/units.md) lorsque l’identifiant d’achat est utilisé, ces mesures ne sont dédupliquées que pour les identifiants d’achat en double qui se produisent au cours de la période de création des rapports pour un visiteur plutôt que pour toutes les dates ou tous les visiteurs dans le monde en raison du fenêtrage de la date de traitement de la période de rapport.
* [**eVars hors marchandisage**](/help/components/dimensions/evar.md) / **eVars réservées :** les valeurs définies en eVar ne persistent que si la valeur a été définie au cours de la période de création des rapports en raison du fenêtrage de la date de traitement de la période de création des rapports. En outre, les expirations basées sur le temps peuvent expirer une heure plus tôt ou une heure en retard si la persistance chevauche un passage à l’heure d’été/d’hiver.
* [**eVars de marchandisage**](/help/components/dimensions/evar-merchandising.md) / **eVars réservées :** voir ci-dessus. De plus, pour la syntaxe de la conversion pour laquelle la liaison est définie sur « any event », « any hit » est utilisé à la place.
* [**Type d’accès**](/help/components/dimensions/hit-type.md) : cette dimension indique si un accès est de premier plan ou en arrière-plan.
* **Dimensions avec (faible trafic) ou « Valeurs uniques dépassées » :** l’élément de ligne (faible trafic) est déterminé légèrement différemment lors de l’utilisation du traitement de la période de rapport et il n’est pas garanti qu’il corresponde à ce qui est observé lors de la création de rapports sur la suite de rapports de base. Il n’est pas garanti que les éléments de ligne de Dimension qui ne font pas partie du Faible trafic représentent 100 % des données de cet élément de ligne. Ces différences peuvent s’accentuer avec l’augmentation du nombre de valeurs uniques dans une dimension.
