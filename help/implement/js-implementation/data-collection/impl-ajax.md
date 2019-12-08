---
description: Procéder à une implémentation à l’aide d'AJAX est tout comme déployer du code sur une page HTML standard.
keywords: Analytics Implementation
title: Mise en œuvre à l’aide d’AJAX
topic: Developer and implementation
uuid: 9e3477ef-7dea-4c76-ab61-36a188222be7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Mise en œuvre à l’aide d’AJAX

Procéder à une implémentation à l’aide d’AJAX est tout comme déployer du code sur une page HTML standard.

L’entreprise souhaite obtenir des réponses à ses questions. Les besoins sont évalués, et les variables sont affectées. La conception est ensuite appliquée et déployée. Ces concepts doivent vous être familiers si vous avez déjà procédé aux étapes initiales de l’implémentation.

## Conception de la solution {#section_78F1C7AFBB4E4175A6FE04A962C9C9D0}

[!UICONTROL AJAX] demande tout d’abord que vous déterminiez le niveau d’informations détaillées à rassembler. La modification du contenu de la page (microniveau) ou le suivi des attributs de l’application (microniveau) détermine les variables à définir et la méthode d’envoi des données à Adobe la plus adaptée.

## Déploiement du code {#section_F3FC6F07A3E148D89A4C9ABC442920C3}

Le code JavaScript contient deux fonctions qui permettent d’envoyer des données. Vous devez suivre des instructions distinctes pour déterminer quelle méthode doit être utilisée pour envoyer des données.
Si une demande d’image a été précédemment effectuée sur la même page, vous devez d’abord effacer les valeurs des variables précédemment définies. Utilisez la fonction `clearVars()` d’[!DNL AppMeasurement] pour JavaScript ou écrivez une fonction JavaScript simple pour effacer les variables si vous utilisez le code H. Définissez les valeurs appropriées pour le contenu modifié, à savoir la variable *`pageName`*. Une fois les variables définies, appelez la fonction *`t()`*.

> [!NOTE] Avant d’appeler `s.t()`, vous devez effacer toute valeur de l’objet s qui ne doit pas persister. Si vous utilisez [!DNL AppMeasurement] pour JavaScript, vous pouvez appeler `s.clearVars()`. Si vous utilisez du code H, écrivez une routine simple afin de définir les variables sur une chaîne vide.

```js
s.clearVars(); 
s.pageName="New Page" 
s.prop1="some value" 
void(s.t());
```

L’exemple suivant illustre un appel de suivi dans le rappel `done` de la fonction `.ajax` de JQuery :

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
* Définissez les variables *`linkTrackVars`* et *`linkTrackEvents`* dans le fichier [!DNL s_code.js], le cas échéant.

* Définissez les valeurs appropriées pour le contenu modifié, à savoir la variable *`pageName`*.
* Une fois les variables définies, appelez la fonction *`tl()`*.

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

