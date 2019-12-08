---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# Propriétés de liste

Les props de liste sont une liste délimitée de valeurs transmises dans une variable, puis signalées comme lignes individuelles. Elles sont généralement implémentées sur des pages contenant des valeurs pouvant être sélectionnées par l’utilisateur, telles que des éléments répertoriés avec des cases à cocher ou des cases d’option. Les props de liste s’avèrent utiles lorsque vous souhaitez définir plusieurs valeurs dans une variable sans envoyer plusieurs demandes d’image.


<!-- 

list_props.xml

 -->

**Considérations**

* Les propriétés de liste ne sont activées que sur les variables de trafic ( [props](/help/implement/js-implementation/page-variables/propn.md)).
* Le cheminement et les corrélations ne peuvent pas être activés pour les props de liste.
* Analytics fournit les visites et visiteurs uniques à presque tous les rapports, notamment tous les rapports sur les props de liste.
* Les classifications sont prises en charge pour les propriétés de liste.
* Toute variable de trafic personnalisée peut devenir une propriété de liste. (Exceptions : [pageName](/help/implement/js-implementation/page-variables/pagename.md), [canal](/help/implement/js-implementation/page-variables/channel.md) et [serveur](/help/implement/js-implementation/page-variables/server.md).)

* Lors de la définition de valeurs dupliquées dans une même demande d’image, les instances ne sont pas dédupliquées.

Vous pouvez changer une variable prop dans une liste sur la page Outils d’administration &gt; Suite de rapports &gt; Variables de trafic en activant la prise en charge des listes et en sélectionnant un délimiteur. Les délimiteurs les plus courants sont les suivants : deux-points, points-virgules, virgules et barres verticales. D’un point de vue technique, il peut s’agir de l’un des 127 premiers caractères ASCII.

**Exemples de mise en œuvre**

Lorsque vous demandez l’activation de propriétés de liste, indiquez le délimiteur à utiliser. Après avoir activé la variable *`s.prop`* de votre choix, vous pouvez définir plusieurs valeurs, comme illustré dans les exemples suivants :

Une propriété de liste délimitée par une barre verticale, transmettant deux valeurs :

```js
s.prop1="Banner ad impression|Sidebar impression"
```

Une propriété de liste délimitée par une virgule, transmettant plusieurs valeurs :

```js
s.prop2="cerulean,vermilion,saffron"
```

Les propriétés de liste peuvent également être envoyées avec une seule valeur :

```js
s.prop3="Single value"
```

Vous pouvez changer de délimiteur à tout moment. L’implémentation doit toutefois correspondre au nouveau délimiteur. Si vous n’utilisez pas le délimiteur correct, la valeur de propriété de liste sera considérée comme un élément concaténé unique dans les rapports.

Comme une prop de liste reste une variable de trafic, elle est donc soumise aux mêmes limites que cette dernière. Les props de liste sont limitées à 100 octets de données et sont sensibles à la casse.

