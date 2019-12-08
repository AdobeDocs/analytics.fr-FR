---
description: Récupère le temps de chargement de la page, en dixièmes de seconde, et vous permet de stocker la valeur dans une prop, une eVar et/ou un événement numérique.
keywords: Analytics Implementation
title: getLoadTime
topic: Developer and implementation
uuid: 5d26a69b-cbde-4be1-bac1-5ee8a4e55ca3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getLoadTime

Récupère le temps de chargement de la page, en dixièmes de seconde, et vous permet de stocker la valeur dans une prop, une eVar et/ou un événement numérique.

Pour utiliser ce module externe, insérez le code de fonction, puis appelez la fonction à deux reprises dans votre fichier [!DNL s_code.js] : une fois au début du fichier et une autre fois dans la section `doPlugins`. Ce module externe est délibérément non défini comme méthode de l’objet s. Sa définition aurait entraîné une augmentation du temps de chargement des pages calculé.

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

## Implémentation et code du module externe {#section_968AC379C3004C359A85AFED5A48D5AE}

**Ajouter la fonction**

Ajoutez la définition suivante de la fonction `s_getLoadTime` dans le fichier [!DNL s_code.js], n’importe où avant la section « DO NOT ALTER ANYTHING BELOW THIS LINE » :

```js
function s_getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

**Effectuer l’appel de fonction initial**

Ajoutez un appel à `s_getLoadTime()` à proximité du début du fichier [!DNL s_code.js], en dehors de toute fonction.

**Effectuer l’appel de fonction final**

Ajoutez un autre appel à `s_getLoadTime()` dans la fonction `s_doPlugins()`, en enregistrant la valeur renvoyée dans une prop, une eVar et/ou un événement numérique.

Exemple d’utilisation 1 – Enregistrement du temps de chargement des pages dans prop10 et eVar20 :

```js
s.eVar20=s.prop10=s_getLoadTime();
```

Exemple d’utilisation 2 – Enregistrement du temps de chargement des pages dans l’événement numérique event99 :

```js
if(s_getLoadTime())s.events=s.apl(s.events,'event90='+s_getLoadTime(),',',1);
```

**(Facultatif) Ajout de la prise en charge des navigateurs plus anciens**

Pour la prise en charge des navigateurs plus anciens qui ne proposent pas la propriété [window.performance.timing](https://www.html5rocks.com/en/tutorials/webperformance/basics/), vous devez inclure la ligne suivante dans la section HEAD du code HTML de la page, près du début et avant d’appeler des fichiers .js, .css ou autres :

```
<script type="text/javascript">var inHeadTS=(new Date()).getTime();</script>
```

