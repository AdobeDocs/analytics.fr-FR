---
description: Les variables Analytics sont utilisées pour capturer des informations d’achat spécifiques pour l’événement d’achat. La variable s.purchaseID sert à sérialiser (dédupliquer) l’événement.
keywords: Analytics Implementation
title: Événements d’achat
topic: Developer and implementation
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Événements d’achat

Les variables Analytics sont utilisées pour capturer des informations d’achat spécifiques pour l’événement d’achat. La variable `s.purchaseID` sert à sérialiser (dédupliquer) l’événement.

Si un accès avec un événement d’achat est transmis sans ID d’achat, Adobe Analytics utilise les informations de l’accès (s.purchase et s.events) pour créer un "ID d’achat temporaire". Cet ID d’achat temporaire s’applique uniquement au visiteur de l’accès. Les 5 identifiants d’achat temporaires précédents sont stockés pour chaque identifiant visiteur (par suite de rapports).

Lorsqu’un visiteur procède à un achat, plusieurs vérifications sont réalisées :

* La variable l’ID d’achat temporaire correspond-il à l’un des cinq derniers ID d’achat temporaire stockés ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports.
* Si `s.purchaseID` est défini, correspond-il à une valeur déjà collectée dans la suite de rapports ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports.

Du code côté serveur spécifique peut être utilisé pour générer le numéro unique (valeur alphanumérique) incorporé dans la source HTML. En règle générale, l’identifiant de commande, ou une valeur alphanumérique similaire, est utilisé à cette fin. Cette valeur ne doit pas être modifiée lorsque l’utilisateur actualise la page.

## du lien personnalisé

```js
s.purchaseID="12345678";
```

## Exemples

```js
s.products="Footwear;Hiking Boots;1;170.00";
s.purchaseID="12345678";
s.events="purchase";
```

## Remarques supplémentaires

* N’utilisez pas de fonction de randomisation JavaScript pour générer un nombre, qui génère des nombres uniques chaque fois que la page est chargée. Adobe recommande d’utiliser une couche de données pour stocker un ID d’achat donné.
* Les identifiants uniques sont applicables à tous les utilisateurs pour toutes les sessions. Assurez-vous que tous les identifiants d’achat sont vraiment uniques.
* Les valeurs valides sont des valeurs alphanumériques d’une longueur maximale de 20 caractères.
* La variable `s.purchaseID``s.events` sérialise tous les événements transmis dans la variable   et remplace toute valeur de sérialisation pour les événements. N’utilisez pas la sérialisation [!UICONTROL d’] événements pour les événements si la `s.purchaseID` variable est utilisée sur la page active.
* If the `s.purchaseID` variable is left blank, each instance of the purchase event, even page reloads, is counted.
