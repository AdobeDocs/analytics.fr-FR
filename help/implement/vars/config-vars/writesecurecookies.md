---
title: writeSecureCookies
description: Permet à AppMeasurement de définir des cookies avec l’attribut Secure.
feature: Appmeasurement Implementation
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
role: Admin, Developer
TQID: https://experienceleague.adobe.com/-tuPYoFSzQb6-auIIAuihn--8Hb6vTKjIhhFd1XfXRQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 278
ht-degree: 77%

---

# writeSecureCookies

La variable`writeSecureCookies` permet à AppMeasurement de définir des [cookies sécurisés](https://en.wikipedia.org/wiki/Secure_cookie) pour Analytics. Ce paramètre s’applique à la fois aux cookies identifiant visiteur définis par AppMeasurement et aux cookies que vous définissez à l’aide de la méthode `Util.CookieWrite()`. Elle nécessite AppMeasurement 2.18.0 ou une version ultérieure.

`writeSecureCookies` sʼapplique uniquement aux cookies définis par JavaScript AppMeasurement (`s_fid`, `s_cc` et `s_sq`). Les cookies définis par la réponse `https` (`s_vi` et `s_ecid`) peuvent être définis sur « sécurisés » en contactant lʼassistance clientèle Adobe.

Apprenez en plus sur les cookies Analytics [ici](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=fr).

>[!WARNING]
>
>Si vous activez la variable `writeSecureCookies`, assurez-vous que tout le contenu de votre site est diffusé en toute sécurité via HTTPS. La collecte de données ne fonctionne pas correctement si cette variable est activée et que votre page contient du contenu non sécurisé.

## Utilisation de cookies sécurisés avec le Web SDK

Si votre site utilise le protocole HTTPS, l’attribut Secure est défini pour tous les cookies définis par Web SDK.

## Écrire des cookies sécurisés à l’aide de l’extension Adobe Analytics

[!UICONTROL Écrire des cookies sécurisés] est une case à cocher située sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton **[!UICONTROL Configurer]** sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies], qui affiche la case à cocher [!UICONTROL Écrire des cookies sécurisés].

## s.writeSecureCookies dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

La variable `s.writeSecureCookies` est une valeur booléenne qui détermine si AppMeasurement définit l’attribut Secure lors de la création d’un cookie. Sa valeur par défaut est `false`. Définissez cette variable sur `true` si tout le contenu de votre site est sécurisé et que vous souhaitez que les cookies définis par AppMeasurement possèdent l’attribut Secure.

```js
s.writeSecureCookies = true;
```
