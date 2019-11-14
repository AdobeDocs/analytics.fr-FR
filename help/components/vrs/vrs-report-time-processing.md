---
description: Le traitement du temps des rapports est un paramètre de suite de rapports virtuelle qui permet de traiter les données de manière rétroactive et non destructive.
title: Traitement de la période de rapport
uuid: 1a1d82ea-8c93-43cc-8689-cdcf59c309b1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Traitement de la période de rapport

Le traitement du temps des rapports est un paramètre de suite de rapports virtuelle qui permet de traiter les données de manière rétroactive et non destructive.

> [!NOTE] Le traitement du temps de rapport est disponible uniquement pour Analysis Workspace.

Le traitement de la période de rapport affecte uniquement les données de la suite de rapports virtuelle et n’a aucune incidence sur les données ou la collecte de données dans la suite de rapports de base (parente). La différence entre le traitement de la période de rapport et le traitement Analytics classique est plus facile à comprendre à l’aide du diagramme suivant :

![Google1](assets/google1.jpg)

Lors du traitement des données Analytics, les données circulent dans le pipeline de collecte de données et dans une étape de prétraitement qui prépare les données pour la création de rapports. Cette étape de prétraitement applique une logique d’expiration de visite et une logique de persistance des eVars (entre autres) aux données lors de leur collecte. Le principal inconvénient de ce modèle de prétraitement est qu’il nécessite une configuration préalable, avant la collecte des données. Cela signifie, qu’à partir de ce moment-là, les modifications apportées aux paramètres de prétraitement s’appliquent uniquement aux nouvelles données. Cela pose problème si les données n’arrivent pas dans l’ordre ou si les paramètres ont été mal configurés.

Le traitement de la période de rapport est une manière fondamentalement différente de traiter les données Analytics pour la création de rapports. Au lieu de prédéterminer la logique de traitement avant la collecte des données, Analytics ignore le jeu de données pendant l’étape de prétraitement et applique cette logique chaque fois qu’un rapport est exécuté :

![Google2](assets/google2.jpg)

Cette architecture de traitement offre des options de création de rapports beaucoup plus flexibles. Par exemple, vous pouvez modifier le délai de visite de manière non destructive et ces modifications sont répercutées rétroactivement dans la persistance des eVars et les conteneurs de segments, comme si vous aviez appliqué ces paramètres avant la collecte des données. En outre, vous pouvez créer un nombre illimité de suites de rapports virtuelles, chacune avec des options de traitement de la période de rapport différentes, basées sur la même suite de rapports de base (parente), sans modifier les données de cette dernière.

Le traitement de la période de rapport permet également à Analytics d’empêcher les accès en arrière-plan de démarrer de nouvelles visites et permet au [SDK Mobile](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) d’indiquer à la création de rapports de démarrer une nouvelle visite chaque fois qu’un événement de lancement d’application est déclenché.

Les options de configuration suivantes sont actuellement disponibles pour les suites de rapports virtuelles pour lesquelles le traitement de la période de rapport est activé :

* **** Délai d’expiration de la visite : Le paramètre du délai d’expiration de la visite définit le niveau d’inactivité que doit subir un visiteur unique avant le démarrage automatique d’une nouvelle visite. Par défaut, cela prend 30 minutes. Par exemple, si vous définissez le délai de visite sur 15 minutes, un nouveau groupe de visites est créé pour chaque séquence d’accès collectés, séparé par 15 minutes d’inactivité. Ce paramètre impacte non seulement le nombre de visites, mais également la manière dont les conteneurs de segments de visite sont évalués, ainsi que la logique d’expiration de la visite pour les eVars expirant lors de la visite. La réduction du délai de visite augmentera probablement le nombre total de visites dans les rapports, tandis que l’augmentation du délai de visite réduira probablement le nombre total de visites dans les rapports.
* **** Paramètres de visite des applications mobiles : Pour les suites de rapports contenant les données générées par les applications mobiles via les SDK [mobiles](https://www.adobe.io/apis/cloudplatform/mobile.html)Adobe, des paramètres de visite supplémentaires sont disponibles. Ces paramètres sont non destructifs et affectent uniquement les accès collectés via les SDK Mobile. Ces paramètres n’ont aucun impact sur les données collectées en dehors du SDK Mobile.
* **** Empêcher les accès en arrière-plan de lancer une nouvelle visite : Les accès en arrière-plan sont collectés par les kits SDK mobiles lorsque l’application est en arrière-plan.
* **** Démarrer une nouvelle visite à chaque lancement d’application : Outre le délai d’expiration de la visite, vous pouvez forcer une visite à commencer chaque fois qu’un événement de lancement d’application a été enregistré à partir des SDK mobiles, quelle que soit la fenêtre d’inactivité. Ce paramètre affecte la mesure des visites et le conteneur de segments de visite, ainsi que la logique d’expiration de visite des eVars.
* **** Commencer une nouvelle visite avec un événement : Une nouvelle session commence lorsqu’un événement est déclenché, qu’une session ait expiré ou non. La session nouvellement créée inclut l’événement à l’origine de son démarrage. De plus, vous pouvez utiliser plusieurs événements pour démarrer une session. Une nouvelle session se déclenche alors si l’un de ces événements est observé dans les données. Ce paramètre aura un impact sur le nombre de visites, sur le conteneur de segmentation des visites et sur la logique d’expiration de visite des eVars.

Le traitement de la période de rapport ne prend pas en charge toutes les mesures et dimensions disponibles dans la création de rapports Analytics traditionnelle. Virtual report suites utilizing Report Time Processing are only accessible in Analysis Workspace and will not be accessible in [!UICONTROL Reports &amp; Analytics], Ad Hoc Analysis, Data Warehouse, Report Builder, Data Feeds, or the reporting API.

En outre, le traitement de la période de rapport traite uniquement les données comprises dans la plage de dates de création de rapports (appelée « fenêtrage de dates » ci-dessous). Cela signifie que les valeurs eVar définies sur « ne jamais expirer » pour un visiteur antérieurement à la plage de dates de création de rapports ne sont pas conservées dans les fenêtres de création de rapports et n’apparaissent pas dans les rapports. Cela signifie également que les mesures de fidélisation des clients sont basées exclusivement sur les données présentes dans la plage de dates de création de rapports et non sur l’ensemble de l’historique antérieurement à la plage de dates de création de rapports.

Vous trouverez ci-dessous une liste de mesures et de dimensions qui ne sont actuellement pas prises en charge lors de l’utilisation du traitement de la période de rapport :

* **** Analytics pour Target : Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **** Mesures/dimensions réservées d’Analytics pour Advertising Cloud : Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **** Mesure Accès unique : Sans prise en charge permanente.
* **** Variables de liste : Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **** eVars de compteur : Sans prise en charge permanente.
* **** Variables des canaux marketing : Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **** Jours depuis la dernière dimension d’achat : En raison de la nature de la fenêtre de la date de traitement de l’heure des rapports, cette dimension n’est pas prise en charge.
* **** Jours avant la première dimension d’achat : En raison de la nature de la fenêtre de la date de traitement de l’heure des rapports, cette dimension n’est pas prise en charge.
* **** Dimension Fréquence des retours : En raison de la nature de la fenêtre de la date de traitement de l’heure des rapports, cette dimension n’est pas prise en charge. Une autre approche utilisant une mesure du nombre de visites dans un segment est possible, ou en utilisant la mesure des visites dans un rapport sous forme d’histogramme.
* **** Jours depuis la dimension Dernière visite : En raison de la nature de la fenêtre de la date de traitement de l’heure des rapports, cette dimension n’est pas prise en charge.
* **** Dimension d’origine de la page d’entrée : En raison de la nature de la fenêtre de la date de traitement de l’heure des rapports, cette dimension n’est pas prise en charge.
* **** eVars d’allocation linéaire : Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **** Dimension de domaine référent d’origine : Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.
* **** Nombre de visites : En raison de la nature de la fenêtre de la date de traitement de l’heure des rapports, cette mesure n’est pas prise en charge. Autre possibilité dans les applications mobiles, vous pouvez utiliser une mesure calculée incluant les visiteurs/visites avec la mesure d’installation de l’application pour identifier les nouveaux visiteurs ou les visites.
* **** Sources de données d’ID de transaction : Actuellement non pris en charge. Une prise en charge est prévue à l’avenir.

Vous trouverez ci-dessous une liste des dimensions et des mesures affectées en fonction des paramètres de traitement de la période de rapport sélectionnés :

* Si l’option "Empêcher les accès en arrière-plan de lancer une nouvelle visite" est activée, les modifications suivantes se produisent. Voir Session [contextuelle](vrs-mobile-visit-processing.md) pour plus d’informations.
   * **** Taux de rebonds/rebonds : Les accès en arrière-plan qui ne sont pas suivis d’un accès en premier plan ne sont pas considérés comme un rebond et ne contribuent pas au taux de rebond.
   * **** Durée de la visite : Seules les visites qui incluent des accès de premier plan contribuent à cette mesure.
   * **** Durée de la visite : Seules les visites qui incluent des accès de premier plan contribuent à cette mesure.
   * **** Dimensions et mesures d’entrée/sortie : Seules les entrées et les sorties des visites avec accès au premier plan apparaissent dans cette dimension.
   * **** Mesure Visiteurs uniques : Les visiteurs uniques n’incluent pas les visiteurs qui n’ont eu que des accès en arrière-plan dans la période du rapport.
* **** Visites : Les visites reflètent les paramètres configurés par la suite de rapports virtuelle, qui peuvent être différents de la suite de rapports de base.
* **** Evénements sérialisés avec ID d’événement : Les événements qui utilisent la sérialisation d’événements avec un ID d’événement ne sont dédupliqués que pour les événements qui se produisent dans la plage de dates des rapports pour un visiteur. Ces événements ne sont pas dédupliqués entre toutes les dates ou tous les visiteurs dans le monde en raison de la fenêtre de la date de traitement de l’heure du rapport.
* **** Achats/Recettes/Commandes/Unités : Lorsque l’ID d’achat est utilisé, ces mesures ne sont dédupliquées que pour les ID d’achat en double qui surviennent au cours de la période du rapport pour un visiteur plutôt que pour toutes les dates ou tous les visiteurs dans le monde en raison de la fenêtre de la date de traitement de l’heure du rapport.
* **** eVars de non-marchandisage/eVars réservées : Les valeurs définies dans une eVar ne sont conservées que si elles ont été définies dans la plage de dates du rapport en raison de la fenêtre de la date de traitement de l’heure du rapport. En outre, les expirations temporelles peuvent expirer une heure plus tôt ou une heure plus tard si la persistance s’étend sur une modification de l’heure d’été.
* **** eVars de marchandisage/eVars réservées : Voir ci-dessus. De plus, pour la syntaxe de la conversion pour laquelle la liaison est définie sur « any event », « any hit » est utilisé à la place.
* **** Type d’accès : Cette dimension indique si un accès est au premier plan ou en arrière-plan.
