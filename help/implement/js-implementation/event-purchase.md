---
description: Les variables Analytics sont utilisées pour capturer des informations d’achat spécifiques pour l’événement d’achat. La variable s.purchaseID sert à sérialiser (dédupliquer) l’événement.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables Analytics sont utilisées pour capturer des informations d’achat spécifiques pour l’événement d’achat. La variable s.purchaseID sert à sérialiser (dédupliquer) l’événement.
seo-title: Événements d’achat
solution: Analytics
title: Événements d’achat
topic: Développeur et mise en œuvre
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: e21bb18dd0d0eb13222c655091c3a87939a0351d

---


# Événements d’achat

Les variables Analytics sont utilisées pour capturer des informations d’achat spécifiques pour l’événement d’achat. La variable `s.purchaseID` sert à sérialiser (dédupliquer) l’événement.

Si un événement d’achat est appelé sans `purchaseID`, un identifiant unique est automatiquement généré sur la base des variables `s.products` et `s.events`. Cet ID d’achat généré automatiquement est stocké localement sous forme de valeur de cookie dans le navigateur du visiteur et n’est pas envoyé à Adobe. Les identifiants d’achat définis manuellement sont par contre envoyés à Adobe. Les cinq derniers achats effectués par un visiteur (avec ou sans ID d’achat) sont stockés dans le cookie local.

Lorsqu’un visiteur procède à un achat, plusieurs vérifications sont réalisées :

* La variable l’ID d’achat correspond à l’une des cinq valeurs de cookie ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports. 
* Si `s.purchaseID` est défini, correspond-il à une valeur déjà collectée dans la suite de rapports ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports. 

Du code côté serveur spécifique peut être utilisé pour générer le numéro unique (valeur alphanumérique) incorporé dans la source HTML. En règle générale, l’identifiant de commande, ou une valeur alphanumérique similaire, est utilisé à cette fin. Cette valeur ne doit pas être modifiée lorsque l’utilisateur actualise la page.

## Syntaxe

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
