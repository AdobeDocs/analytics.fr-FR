---
title: visitorID
description: Permet d’utiliser un identifiant visiteur personnalisé.
feature: Variables
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 72%

---

# visitorID

Adobe utilise plusieurs méthodes différentes pour identifier les visiteurs de votre site. La variable `visitorID` remplace toutes les autres méthodes d’identification des visiteurs.

>[!IMPORTANT]
>
>Adobe conseille d’utiliser cette variable. Utilisez plutôt [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr).

## Identifiant visiteur utilisant l’extension Adobe Analytics

L’[!UICONTROL identifiant visiteur] est un champ sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies], ce qui permet d’afficher le champ [!UICONTROL Identifiant visiteur].

Affectez ce champ à l’élément de données contenant votre identifiant visiteur personnalisé. Ne définissez pas ce champ sur une valeur statique.

## s.visitorID dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.visitorID` est une chaîne qui contient un identifiant unique personnalisé pour le visiteur. Les valeurs valides comprennent des caractères alphanumériques jusqu’à 100 octets. Évitez d’utiliser des tirets, des espaces, des traits de soulignement ou des symboles dans cette variable.

>[!WARNING]
>
>Si vous définissez la variable `visitorID` à mi-chemin au cours d’une visite, les données génèrent deux visiteurs uniques distincts.

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>Une implémentation non valide des identifiants visiteur personnalisés peut se traduire par des données incorrectes et de mauvaises performances en matière de rapports. Si cette variable contient une valeur par défaut (telle que `"0"` ou `"NULL"`), Adobe traite ces accès comme s’il s’agissait du même visiteur. Cette situation génère des données incorrectes, avec un faible nombre de visiteurs et des segments au niveau des visiteurs qui ne fonctionnent pas comme prévu. L’implémentation incorrecte des identifiants visiteur personnalisés entraîne également une charge importante sur les serveurs de traitement, ce qui augmente la [latence](/help/technotes/latency.md) et réduit les performances en matière de rapports.

## Identifiant visiteur utilisant le SDK Web et Experience Edge

Experience Edge vous permet de fournir plusieurs identifiants à l’aide de XDM [Carte des identités](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html?lang=en#using-identitymap). Chaque identité d’une carte des identités comporte un espace de noms différent. Vous pouvez spécifier l’espace de noms à utiliser pour l’identifiant visiteur dans le cadre de [configuration des flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#analytics). Une fois configuré, lorsque vous envoyez un événement avec une valeur spécifiée pour cet espace de noms, il est automatiquement utilisé comme identifiant visiteur dans Analytics.
