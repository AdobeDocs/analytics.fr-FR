---
title: Mise en œuvre à l’aide d’AJAX
description: Découvrez comment mettre en œuvre Adobe Analytics sur un site à l’aide d’AJAX.
feature: Implementation Basics
exl-id: 3286bf97-3a66-4f68-9053-bf84269962fd
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 100%

---

# Mise en œuvre à l’aide d’AJAX

AJAX utilise JavaScript et HTML pour effacer et générer du contenu sans charger de nouvelle page.

Adobe Analytics utilise normalement le rechargement des pages pour réinitialiser l’objet de suivi Analytics. Chaque fois que vous accédez à une URL différente, toutes les variables Analytics sont réinitialisées et peuvent être définies à nouveau. Lors de l’utilisation d’AJAX sur votre site, ajustez votre mise en œuvre en fonction de l’absence d’actualisation des pages afin de vous assurer que les données ne restent pas incorrectes entre les accès.

Une fois que vous avez mis en place des mesures pour effacer les valeurs de variable, la mise en œuvre d’Adobe Analytics sur les sites qui utilisent AJAX est essentiellement la même que les autres méthodes de mise en œuvre.

## Détermination des interactions et des types d’accès

Comme les pages qui utilisent AJAX ne se rechargent généralement pas, il existe plusieurs interactions qu’un utilisateur peut entreprendre sur votre site. Lors de la mise en œuvre d’Adobe Analytics, veillez à différencier les pages vues des appels de suivi des liens. Tenez compte de la question suivante pour chaque interaction qu’un utilisateur peut entreprendre sur votre site :

*Lorsqu’un utilisateur interagit avec mon site, cette interaction change-t-elle suffisamment du contenu de la page pour être considérée comme une nouvelle page ?*

* Si la réponse est **oui**, pensez à utiliser un appel de suivi des pages vues (`s.t()`).
* Si la réponse est **non**, envisagez d’effectuer le suivi de cette interaction à l’aide d’un appel de suivi des liens (`s.tl()`).

>[!NOTE]
>
>Toutes les interactions ou tous les clics ne doivent pas être enregistrés. Examinez attentivement les actions qui sont les plus importantes à suivre et envoyez les données à Adobe en conséquence.

## Effacement des variables sur chaque page

Les valeurs de variable persistent sur les pages utilisant AJAX, car la page ne se recharge pas. Par conséquent, des mesures d’adaptation spéciales sont nécessaires pour effacer les valeurs variables afin qu’elles ne persistent pas incorrectement dans les accès. Adobe offre la fonction [`clearVars`](../vars/functions/clearvars.md) permettant d’effacer facilement les valeurs de variable. Veillez à utiliser cette fonction après avoir envoyé chaque accès à Adobe et avant de définir les valeurs de variable pour le prochain accès.

>[!TIP]
>
>La fonction `clearVars()` n’est pas disponible dans le code H. Si vous n’avez pas effectué la mise à niveau vers AppMeasurement, définissez chaque valeur de variable Analytics sur une chaîne vide.

## Exemples

L’exemple suivant utilise JavaScript simple pour effacer les valeurs de variable existantes, définir de nouvelles valeurs, puis envoyer une demande d’image à Adobe :

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

L’exemple suivant illustre un appel de suivi dans le rappel `done` de la fonction `.ajax` de JQuery :

```js
$.ajax({
  url: "example.html",
  dataType: "html"
})
  .done(function( response ) {
    $( "#content" ).html( response );
  s.clearVars();
  s.pageName = $( "h1:first" ).text();
  s.t();
  });
```
