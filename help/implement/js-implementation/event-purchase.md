---
description: Les variables Analytics sont utilisées pour capturer des informations d’achat spécifiques pour l’événement d’achat. La variable s.purchaseID sert à sérialiser (dédupliquer) l’événement.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables Analytics sont utilisées pour capturer des informations d’achat spécifiques pour l’événement d’achat. La variable s.purchaseID sert à sérialiser (dédupliquer) l’événement.
seo-title: Evénements d'achat
solution: Analytics
title: Evénements d'achat
topic: Développeur et mise en œuvre
uuid: d 90 cdec 7-7397-445 a -84 e 5-31014 f 7 ff 875
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Evénements d'achat

Les variables Analytics sont utilisées pour capturer des informations d’achat spécifiques pour l’événement d’achat. La variable s.purchaseID sert à sérialiser (dédupliquer) l’événement.

The *`purchaseID`* is limited to 20 characters. La variable *`purchaseID`* sérialise tous les événements transmis dans la variable [!UICONTROL s.events] et remplace toute valeur de sérialisation pour les événements. If *`purchaseID`* is left blank, each instance of the purchase event, even page reloads, is counted.

Si un événement d’achat est appelé sans *`purchaseID`*, un identifiant unique est automatiquement généré sur la base des variables *`s.products`* et *`s.events`.* Ce *`purchaseID`généré automatiquement est stocké en local en tant que valeur de cookie dans le navigateur du visiteur et n’est envoyé à aucun tableau de la suite de rapports.* Manually defined *`purchaseID`*s on the other hand are sent to a back-end table within the report suite. The last five purchases made by a visitor (with or without *`purchaseID`*) are stored in the local cookie.

Lorsqu’un visiteur procède à un achat, plusieurs vérifications sont réalisées :

* La variable *`purchaseID`* correspond-elle à l’une des cinq valeurs du cookie ? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports. 
* If *`purchaseID`* is defined, does it match any value in the report suite's back-end table? Si tel est le cas, la demande d’image est considérée comme un achat en double. Aucune variable de conversion, y compris l’événement d’achat, ne figure dans les rapports. 
* Si le *`purchaseID`* est propre aux 5 dernières valeurs stockées dans le cookie et au tableau *`purchaseID`de la suite de rapports, la demande d’image est unique et incluse dans les rapports.* Si, par exemple, cinq achats ont déjà été inclus dans le cookie local, l’achat le plus ancien est écrasé.

Du code côté serveur spécifique peut être utilisé pour générer le numéro unique (valeur alphanumérique) incorporé dans la source HTML. En règle générale, l’identifiant de commande, ou une valeur alphanumérique similaire, est utilisé à cette fin. Cette valeur ne doit pas être modifiée lorsque l’utilisateur actualise la page. Voici un court exemple (notez le code *`purchaseID`* en gras) :

## du lien personnalisé{#section_4FBF138093BD41F59885D2ACC429FF5B}

```js
s.products="Category;ProductName;Qty;total_price [,Category2;ProductName2;Qty;total_price]" 
s.state="XX" 
s.zip="00000" 
 
<b>s.purchaseID="<%=getPurchaseID()%>"</b> 
s.events="purchase" 
```

## Exemples {#section_2CBA9B6386A146C0BEF375E1B55687BC}

```js
s.products="Footwear;Hiking Boots (1234);1;170.00" 
s.state="UT" 
s.zip="84097" 
s.purchaseID="12341234" 
s.events="purchase"
```

## Remarques supplémentaires {#section_5A0590B8FD4F40DC89776F55ED9DE668}

* Veillez à utiliser du code côté serveur pour générer l’identifiant unique de l’événement. N’utilisez pas de fonction de génération aléatoire JavaScript pour générer un numéro, car elle génère un numéro unique à chaque chargement de la page (chaque [!UICONTROL instance]/[!UICONTROL pageview] est comptabilisé).

* Les identifiants uniques sont applicables à tous les utilisateurs pour toutes les sessions. Vous devez donc vous assurer que l’identifiant est unique pour les utilisateurs et les sessions. Par exemple, si l’identifiant de commande est réutilisé au bout de 30 jours, ajoutez la date de la commande pour que cet [!UICONTROL identifiant] soit unique.
* La valeur de sérialisation peut être une valeur alphanumérique comportant jusqu’à 20 caractères. Cette limite est identique à celle de la variable [!UICONTROL s.purchaseID] (remplacez s. par s_ pour le code version G).
* La variable [!UICONTROL s.purchaseID] sérialise tous les événements transmis dans la variable [!UICONTROL s.events] et remplace toute valeur de sérialisation pour les événements. N’utilisez pas la [!UICONTROL sérialisation d’événements] pour les événements si la variable [!UICONTROL s.purchaseID] est utilisée sur la page active (remplacez s. par s_ pour le code version G).

