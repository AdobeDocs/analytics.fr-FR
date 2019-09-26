---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.charSet

La propriété charSet, qui est normalement définie dans le fichier JavaScript, est utilisée par Analytics pour convertir les données entrantes au format UTF-8 en vue de les stocker et de créer des rapports par Analytics.

>[!N] Remarque : La propriété charSet est requise lors de l’envoi de données vers une suite de rapports multioctet et ne doit jamais être utilisée avec une suite de rapports standard. L’utilisation de la propriété charSet avec une suite de rapports ISO standard peut provoquer une troncature de la variable ou une conversion inattendue des caractères.

La valeur de la propriété charSet doit correspondre à l’encodage de la page Web utilisé dans la balise META ou l’en-tête http, même si la syntaxe est légèrement différente. Bien que la balise META utilise un alias pour l’encodage, la valeur de charSet doit utiliser le nom recommandé (ou officiel) de l’encodage.

Le tableau suivant répertorie certains des encodages les plus fréquents avec leur nom recommandé et leurs alias.

| Nom recommandé | Alias |
|--- |--- |
| ISO-8859-1 | ISO_8859-1, CP819, latin1 |
| ISO-8859-2 | ISO_8859-2, latin2 |
| ISO-8859-5 | ISO_8859-5, cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Because numerous encodings and aliases exist, contact your Implementation Consultant or Adobe Customer Care to confirm the proper value for charSet if it does not appear in the table above.

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

Toute valeur non vide du paramètre charSet provoque la conversion des données en UTF-8 pour le stockage. Tous les caractères de la plage 128 à 255 sont convertis dans la séquence UTF-8 sur deux octets correcte puis stockés. Ces caractères ne s’afficheront pas correctement dans une suite de rapports standard. La propriété charSet ne doit donc jamais être utilisée avec une suite de rapports standard.

De même, une valeur vide du paramètre charSet contourne le processus de conversion de données et tous les caractères de la plage 128 à 255 sont alors stockés sur un seul octet. Ces caractères ne s’affichent pas correctement dans une suite de rapports multioctet, puisque les codes mono-octets de ces caractères ne sont pas des valeurs UTF-8 correctes. Le paramètre charSet ne doit donc jamais être utilisé avec une suite de rapports standard. De plus, la valeur exacte d’encodage de la page Web doit être utilisée.

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. Toutefois, si les variables de vos pages contiennent des caractères non ASCII, la *`charSet`* variable doit être renseignée.

## Paramètres

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | CE | N/D | "" |

## Syntaxe et valeurs possibles

```js
s.charSet="character_set"
```

## Exemples

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```
