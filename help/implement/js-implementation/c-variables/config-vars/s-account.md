---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.account

La variable détermine la suite de rapports dans laquelle les données sont stockées et consignées.

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. L’ID de la suite de rapports est déterminé par Adobe.

## Paramètres

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| 40 octets | Dans le chemin de l’URL | N/D | N/D |

Chaque ID de suite de rapports doit correspondre à la valeur créée dans [!DNL Admin Console]. La taille de cet ID est limitée à 40 octets ; cependant, la somme de toutes les suites de rapports (toute la liste des valeurs séparées par des virgules) est illimitée.

La suite de rapports est le niveau de segmentation le plus fondamental dans le cadre de la création de rapports. Vous pouvez définir autant de suites de rapports que le permet votre contrat. Chaque suite de rapports fait référence à un ensemble dédié de tableaux remplis dans les serveurs de collecte d’Adobe. Une suite de rapports est identifiée par la variable `s_account` dans votre code JavaScript.

La liste déroulante des sites située dans le coin supérieur gauche des rapports d’[!DNL Analytics] affiche la suite de rapports active. Un identifiant (ID) unique est affecté à chaque suite de rapports. La variable `s_account` contient un ou plusieurs ID auxquels des données sont envoyées. La valeur d’ID de la suite de rapports est invisible pour les utilisateurs d’[!DNL Analytics]. Elle doit être fournie ou approuvée par Adobe avant son utilisation. Un « nom convivial », que vous pouvez modifier dans la section des suites de rapports d’[!DNL Admin Console], est associé à chaque ID de suite de rapports.

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). You can declare the `s_account` variable on the HTML page, which is a common practice when the value of `s_account` may change from page to page. Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. In some cases, the value of `s_account` also appears in the domain, before 112.2o7.net. La valeur indiquée dans le chemin est la seule qui détermine la suite de rapports de destination. Le texte en gras dans l’exemple ci-dessous affiche les suites de rapports auxquelles des données sont envoyées, telles qu’elles apparaissent dans le débogueur. Voir   [Débogueur DigitalPulse](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## Syntaxe et valeurs possibles

L’identifiant de la suite de rapports est une chaîne composée de caractères ASCII alphanumériques, d’une longueur maximale de 40 octets. Le trait d’union est le seul caractère spécial autorisé. Les espaces, les points, les virgules et les autres signes de ponctuation ne sont pas autorisés. La variable `s_account` peut contenir plusieurs suites de rapports ; elles reçoivent toutes des données de cette page.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

All values of `s_account` must be provided or approved by Adobe.

## Exemples

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

## Configuration de la variable dans Analytics

Le nom convivial associé à chaque ID de suite de rapports peut être modifié par Adobe [!DNL Customer Care]. Ce nom est visible dans la liste déroulante des sites située dans le coin supérieur gauche d’[!DNL Analytics].

## Pièges, questions et conseils

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. Utilisez le [!DNL DigitalPulse Debugger] pour déterminer les suites de rapports de ce type.

* Dans certains cas, [!DNL VISTA] peut être utilisé pour modifier la suite de rapports de destination. Il est conseillé d’utiliser [!DNL VISTA] pour réacheminer ou copier les données sur une autre suite de rapports en cas d’utilisation de cookies propriétaires ou si votre site comporte plus de 20 suites actives.

* Always declare `s_account` inside the JS file or just before it is included.
