---
description: Le traitement de la période de rapport est un paramètre des suites de rapports virtuelles qui permet aux données d’être traitées de façon rétroactive et non destructrice.
title: Traitement de la période de rapport
uuid: 1a1d82ea-8c93-43cc-8689-cdcf59c309b1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Traitement de la période de rapport

Le traitement de la période de rapport est un paramètre des suites de rapports virtuelles qui permet aux données d’être traitées de façon rétroactive et non destructrice.

>[!NOTE] Le traitement de la période de rapport n’est disponible que dans Analysis Workspace.

Le traitement du temps des rapports affecte uniquement les données de la suite de rapports virtuelle et n’affecte aucune donnée ni collecte de données dans la suite de rapports de base. La différence entre le traitement du temps des rapports et le traitement Analytics traditionnel est mieux comprise à l’aide du diagramme suivant :

![Google1](assets/google1.jpg)

Pendant le traitement des données Analytics, les données passent par le pipeline de collecte des données et passent à une étape de prétraitement, qui prépare les données pour les  de. Cette étape de prétraitement applique la logique d’expiration de visite et la logique de persistance d’eVar (entre autres) aux données collectées. Le principal inconvénient de ce modèle de prétraitement est qu’il nécessite que toute configuration soit effectuée à l’avance avant la collecte des données. Cela signifie que toute modification des paramètres de prétraitement s’applique uniquement aux nouvelles données à partir de ce moment. Cela est problématique si les données sont incohérentes ou si les paramètres ont été mal configurés.

Le traitement du temps de rapport est une méthode fondamentalement différente de traitement des données Analytics pour les  de. Au lieu de prédéterminer la logique de traitement avant la collecte des données, Analytics ignore le jeu de données pendant l’étape de prétraitement et applique cette logique chaque fois qu’un rapport est exécuté :

![Google2](assets/google2.jpg)

Cette architecture de traitement permet des options de beaucoup plus flexibles. Vous pouvez, par exemple, modifier le délai d’expiration de la visite sur la durée souhaitée de manière non destructive et ces modifications sont répercutées dans votre persistance d’eVar et votre de segments de manière rétroactive comme si vous aviez appliqué ces paramètres avant la collecte des données. De plus, vous pouvez créer un nombre illimité de suites de rapports virtuelles, chacune avec des options de traitement du temps des rapports différentes basées sur la même suite de rapports de base, sans modifier aucune des données de la suite de rapports de base.

Le traitement du temps des rapports permet également à Analytics d’empêcher les accès en arrière-plan de déclencher de nouvelles visites et permet au SDK [](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) mobile d’indiquer au de de une nouvelle visite chaque fois qu’unlancement d’application est déclenché.

Les options de configuration suivantes sont actuellement disponibles pour les suites de rapports virtuelles pour lesquelles le traitement de l’heure des rapports est activé :

* **Délai de visite** : le paramètre Délai de visite définit le délai d’inactivité d’un visiteur unique avant qu’une nouvelle visite ne soit lancée automatiquement. Il est défini par défaut sur 30 minutes. Par exemple, si vous définissez le délai d’expiration de la visite sur 15 minutes, un nouveau regroupement de visites est créé pour chaque séquence d’accès collectée, séparé par 15 minutes d’inactivité. Ce paramètre a un impact non seulement sur le nombre de visites, mais également sur la manière dont les de segments de visites sont évalués et sur la logique d’expiration des visites pour les eVars qui expirent au cours d’une visite. La réduction du délai d’expiration des visites augmentera probablement le nombre total de visites dans votre , tandis que l’augmentation du délai d’expiration des visites diminuera probablement le nombre total de visites dans votre  de.
* **Paramètres de visite pour les applications mobiles** : pour les suites de rapports contenant des données générées par des applications mobiles via les [SDK Adobe Mobile](https://www.adobe.io/apis/cloudplatform/mobile.html), des paramètres de visite supplémentaires sont disponibles. Ces paramètres sont non destructifs et n’affectent que les accès collectés via les kits SDK mobiles. Ces paramètres n’ont aucune incidence sur les données collectées en dehors du kit SDK Mobile.
* **Empêcher les accès en arrière-plan de commencer une nouvelle visite** : les accès en arrière-plan sont collectés par les SDK mobiles lorsque l’application est en arrière-plan.
* **Démarrer de nouvelles visites à chaque lancement d’une application** : en plus du délai de visite, vous pouvez forcer une visite à démarrer chaque fois qu’un événement de lancement d’application est enregistré depuis les SDK Mobile, quelle que soit la fenêtre d’inactivité. Ce paramètre affecte la mesure des visites et le conteneur de segments de visite, ainsi que la logique d’expiration de visite des eVars.
* **Démarrer une nouvelle visite avec un événement** : une nouvelle session démarre lorsqu’un événement est déclenché, qu’une session ait expiré ou non. La nouvelle session comprend le  qui l’a démarré. De plus, vous pouvez utiliser plusieurs  pour  une session et une nouvelle session se déclenche si l’un de cestermes est observé dans les données. Ce paramètre aura un impact sur le nombre de visites, le de segmentation des visites et la logique d’expiration des visites sur les eVars.

Le traitement de la période de rapport ne prend pas en charge toutes les mesures et dimensions disponibles dans la création de rapports Analytics traditionnelle. Les suites de rapports virtuelles utilisant le traitement de la période de rapport sont accessibles uniquement dans Analysis Workspace et ne sont pas accessibles dans les [!UICONTROL Reports & Analytics], les Ad Hoc Analysis, Data Warehouse, le Report Builder, les flux de données ou l’API de création de rapports.

En outre, le traitement de l’heure des rapports traite uniquement les données issues de la période de  du (appelée &quot;fenêtre de date&quot; ci-dessous). Cela signifie que les valeurs d’eVar définies sur &quot;n’expirent jamais&quot; pour un avant la période  du ne persistent pas dans les fenêtres  et n’apparaissent pas dans les rapports. Cela signifie également que les mesures de fidélité des clients sont basées exclusivement sur les données présentes dans la plage de dates  du et non sur l’historique complet avant la plage de dates  du.

Vous trouverez ci-dessous un de mesures et de dimensions qui ne sont actuellement pas prises en charge lors de l’utilisation du traitement de l’heure des rapports :

* **Analytics pour Target** : actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **Mesures/dimensions réservées d’Analytics pour Advertising Cloud :** actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **Mesure Accès unique** : sans prise en charge permanente.
* **Variables de liste** : actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **eVars de compteur :** sans prise en charge permanente.
* **Variables Canaux marketing** : actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **Jours depuis la dernière dimension d’achat** : en raison de la nature du fenêtrage de dates de traitement de l’heure des rapports, cette dimension n’est pas prise en charge.
* **Jours avant la première dimension d’achat** : en raison de la nature du fenêtrage de dates de traitement de l’heure des rapports, cette dimension n’est pas prise en charge.
* **Dimension Fréquence des retours** : en raison de la nature du fenêtrage de dates de l’option Traitement de la période de rapport, cette dimension n’est pas prise en charge. Une autre approche utilisant une mesure du nombre de visites dans un segment est possible, ou en utilisant la mesure des visites dans un rapport sous forme d’histogramme.
* **Jours depuis la dimension Dernière visite** : en raison de la nature du fenêtrage de dates de traitement de l’heure des rapports, cette dimension n’est pas prise en charge.
* **Dimension Page d’accès d’origine** : en raison de la nature du fenêtrage de dates de l’option Traitement de la période de rapport, cette dimension n’est pas prise en charge.
* **eVars d’affectation linéaire** : actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **Dimension Domaine référent initial** : actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **Nombre de visites** : en raison de la nature du fenêtrage de dates de l’option Traitement de la période de rapport, cette mesure n’est pas prise en charge. Autre possibilité dans les applications mobiles, vous pouvez utiliser une mesure calculée incluant les visiteurs/visites avec la mesure Installation de l’application pour identifier les nouveaux visiteurs ou les nouvelles visites.
* **Sources de données d’ID de transaction** : actuellement non pris en charge. Une prise en charge est prévue à l’avenir.

Vous trouverez ci-dessous un  de dimensions et de mesures qui sont affectées selon les paramètres de traitement de l’heure du rapport sélectionnés :

* Si l’option « Empêcher les accès en arrière-plan de commencer une nouvelle visite » est activée, les modifications suivantes se produisent. Voir [Session contextuelle](vrs-mobile-visit-processing.md) pour plus d’informations.
   * **Rebonds/Taux de rebond** : les accès en arrière-plan qui ne sont pas suivis d’un accès de premier plan ne sont pas considérés comme un rebond et ne font pas partie du taux de rebond.
   * **Durée de la visite en secondes** : seules les visites qui incluent des accès de premier plan sont incluses dans cette mesure.
   * **Durée de la visite** : seules les visites qui incluent des accès de premier plan sont incluses dans cette mesure.
   * **Dimensions et mesures d’entrée/sortie** : seules les entrées et les sorties des visites avec accès de premier plan apparaissent dans cette dimension.
   * **Mesure Visiteurs uniques** : les visiteurs uniques n’incluent pas les visiteurs qui n’ont eu que des accès en arrière-plan dans la plage de dates de création de rapports.
* **Visites** : les visites reflètent les paramètres configurés par la suite de rapports virtuelle, qui peuvent différer de ceux de la suite de rapports de base.
* **Événements sérialisés avec identifiant d’événement** : les événements qui utilisent la sérialisation des événements avec un identifiant d’événement ne sont dédupliqués que pour les événements qui se produisent dans la plage de dates de création de rapports pour un visiteur. Ces événements ne sont pas dédupliqués de manière globale entre toutes les dates ou tous les visiteurs en raison du fenêtrage de dates de l’option Traitement de la période de rapport.
* **Achats/Recettes/Commandes/Unités** : lorsque l’identifiant d’achat est utilisé, ces mesures ne sont dédupliquées que pour les identifiants d’achat en double se produisant dans la plage de dates de création de rapports pour un visiteur plutôt que pour l’ensemble des dates ou visiteurs en raison du fenêtrage de dates de l’option Traitement de la période de rapport.
* **eVars de non-marchandisage/eVars réservés** : les valeurs définies dans une eVar ne sont conservées que si la valeur a été définie dans la plage de dates de création de rapports en raison du fenêtrage de dates de l’option Traitement de la période de rapport. En outre, les expirations basées sur le temps peuvent expirer une heure plus tôt ou une heure en retard si la persistance chevauche un passage à l’heure d’été/d’hiver.
* **eVars de marchandisage/eVars réservées :** voir ci-dessus. De plus, pour la syntaxe de la conversion pour laquelle la liaison est définie sur « any event », « any hit » est utilisé à la place.
* **Type d’accès** : cette dimension indique si un accès est de premier plan ou en arrière-plan.
