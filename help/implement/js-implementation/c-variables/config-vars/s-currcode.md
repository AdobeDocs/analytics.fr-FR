---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.currencyCode

La variable détermine le taux de conversion à appliquer aux recettes.

Toutes les valeurs monétaires sont stockées dans la devise de votre choix. Si cette devise est identique à celle qui est spécifiée dans Si la valeur *`currencyCode`* ou *`currencyCode`* est vide, aucune conversion n’est appliquée.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|--- |--- |--- |--- |
| N/D | cc | Conversion &gt; Achats &gt; Recettes Tous les rapports de conversion affichant des recettes ou des valeurs monétaires | "USD" |

Si votre site autorise les visiteurs à effectuer des achats dans plusieurs devises, vous devez utiliser la variable *`currencyCode`* pour vous assurer que les recettes sont stockées dans la devise appropriée. Si, par exemple, la devise de base de votre suite de rapports est le dollar américain (USD) et que vous vendez un article au prix de 40 euros, vous devez renseigner « EUR » dans la variable *`currencyCode`* sur la page HTML. Dès que la collecte de données reçoit les données, elle utilise le taux de conversion en cours pour convertir le montant de 40 euros dans son équivalent en dollars.

Il est recommandé de renseigner la variable *`currencyCode`* sur la page HTML, au lieu du fichier JavaScript, si vous vendez des articles dans plusieurs devises. Si vous souhaitez utiliser vos propres taux de conversion plutôt que ceux utilisés par Adobe, définissez *`currencyCode`* pour correspondre à la devise de base de votre suite de rapports. Convertissez ensuite toutes les recettes avant de les envoyer dans [!DNL Analytics].

La conversion de devise s’applique à la fois aux recettes et à tout événement monétaire. Il s’agit d’événements utilisés pour additionner des valeurs semblables à des recettes, telles que des taxes et des frais d’expédition. Les recettes et les événements monétaires sont spécifiés dans la chaîne « products ». Pour plus d’informations sur la chaîne « products », reportez-vous à la section [events](https://docs.adobe.com/content/help/en/analytics/implementation/analytics-basics/ref-events.html).

## Syntaxe et valeurs possibles

```js
s.currencyCode="currency_code"
```

## Exemples

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

## Paramètres de configuration

Adobe [!DNL Customer Care] peut modifier le paramètre de devise par défaut de votre suite de rapports. Lorsque vous modifiez la devise de base d’une suite de rapports, les recettes existantes figurant dans le système ne sont pas converties. Toutes les nouvelles valeurs de recettes sont converties en conséquence.

## Pièges, questions et conseils

* Si vous constatez des recettes étonnamment importantes dans les rapports, assurez-vous que la variable *`currencyCode`* et la devise de base de la suite de rapports sont correctement définies.
* La variable *`currencyCode`* n’est pas persistante, ce qui signifie qu’elle doit être transmise dans la même demande d’image que les recettes ou toute autre mesure liée aux devises.
* Les événements monétaires doivent uniquement être utilisés pour les devises. Si vous devez comptabiliser des valeurs arbitraires ou dynamiques qui ne sont pas des devises, utilisez le type d’événement [!UICONTROL numeric].
* Lorsque la variable *`currencyCode`* est vide, aucune conversion n’est appliquée.

Pour plus d’informations, voir Codes [de](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/currency.html)devise.
