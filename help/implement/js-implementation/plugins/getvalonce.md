---
description: Le module externe getValOnce empêche une variable donnée d’être réglée sur une valeur définie précédemment. Il utilise ainsi un cookie pour déterminer la dernière valeur connue d’une variable. Si la valeur actuelle correspond à la valeur du cookie, la variable est remplacée par une chaîne vide avant d’être envoyée aux serveurs de traitement d’Adobe. Ce module externe se révèle particulièrement utile pour éviter l’augmentation excessive des instances de variables de conversion qui survient lorsque les utilisateurs actualisent la page ou cliquent sur le bouton Précédent.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getValOnce.
topic: Developer and implementation
uuid: 82fe0da5-3bc4-4632-8c62-7b5683f6b587
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getValOnce.

Le module externe getValOnce empêche une variable donnée d’être réglée sur une valeur définie précédemment. Il utilise ainsi un cookie pour déterminer la dernière valeur connue d’une variable. Si la valeur actuelle correspond à la valeur du cookie, la variable est remplacée par une chaîne vide avant d’être envoyée aux serveurs de traitement d’Adobe. Ce module externe se révèle particulièrement utile pour éviter l’augmentation excessive des instances de variables de conversion qui survient lorsque les utilisateurs actualisent la page ou cliquent sur le bouton Précédent.

>[!IMPORTANT]
>
>Ce module externe n’a pas été validé pour être compatible avec [AppMeasurement pour JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md). Reportez-vous à la section [Prise en charge des modules externes dans AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

**Paramètres**

```js
s.eVar1=s.getValOnce(variable,cookie,expiration,minute);
```

* **Variable :** variable qui sera vérifiée. Elle correspond généralement à la variable en cours de définition.
* **Cookie :** nom du cookie qui stocke la valeur précédente qui servira d’élément de comparaison. Il peut s’agir de n’importe quelle valeur.
* (Facultatif) **Expiration :** délai d’expiration du cookie, exprimé en jours. Si ce paramètre est omis ou s’il est défini sur 0, l’expiration par défaut correspond à la session du navigateur.
* (Facultatif) **Minute :** si vous définissez ce paramètre sur la valeur de chaîne *`m`*, la valeur d’expiration est exprimée en minutes, et non plus en jours. Si elle n’est pas définie, *`days`* correspond à l’expiration par défaut.

**Propriétés**

* Ce module externe est couramment utilisé sur les variables de conversion. Vous pouvez toutefois l’utiliser sur toute variable [!DNL Analytics].
* Lorsque JavaScript rencontre cette fonction, il compare la valeur définie au contenu stocké dans le cookie. Si la valeur définie diffère de celle du cookie, elle est appliquée. En revanche, si elle est identique à la valeur du cookie, une chaîne vide est renvoyée.
* Le cookie ne peut stocker qu’une seule valeur, ce qui signifie que le module externe ne regarde que la dernière valeur définie.
* Le module externe n’empêche pas toutes les valeurs de définir la variable après sa définition. Il évite simplement que la dernière valeur ne soit définie plusieurs fois de suite.
* Si l’utilisateur final bloque ou refuse les cookies, la valeur initiale est toujours renvoyée.
* Une session de module externe se distingue de la définition d’une session (ou visite) dans [!DNL Analytics]. [!DNL Analytics] met fin à une session après 12 heures d’activité ou 30 minutes d’inactivité. Etant donné que le module externe utilise la définition de session du navigateur, celle-ci prend fin uniquement lorsque l’utilisateur ferme l’onglet ou quitte le navigateur.

   * Si un utilisateur ferme votre page, ouvre un autre onglet et revient sur votre site en moins de 30 minutes, le module externe crée une session, tout en maintenant ouverte la visite [!DNL Analytics].
   * Si un utilisateur laisse la fenêtre du navigateur ouverte sans cliquer sur un lien pendant plus de 30 minutes, la visite [!DNL Analytics] expire, mais la session du navigateur reste ouverte.

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

## Implémentation {#section_177FF7F425B64FFB83CDE15A6ACC8D21}

> [!NOTE]Si votre organisation a recours à des canaux marketing et dispose de règles basées sur `s.campaign`, il est recommandé de ne pas utiliser le module externe getValOnce lors de la définition de la valeur de `s.campaign`. Dans le cas contraire, un mauvais canal pourrait être affecté lors d’un clic publicitaire de campagne secondaire.

Pour implémenter ce module externe, placez le code suivant dans votre fichier [!DNL s_code.js].

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getValOnce_v1.11 
 */ 
s.getValOnce=new Function("v","c","e","t","" 
+"var s=this,a=new Date,v=v?v:'',c=c?c:'s_gvo',e=e?e:0,i=t=='m'?6000" 
+"0:86400000,k=s.c_r(c);if(v){a.setTime(a.getTime()+e*i);s.c_w(c,v,e" 
+"==0?0:a);}return v==k?'':v");
```

Une fois ce code implémenté, définissez la variable de votre choix à l’aide de la fonction *`getValOnce`*. Vous trouverez, ci-dessous, quelques exemples d’implémentation :

**Eviter que la même valeur de campagne ne soit définie si une valeur en double est détectée dans les 30 jours suivant la définition du cookie :** `s.campaign=s.getValOnce(s.campaign,'s_cmp',30);`  **empêche la définition de la même valeur eVar1 si une valeur en double est détectée dans les 30 minutes suivant la définition du cookie :**
`s.eVar1=s.getValOnce(s.eVar1,'s_ev1',30,'m');`  **évite que la même valeur eVar2 ne soit définie plusieurs fois dans la même session de navigateur :**
`s.eVar2=s.getValOnce(s.eVar2,'s_ev2');` **Notes**

* Les installations de module externe doivent toujours faire l’objet de tests approfondis afin de s’assurer que la collecte des données fonctionne comme prévu avant son déploiement dans un environnement de production.
* Assurez-vous de supprimer le cookie ou d’en utiliser un nouveau, les valeurs uniques au cours du test ou les variables ne seront pas envoyées.

