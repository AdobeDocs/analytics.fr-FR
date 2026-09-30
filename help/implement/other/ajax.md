---
title: Mise en œuvre à l’aide d’AJAX
description: Découvrez comment mettre en œuvre Adobe Analytics sur un site à l’aide d’AJAX.
feature: Implementation Basics
exl-id: 3286bf97-3a66-4f68-9053-bf84269962fd
role: Developer
autotag-review: '2026-05-22T08:06:40.936Z'
TQID: 'https://experienceleague.adobe.com/M0MNFZRcHpPwxL-ZtTky67DHDr1A0fL-peaGKicXgIM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 100%
---
# Mise en œuvre à l’aide d’AJAX

AJAX utilise JavaScript et HTML pour effacer et générer du contenu sans charger de nouvelle page.

Adobe Analytics utilise normalement le rechargement des pages pour réinitialiser l’objet de suivi Analytics. Chaque fois que vous accédez à une URL différente, toutes les variables Analytics sont réinitialisées et peuvent être définies à nouveau. Lorsque vous utilisez AJAX sur votre site, adaptez votre implémentation à l’absence d’actualisation des pages afin de vous assurer que les données ne persistent pas de manière incorrecte entre les hits.

Une fois que vous avez mis en place des mesures pour effacer les valeurs de variable, la mise en œuvre d’Adobe Analytics sur les sites qui utilisent AJAX est essentiellement la même que les autres méthodes de mise en œuvre.

## Détermination des interactions et des types de hits

Comme les pages qui utilisent AJAX ne se rechargent généralement pas, il existe plusieurs interactions qu’un utilisateur peut entreprendre sur votre site. Lors de la mise en œuvre d’Adobe Analytics, veillez à différencier les pages vues des appels de suivi des liens. Tenez compte de la question suivante pour chaque interaction qu’un utilisateur peut entreprendre sur votre site :

*Lorsqu’un utilisateur interagit avec mon site, cette interaction change-t-elle suffisamment du contenu de la page pour être considérée comme une nouvelle page ?*

* Si la réponse est **oui**, pensez à utiliser un appel de suivi des pages vues (`s.t()`).
* Si la réponse est **non**, envisagez d’effectuer le suivi de cette interaction à l’aide d’un appel de suivi des liens (`s.tl()`).

>[!NOTE]
>
>Toutes les interactions ou tous les clics ne doivent pas être enregistrés. Examinez attentivement les actions qui sont les plus importantes à suivre et envoyez les données à Adobe en conséquence.

## Effacement des variables sur chaque page

Les valeurs de variable persistent sur les pages utilisant AJAX, car la page ne se recharge pas. Par conséquent, des mesures d’adaptation spéciales sont nécessaires pour effacer les valeurs variables afin qu’elles ne persistent pas incorrectement dans les hits. Adobe offre la fonction [`clearVars`](../vars/functions/clearvars.md) permettant d’effacer facilement les valeurs de variable. Veillez à utiliser cette fonction après avoir envoyé chaque hit à Adobe et avant de définir les valeurs de variable pour le prochain hit.

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
