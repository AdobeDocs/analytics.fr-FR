---
description: Procéder à une implémentation à l’aide d’AJAX est tout comme déployer du code sur une page HTML standard.
keywords: Mise en œuvre d’Analytics
seo-description: Procéder à une implémentation à l'aide d'AJAX est tout comme déployer du code sur une page HTML standard.
seo-title: Implémentation à l'aide d'AJAX
solution: Analytics
title: Implémentation à l’aide d’AJAX
topic: Développeur et mise en œuvre
uuid: 9 e 3477 ef -7 dea -4 c 76-ab 61-36 a 188222 be 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Implémentation à l’aide d’AJAX

Procéder à une implémentation à l’aide d’AJAX est tout comme déployer du code sur une page HTML standard.

L’entreprise souhaite obtenir des réponses à ses questions. Les besoins sont évalués, et les variables sont affectées. La conception est ensuite appliquée et déployée. Ces concepts doivent vous être familiers si vous avez déjà procédé aux étapes initiales de l’implémentation.

## Conception de la solution {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

[!UICONTROL AJAX] demande tout d’abord que vous déterminiez le niveau d’informations détaillées à rassembler. La modification du contenu de la page (microniveau) ou le suivi des attributs de l’application (microniveau) détermine les variables à définir et la méthode d’envoi des données à Adobe la plus adaptée.

## Déploiement du code {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

Le code JavaScript contient deux fonctions qui permettent d’envoyer des données. Vous devez suivre des instructions distinctes pour déterminer quelle méthode doit être utilisée pour envoyer des données.
Si une demande d’image a été précédemment effectuée sur la même page, vous devez d’abord effacer les valeurs des variables précédemment définies. Use the `clearVars()` funtion in [!DNL AppMeasurement] for JavaScript, or write a simple JavaScript function to clear the variables if you are using H code. Set the values appropriate for the changed content, namely the *`pageName`* variable. After the variables are set call the *`t()`* function.

>[!NOTE]
>
>Before you call `s.t()`, you must clear any values on the s object that you do not want to persist. if you are using [!DNL AppMeasurement] for JavaScript, you can call `s.clearVars()`. Si vous utilisez du code H, écrivez une routine simple afin de définir les variables sur une chaîne vide.

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

The following example shows a tracking call in the `done` callback of the JQuery `.ajax` function:

```
$.ajax({ 
  url: "test.html", 
  dataType: "html" 
}) 
  .done(function( response ) { 
    $( "#content" ).html( response ); 
  s.clearVars(); 
  s.pageName = $( "h1:first" ).text(); 
  s.t(); 
  }); 
```

Si une demande d’image a été précédemment effectuée sur la même page, effacez les valeurs des variables précédemment définies. Pour ce faire :

* Ecrivez une fonction JavaScript simple pour effacer les variables Adobe.
* Définissez les variables *`linkTrackVars`* et *`linkTrackEvents`* les variables si vous ne l'avez pas déjà fait dans [!DNL s_code.js] le fichier.

* Set the values appropriate for the changed content, namely the *`pageName`* variable.
* After the variables are set, call the *`tl()`* function.

```js
//set linkTrackVars and linkTrackEvents> (if applicable) 
//set new variables 
s.tl(this,'o','Link Name');
```

```js
s.linkTrackVars="prop1,eVar1,events"; s.linkTrackEvents="event1"; 
s.prop1="some value"; s.eVar1="another value"; s.events="event1"; 
s.tl(this,'o','My Link Name');
```

