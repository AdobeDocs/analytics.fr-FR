---
title: writeSecureCookies
description: Permet à AppMeasurement de définir des cookies avec l’attribut Secure.
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
source-git-commit: b93cd06c2a8867f4848dc317e426b73dcfbb5dfd
workflow-type: ht
source-wordcount: '238'
ht-degree: 100%

---

# writeSecureCookies

La variable`writeSecureCookies` permet à AppMeasurement de définir des [cookies sécurisés](https://en.wikipedia.org/wiki/Secure_cookie) pour Analytics. Ce paramètre s’applique à la fois aux cookies identifiant visiteur définis par AppMeasurement et aux cookies que vous définissez à l’aide de la méthode `Util.CookieWrite()`. Elle nécessite AppMeasurement 2.18.0 ou une version ultérieure.

`writeSecureCookies` sʼapplique uniquement aux cookies définis par JavaScript AppMeasurement (`s_fid`, `s_cc` et `s_sq`). Les cookies définis par la réponse `https` (`s_vi` et `s_ecid`) peuvent être définis sur « sécurisés » en contactant lʼassistance clientèle Adobe.

Apprenez en plus sur les cookies Analytics [ici](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=fr).

>[!IMPORTANT]
>
>Si vous activez la variable `writeSecureCookies`, assurez-vous que tout le contenu de votre site est diffusé en toute sécurité via HTTPS. AppMeasurement ne fonctionne pas si cette variable est activée et que votre page contient du contenu non sécurisé.

## Écrire des cookies sécurisés dans Adobe Experience Platform Launch

[!UICONTROL Écrire des cookies sécurisés] est une case à cocher située sous l’accordéon [!UICONTROL Cookies] lors de la configuration de l’extension Adobe Analytics.

1. Connectez-vous à [launch.adobe.com](https://launch.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de votre choix.
3. Accédez à l’onglet [!UICONTROL Extensions], puis cliquez sur le bouton [!UICONTROL Configurer] sous Adobe Analytics.
4. Développez l’accordéon [!UICONTROL Cookies], qui affiche la case à cocher [!UICONTROL Écrire des cookies sécurisés].

## s.writeSecureCookies dans AppMeasurement et l’éditeur de code personnalisé Launch

La variable `s.writeSecureCookies` est une valeur booléenne qui détermine si AppMeasurement définit l’attribut Secure lors de la création d’un cookie. Sa valeur par défaut est `false`. Définissez cette variable sur `true` si tout le contenu de votre site est sécurisé et que vous souhaitez que les cookies définis par AppMeasurement possèdent l’attribut Secure.

```js
s.writeSecureCookies = true;
```
