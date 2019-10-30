---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.charSet

La propriété charSet, normalement définie dans le fichier JavaScript, permet à Analytics de convertir les données entrantes en UTF-8 pour le stockage et la création de rapports par Analytics.

>[!NRemarque :] La propriété charSet est nécessaire lors de l’envoi de données vers une suite de rapports multioctet et ne doit jamais être utilisée avec une suite de rapports standard. L’utilisation de la propriété charSet avec une suite de rapports ISO standard peut provoquer une troncature de la variable ou une conversion inattendue des caractères.

La valeur de la propriété charSet doit correspondre à l’encodage de la page Web utilisé dans la balise META ou l’en-tête http, même si la syntaxe est légèrement différente. Bien que la balise META utilise un alias pour l’encodage, la valeur de charSet doit utiliser le nom recommandé (ou officiel) de l’encodage.

Le tableau suivant répertorie certains des encodages les plus fréquents avec leur nom recommandé et leurs alias.

| Nom recommandé | Alias |
|--- |--- |
| ISO-8859-1 | ISO_8859-1, CP819, latin1 |
| ISO-8859-2 | ISO_8859-2, latin2 |
| ISO-8859-5 | ISO_8859-5, cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Comme il existe de nombreux encodages et alias, contactez votre conseiller en implémentation ou le service à la clientèle Adobe pour vérifier l’exactitude de la valeur de charSet si elle ne figure pas dans le tableau ci-dessus.

Si l’encodage d’un site web varie en fonction de la page ou en cas d’utilisation d’un fichier JavaScript unique pour plusieurs sites, il est possible de définir une valeur par défaut pour la propriété charSet dans le fichier JavaScript, puis de la réinitialiser sur des pages spécifiques si nécessaire ; par exemple, `s.charSet="UTF-8"` ou `s.charSet="SJIS"`.

Toute valeur non vide du paramètre charSet provoque la conversion des données en UTF-8 pour le stockage. Tous les caractères de la plage 128 à 255 sont convertis dans la séquence UTF-8 sur deux octets correcte puis stockés. Ces caractères ne s’afficheront pas correctement dans une suite de rapports standard. La propriété charSet ne doit donc jamais être utilisée avec une suite de rapports standard.

De même, une valeur vide du paramètre charSet contourne le processus de conversion de données et tous les caractères de la plage 128 à 255 sont alors stockés sur un seul octet. Ces caractères ne s’affichent pas correctement dans une suite de rapports multioctet, puisque les codes mono-octets de ces caractères ne sont pas des valeurs UTF-8 correctes. Le paramètre charSet ne doit donc jamais être utilisé avec une suite de rapports standard. De plus, la valeur exacte d’encodage de la page Web doit être utilisée.

Si la variable *`charSet`* contient une valeur incorrecte, la conversion des données de toutes les autres variables s’effectue de manière incorrecte. Si des variables JavaScript situées sur vos pages (*`pageName`*, [!UICONTROL prop1] ou *`channel`*, par exemple) contiennent uniquement des caractères ASCII, la variable *`charSet`* ne doit pas être définie. Toutefois, si les variables de vos pages contiennent des caractères non ASCII, la variable *`charSet`* doit être renseignée.

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
