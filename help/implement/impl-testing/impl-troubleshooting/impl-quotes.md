---
description: Lorsque vous saisissez des valeurs dans une variable, vous devez suivre quelques bonnes pratiques.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Utilisation de guillemets
topic: Developer and implementation
uuid: 9f09c48b-7ae5-441e-8635-fd6bdc2e94c7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Utilisation de guillemets

Lorsque vous saisissez des valeurs dans une variable, vous devez suivre quelques bonnes pratiques.

Vous pouvez utiliser des guillemets simples ou doubles, mais vous devez les utiliser de façon cohérente. Si vous choisissez des guillemets simples, vous devez toujours les utiliser. Il en est de même pour les guillemets doubles. Les deux exemples ci-dessous sont corrects.

```js
s.prop2='test' (single quotes)
```

```js
s.prop2="test" (double quotes)
```

Vérifiez que les guillemets anglais sont désactivés. Si vous utilisez des guillemets simples et que la valeur de la variable contient une apostrophe, JavaScript interprète cette dernière comme un guillemet simple. Cela signifie donc qu’il s’agit de la fin de la chaîne. Examinez l’exemple suivant :

```js
s.pageName='John's Home Page'
```

Dans ce cas, JavaScript interprète l’apostrophe (qui est également un guillemet simple) de « John’s » comme étant la fin de la chaîne. Dans la mesure où « s Home Page » n’a aucune signification en JavaScript, une erreur qui empêche la demande d’image se produit. Les deux exemples suivants fonctionnent :

```js
s.pageName='John\'s Home Page'
```

```js
s.pageName="John's Home Page"
```

Dans le premier exemple, vous pouvez ajouter une séquence d’échappement à l’apostrophe en insérant une barre oblique inverse (\) juste avant celle-ci. Cela indique à JavaScript que l’apostrophe ne termine pas la chaîne, mais qu’elle fait partie de celle-ci. La chaîne se termine ensuite comme prévu, au niveau du guillemet simple fermant. Le second exemple montre la chaîne entière placée entre guillemets doubles. Dans ce cas, un guillemet simple ne peut pas indiquer la fin de la chaîne. Il en est de même si un guillemet double fait partie de la chaîne. La valeur de s.pageName="L’équipe a déclaré "Nous avons gagné !"" est incorrecte en raison de l’utilisation de guillemets doubles dans la chaîne et autour de celle-ci. La valeur est correcte sous la forme s.pageName="L’équipe a déclaré \"Nous avons gagné!\"".
