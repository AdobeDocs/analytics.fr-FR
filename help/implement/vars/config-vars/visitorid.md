---
title: visitorID
description: Permet d’utiliser un identifiant visiteur personnalisé.
translation-type: tm+mt
source-git-commit: b9bb7a60398b8c392393a8d16b58292f91ab0ea7
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 71%

---


# visitorID

Adobe utilise plusieurs méthodes différentes pour identifier les visiteurs de votre site. La variable `visitorID` remplace toutes les autres méthodes d’identification des visiteurs.

>[!IMPORTANT] Adobe conseille d’utiliser cette variable. Utilisez plutôt [Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html).

## Identifiant visiteur dans Adobe Experience Platform Launch

[!UICONTROL L’identifiant visiteur] est un champ sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies], ce qui permet d’afficher le champ [!UICONTROL Identifiant visiteur].

Affectez ce champ à l’élément de données contenant votre identifiant visiteur personnalisé. Ne définissez pas ce champ sur une valeur statique.

## s.visitorID dans AppMeasurement et l’éditeur de code personnalisé de Launch

La variable `s.visitorID` est une chaîne qui contient un identifiant unique personnalisé pour le visiteur. Les valeurs valides comprennent des caractères alphanumériques jusqu’à 100 octets. Évitez d’utiliser des tirets, des espaces, des traits de soulignement ou des symboles dans cette variable.

>[!WARNING] Si vous définissez la variable `visitorID` à mi-chemin au cours d’une visite, les données génèrent deux visiteurs uniques distincts.

```js
s.visitorID = "abc123";
```

>[!CAUTION] Une mise en oeuvre non valide des identifiants de visiteur personnalisés peut entraîner des données incorrectes et des performances de rapports médiocres. Si cette variable contient une valeur par défaut (telle que `"0"` ou `"NULL"`), Adobe traite ces accès comme s’ils étaient du même visiteur. Cette situation génère des données incorrectes, avec un faible nombre de visiteurs et des segments au niveau du visiteur qui ne fonctionnent pas comme prévu. Les identifiants de visiteur personnalisés incorrectement implémentés entraînent également une charge importante sur les serveurs de traitement, augmentant la [latence](/help/technotes/latency.md) et réduisant les performances des rapports.
