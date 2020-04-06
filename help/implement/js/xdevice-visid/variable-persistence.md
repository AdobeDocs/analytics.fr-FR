---
description: Lorsque des profils du visiteur sont fusionnés après avoir été associés à la même variable d’identifiant visiteur, l’attribution n’est pas modifiée dans l’ensemble de données historiques.
keywords: Analytics Implementation
title: Attribution et persistance
topic: Developer and implementation
uuid: 5dd706be-83f6-498a-a856-e3c5af995348
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Attribution et persistance

>[!IMPORTANT] Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la section [Analytics sur l’ensemble des appareils](/help/components/cda/cda-home.md) dans le guide d’utilisation Composants.

Lorsque des profils du visiteur sont fusionnés après avoir été associés à la même variable d’identifiant visiteur, l’attribution n’est pas modifiée dans l’ensemble de données historiques.

* Lorsque la variable `s.visitorID` est définie et envoyée sur un accès, Adobe recherche les autres profils du visiteur ayant un identifiant visiteur correspondant.
* S’il existe un , le  de qui se trouve déjà dans le système est utilisé à partir de ce moment et le précédent de l’n’est plus utilisé.
* Si aucun ID de correspondant n’est trouvé, un nouveau  de est créé.

Lorsqu’un client non authentifié arrive pour la première fois sur votre site, Adobe Analytics lui affecte un de . Lorsque le nouveau profil est créé, une visite se termine et une autre visite commence.

## Exemple 1

L’exemple ci-dessous explique comment les données sont envoyées à Adobe Analytics lorsqu’un client s’authentifie pour la première fois, sur le premier appareil :

* `eVar16` expire au bout d’1 jour et `evar17` expire à la fin de la visite.
* La colonne `post_visitor_id` représente le profil stocké par Adobe Analytics. Les colonnes de publication sont généralement affichées dans les flux de données. Voir [Flux de données](/help/export/analytics-data-feed/data-feed-overview.md) dans le guide d’utilisation Exportation.
* Les colonnes `post_evar16` et `post_evar17` affichent la persistance des eVars.
* `cust_visid` représente un jeu de valeurs dans `s.visitorID`.
* Chaque ligne correspond à un « accès », une seule demande envoyée aux serveurs de collecte de données d’Adobe Analytics.

![Exemple 1 sur plusieurs appareils](assets/xdevice_first.jpg)

Lors de la première connexion de données contenant une valeur `s.visitorID` précédemment non reconnue (`u999` ci-dessus), un nouveau profil est créé. Les valeurs persistantes du  précédent sont transférées vers le nouvel  de.

* Les eVars définies pour expirer lors de la visite ne sont pas copiées dans le  authentifié. Notez que la valeur `car` ci-dessus n’est pas conservée.
* Les eVars définies pour expirer selon d’autres mesures sont copiées vers le profil authentifié. Notez que la valeur `apple` n’est pas conservée.
* Pour les eVars persistantes, aucune mesure d’instance n’est enregistrée. Cela signifie que lors de l’utilisation de l’identification des visiteurs sur plusieurs appareils, il est possible d’afficher des rapports pour lesquels la mesure Visites uniques d’une valeur eVar est supérieure à la mesure d’instance.

>[!NOTE] Si un utilisateur est nouveau sur votre site (n’a jamais effectué de visites auparavant avec cet appareil) ET qu’il s’authentifie dans les 3 minutes (environ) suivant son arrivée, aucune valeur ne sera conservée dans le profil authentifié.

## Exemple 2

L’exemple ci-dessous explique comment les données sont envoyées à Adobe Analytics lorsqu’un client s’authentifie sur un nouvel appareil, après s’être authentifié antérieurement sur un appareil différent.

![Exemple 2 sur plusieurs appareils](assets/xdevice-subsequent.jpg)

Lorsque le client s’authentifie, il est mis en correspondance avec le profil « authentifié » précédent - `2947539300`. Le profil utilisé au début de cette visite (`5477766334477`) n’est plus utilisé et aucune donnée du fichier n’est conservée.

* Les données de géosegmentation sont enregistrées selon le premier accès de la visite. Elles ne changent pas pour une même visite, quel que soit l’appareil utilisé. Cela signifie que, lors d’une connexion de données suivante sur un nouvel appareil, la géosegmentation n’est généralement pas incluse.
* Les colonnes de technologie telles que le navigateur, le système d’exploitation et la profondeur de couleur sont enregistrées lors du premier accès d’une visite. Comme les valeurs de géosegmentation, elles ne sont pas copiées sur le profil associé.
* Les canaux marketing remplacent d’autres canaux lors d’une connexion de données ultérieure contenant une première authentification pour cet appareil.
