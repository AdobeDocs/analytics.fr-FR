---
description: Le traitement du temps de rapport est un paramètre de suite de rapports virtuelle qui permet le traitement des données d'une manière non destructive et rétroactive.
seo-description: Le traitement du temps de rapport est un paramètre de suite de rapports virtuelle qui permet le traitement des données d'une manière non destructive et rétroactive.
seo-title: Traitement de la période de rapport
title: Traitement de la période de rapport
uuid: 1 a 1 d 82 ea -8 c 93-43 cc -8689-cdcf 59 c 309 b 1
translation-type: tm+mt
source-git-commit: 658aba8a456f5760d4871fdc941150d64e9e2e94

---


# Traitement de la période de rapport

Le traitement du temps de rapport est un paramètre de suite de rapports virtuelle qui permet le traitement des données d'une manière non destructive et rétroactive.

> [!NOTE] Le Traitement du temps de rapport est disponible uniquement pour Analysis Workspace.

Le traitement de la période de rapport affecte uniquement les données de la suite de rapports virtuelle et n’a aucune incidence sur les données ou la collecte de données dans la suite de rapports de base (parente). La différence entre le traitement de la période de rapport et le traitement Analytics classique est plus facile à comprendre à l’aide du diagramme suivant :

![Google1](assets/google1.jpg)

Lors du traitement des données Analytics, les données circulent dans le pipeline de collecte de données et dans une étape de prétraitement qui prépare les données pour la création de rapports. Cette étape de prétraitement applique une logique d’expiration de visite et une logique de persistance des eVars (entre autres) aux données lors de leur collecte. Le principal inconvénient de ce modèle de prétraitement est qu’il nécessite une configuration préalable, avant la collecte des données. Cela signifie, qu’à partir de ce moment-là, les modifications apportées aux paramètres de prétraitement s’appliquent uniquement aux nouvelles données. Cela pose problème si les données n’arrivent pas dans l’ordre ou si les paramètres ont été mal configurés.

Le traitement de la période de rapport est une manière fondamentalement différente de traiter les données Analytics pour la création de rapports. Au lieu de prédéterminer la logique de traitement avant la collecte des données, Analytics ignore le jeu de données pendant l’étape de prétraitement et applique cette logique chaque fois qu’un rapport est exécuté :

![Google2](assets/google2.jpg)

Cette architecture de traitement offre des options de création de rapports beaucoup plus flexibles. Par exemple, vous pouvez modifier le délai de visite de manière non destructive et ces modifications sont répercutées rétroactivement dans la persistance des eVars et les conteneurs de segments, comme si vous aviez appliqué ces paramètres avant la collecte des données. En outre, vous pouvez créer un nombre illimité de suites de rapports virtuelles, chacune avec des options de traitement de la période de rapport différentes, basées sur la même suite de rapports de base (parente), sans modifier les données de cette dernière.

Le traitement de la période de rapport permet également à Analytics d’empêcher les accès en arrière-plan de démarrer de nouvelles visites et permet au [SDK Mobile](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) d’indiquer à la création de rapports de démarrer une nouvelle visite chaque fois qu’un événement de lancement d’application est déclenché.

Les options de configuration suivantes sont actuellement disponibles pour les suites de rapports virtuelles pour lesquelles le traitement de la période de rapport est activé :

* **Délai d'expiration de la visite :** Le délai d'expiration de la visite définit le volume d'inactivité qu'un visiteur unique doit avoir avant qu'une nouvelle visite ne soit automatiquement lancée. Par défaut, cela prend 30 minutes. Par exemple, si vous définissez le délai de visite sur 15 minutes, un nouveau groupe de visites est créé pour chaque séquence d’accès collectés, séparé par 15 minutes d’inactivité. Ce paramètre impacte non seulement le nombre de visites, mais également la manière dont les conteneurs de segments de visite sont évalués, ainsi que la logique d’expiration de la visite pour les eVars expirant lors de la visite. La réduction du délai de visite augmentera probablement le nombre total de visites dans les rapports, tandis que l’augmentation du délai de visite réduira probablement le nombre total de visites dans les rapports.
* **Paramètres de visite des applications mobiles :** Pour les suites de rapports contenant des données générées par des applications mobiles via les [SDK](https://www.adobe.io/apis/cloudplatform/mobile.html)Adobe Mobile, des paramètres de visite supplémentaires sont disponibles. Ces paramètres sont non destructifs et affectent uniquement les accès collectés via les SDK Mobile. Ces paramètres n’ont aucun impact sur les données collectées en dehors du SDK Mobile.
* **Empêcher les accès en arrière-plan de démarrer une nouvelle visite :** Les accès en arrière-plan sont collectés par les SDK mobiles lorsque l'application est en état d'arrière-plan.
* **Démarrer une nouvelle visite à chaque lancement d'application :** Outre le délai d'expiration de la visite, vous pouvez forcer une visite à commencer chaque fois qu'un événement de lancement d'application a été enregistré à partir des SDK mobiles, quelle que soit la fenêtre d'inactivité. Ce paramètre affecte la mesure des visites et le conteneur de segments de visite, ainsi que la logique d’expiration de visite des eVars.
* **Démarrer la nouvelle visite avec Événement :** Une nouvelle session commence lorsqu'un événement est déclenché, qu'une session ait expiré ou non. La session nouvellement créée inclut l’événement à l’origine de son démarrage. De plus, vous pouvez utiliser plusieurs événements pour démarrer une session. Une nouvelle session se déclenche alors si l’un de ces événements est observé dans les données. Ce paramètre aura un impact sur le nombre de visites, sur le conteneur de segmentation des visites et sur la logique d’expiration de visite des eVars.

Le traitement de la période de rapport ne prend pas en charge toutes les mesures et dimensions disponibles dans la création de rapports Analytics traditionnelle. Virtual report suites utilizing Report Time Processing are only accessible in Analysis Workspace and will not be accessible in [!UICONTROL Reports &amp; Analytics], Ad Hoc Analysis, Data Warehouse, Report Builder, Data Feeds, or the reporting API.

En outre, le traitement de la période de rapport traite uniquement les données comprises dans la plage de dates de création de rapports (appelée « fenêtrage de dates » ci-dessous). Cela signifie que les valeurs eVar définies sur « ne jamais expirer » pour un visiteur antérieurement à la plage de dates de création de rapports ne sont pas conservées dans les fenêtres de création de rapports et n’apparaissent pas dans les rapports. Cela signifie également que les mesures de fidélisation des clients sont basées exclusivement sur les données présentes dans la plage de dates de création de rapports et non sur l’ensemble de l’historique antérieurement à la plage de dates de création de rapports.

Vous trouverez ci-dessous une liste de mesures et de dimensions qui ne sont actuellement pas prises en charge lors de l’utilisation du traitement de la période de rapport :

* **Analytics pour Target :** Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **Analytics pour les mesures/dimensions réservées à la publicité Cloud :** Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **Mesure d'accès unique :** Définitivement non pris en charge.
* **List Vars :** Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **Evars de compteur :** Définitivement non pris en charge.
* **Variables Canaux marketing :** Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **Jours depuis la dernière dimension d'achat :** En raison de la nature du rapport de date Traitement du temps passé, cette dimension n'est pas prise en charge.
* **Jours avant la première dimension d'achat :** En raison de la nature du rapport de date Traitement du temps passé, cette dimension n'est pas prise en charge.
* **Dimension de fréquence des retours :** En raison de la nature du rapport de date Traitement du temps passé, cette dimension n'est pas prise en charge. Une autre approche utilisant une mesure du nombre de visites dans un segment est possible, ou en utilisant la mesure des visites dans un rapport sous forme d’histogramme.
* **Jours depuis la dernière dimension :** En raison de la nature du rapport de date Traitement du temps passé, cette dimension n'est pas prise en charge.
* **Dimension d'origine de la page d'entrée :** En raison de la nature du rapport de date Traitement du temps passé, cette dimension n'est pas prise en charge.
* **Evars d'attribution linéaire :** Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **Dimension de domaine référent initial :** Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **Nombre de visites :** En raison de la nature du rapport de date Traitement du temps passé, cette mesure n'est pas prise en charge. À titre d'alternative dans les applications mobiles, vous pouvez utiliser une mesure calculée incluant les visiteurs/visites avec la mesure Installation d'application pour identifier les nouveaux visiteurs ou les visites.
* **Sources de données d'ID de transaction :** Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.

Vous trouverez ci-dessous une liste des dimensions et des mesures affectées en fonction des paramètres de traitement de la période de rapport sélectionnés :

* Les modifications suivantes se produisent si « Empêcher les accès en arrière-plan du démarrage d'une nouvelle visite » est activé. Pour [plus d'informations, reportez-vous à la section Sessionation](vrs-mobile-visit-processing.md) basée sur le contexte.
   * **Rebonds/Taux de rebonds :** Les accès en arrière-plan qui ne sont pas suivis d'un accès au premier plan ne sont pas considérés comme un retour et ne contribuent pas au taux de rebond.
   * **Durée de durée de la visite par visite :** Seules les visites incluant des accès au premier plan contribuent à cette mesure.
   * **Durée de la visite :** Seules les visites incluant des accès au premier plan contribuent à cette mesure.
   * **Dimensions et mesures d'entrée et de sortie :** Seules les entrées et sorties issues des visites avec accès au premier plan apparaissent dans cette dimension.
   * **Mesure Visiteurs uniques :** Les visiteurs uniques n'incluent pas les visiteurs qui n'avaient que des accès en arrière-plan dans la plage de dates des rapports.
* **Visites :** Les visites reflètent les paramètres configurés par la suite de rapports virtuelle, qui peuvent différer de ceux de la suite de rapports de base.
* **Événements sérialisés avec les ID d'événement :** Les événements qui utilisent la sérialisation d'événements avec un ID d'événement ne sont dédupliqués que pour les événements qui se produisent dans la plage de dates des rapports pour un visiteur. Ces événements ne sont pas dédupliqués globalement sur toutes les dates ou tous les visiteurs en raison de la date de traitement du temps passé sur le rapport.
* **Achats/Recettes/Commandes/Unités :** Lorsque l'ID d'achat est utilisé, ces mesures ne sont dédupliquées que pour les ID d'achat en double qui se produisent dans la plage de dates des rapports pour un visiteur plutôt que pour l'ensemble des dates ou visiteurs en raison de la date de traitement du temps passé sur le rapport.
* **Evars non marchandisage/evars réservées :** Les valeurs définies dans une evar persistent uniquement si la valeur a été définie dans la plage de dates des rapports en raison de la date de traitement du temps de traitement du rapport. En outre, les expirations temporelles peuvent expirer une heure tôt ou une heure en retard si la persistance s'étend sur une modification de l'heure d'été.
* **Evars de marchandisage/evars réservées :** Voir ci-dessus. De plus, pour la syntaxe de la conversion pour laquelle la liaison est définie sur « any event », « any hit » est utilisé à la place.
* **Type d'accès :** Cette dimension indique si un accès est un premier plan ou un arrière-plan.
