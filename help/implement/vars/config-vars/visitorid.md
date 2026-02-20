---
title: visitorID
description: Permet d’utiliser un identifiant visiteur personnalisé.
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: de98bf68c57f5453b6662f6e6e57312d8fd3e642
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 19%

---

# visitorID

Adobe utilise plusieurs méthodes différentes pour [identifier les visiteurs](../../id/overview.md) sur votre site. **La variable `visitorID` remplace toutes les autres méthodes d’identification des visiteurs.**

>[!IMPORTANT]
>
>Adobe conseille d’utiliser cette variable. Utilisez plutôt [Adobe Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr).

## Utilisation de `visitorID` par Analytics

Cette variable est un remplacement manuel de l’identifiant visiteur qui remplace toutes les autres formes d’identification des visiteurs. Pour être comptabilisé comme un seul visiteur, chaque accès pour une personne doit utiliser la même valeur `visitorID`.

* Les accès qui omettent `visitorID` reviennent à une autre méthode d’identification des visiteurs et sont traités comme un visiteur distinct.
* Les accès qui utilisent plusieurs valeurs `visitorID` sont traités comme des visiteurs distincts.
* Adobe n’assemble pas les accès qui utilisent différents ID de visiteur.

Voir [Identification des visiteurs dans Adobe Analytics](../../id/overview.md) pour plus d’informations sur la priorité d’identification et la raison pour laquelle le mélange d’identifiants peut gonfler le nombre de visiteurs.

>[!WARNING]
>
>Définissez `visitorID` uniquement si vous pouvez garantir qu’il est défini sur chaque accès pour cette personne et que la valeur ne change jamais. La définir uniquement sur certains accès, l’introduire au cours d’une visite (par exemple lors de l’authentification) ou la modifier entre les accès divise l’activité d’un seul visiteur en plusieurs visiteurs.

>[!CAUTION]
>
>Des valeurs d’identifiant visiteur personnalisé non valides peuvent entraîner des données incorrectes et de mauvaises performances en matière de rapports. Si cette variable contient une valeur par défaut ou d’espace réservé (telle que `"0"` ou `"NULL"`), Adobe traite ces accès comme s’ils étaient le même visiteur. Cette situation génère des données incorrectes, avec un nombre de visiteurs artificiellement faible et des segments au niveau du visiteur qui ne fonctionnent pas comme prévu. Une implémentation incorrecte des identifiants de visiteur personnalisés peut également introduire une charge importante sur les serveurs de traitement, ce qui augmente la [latence](/help/technotes/latency.md) et diminue les performances des rapports.

## Identifiant visiteur utilisant l’extension Adobe Analytics

L’[!UICONTROL identifiant visiteur] est un champ sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Sélectionnez la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL &#x200B; Extensions] puis sélectionnez le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies], ce qui permet d’afficher le champ [!UICONTROL Identifiant visiteur].

Affectez ce champ à l’élément de données contenant votre identifiant visiteur personnalisé. **Ne définissez pas ce champ sur une valeur statique unique pour tous les visiteurs.** Utilisez un élément de données qui est résolu par visiteur et qui reste constant pour tous les accès.

## s.visitorID dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.visitorID` est une chaîne qui contient un identifiant unique personnalisé pour le visiteur. Les valeurs valides comprennent des caractères alphanumériques jusqu’à 100 octets. Évitez d’utiliser des tirets, des espaces, des traits de soulignement ou des symboles dans cette variable.

```js
s.visitorID = "abc123";
```

## Identifiant visiteur à l’aide de Web SDK

Adobe Experience Platform Edge Network vous permet de fournir plusieurs identifiants à l’aide de la [carte des identités](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html?lang=fr#using-identitymap) de XDM. Chaque identité d’un mappage d’identités comporte un espace de noms différent. Vous pouvez spécifier l’espace de noms à utiliser pour l’identifiant visiteur dans le cadre de la [configuration du flux de données](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=fr#analytics). Une fois ce champ configuré, lorsque vous envoyez un événement avec une valeur spécifiée pour cet espace de noms, il est automatiquement utilisé comme identifiant visiteur dans Analytics.
