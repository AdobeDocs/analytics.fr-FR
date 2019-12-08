---
description: Le module externe getAndPersistValue obtient la valeur de votre choix et l’insère dans une variable Analytics pour une période déterminée. Une utilisation courante consiste à voir combien de consultations de pages sont générées par une campagne après un clic publicitaire, ce qui vous permet d’identifier les pages les plus courantes de chaque campagne.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getAndPersistValue
topic: Developer and implementation
uuid: ddeab80c-260e-44b6-8483-8b8b369ec19b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getAndPersistValue

Le module externe getAndPersistValue obtient la valeur de votre choix et l’insère dans une variable Analytics pour une période déterminée. Une utilisation courante consiste à voir combien de consultations de pages sont générées par une campagne après un clic publicitaire, ce qui vous permet d’identifier les pages les plus courantes de chaque campagne.

>[!IMPORTANT]
>
>Ce module externe n’a pas été validé pour être compatible avec [AppMeasurement pour JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md). Reportez-vous à la section [Prise en charge des modules externes dans AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

Vous pouvez, par exemple, utiliser ce module externe pour définir un code de suivi de campagne à partir de la variable *`campaign`* dans une variable Trafic personnalisé (*`s.prop`*) sur la page vue de chaque visiteur pendant les 30 jours suivants. Cela vous permet de déterminer le nombre de pages vues que le code de suivi a générées à la suite du clic publicitaire initial.

> [!NOTE] Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

## Implémentation et code du module externe {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION** : aucune modification n’est requise pour cette section.

**Plugin Config**

Placez le code suivant dans la fonction *`s_doPlugins()`* située dans la section du fichier *`s_code.js`intitulée* Plugin Config *.* Sélectionnez une variable Trafic personnalisé (s.prop) ou Conversion personnalisée (s.eVar) à utiliser dans le cadre de la capture de données de valeurs persistantes. Il doit s’agir d’une variable que vous avez activée à l’aide d’Admin Console, mais qui, pour l’heure, n’est affectée à aucun autre usage. Vous pouvez utiliser l’exemple suivant et l’adapter en fonction de vos besoins.

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* possède trois arguments :

1. Variable ou valeur actuellement renseignée persistante ( *`s.campaign`* illustrée ci-dessus).
1. Nom du cookie, utilisé pour stocker la valeur (*`s_getval`* illustré ci-dessus).
1. Durée de la persistance, exprimée en jours. Si le paramètre est défini sur « 30 », comme dans l’exemple ci-dessus, la valeur sera renseignée dans la variable sélectionnée sur chaque page vue par l’utilisateur au cours des 30 prochains jours. Par défaut, le paramètre est défini sur la *session*.

**PLUGINS SECTION** : ajoutez le code suivant à la section du fichier [!DNL s_code.js] intitulée PLUGINS SECTION. N’effectuez aucune modification dans cette partie du code du module externe.

```js
/* 
 * Plugin: getAndPersistValue 0.3 - get a value on every page 
 */ 
s.getAndPersistValue=new Function("v","c","e","" 
+"var s=this,a=new Date;e=e?e:0;a.setTime(a.getTime()+e*86400000);if(" 
+"v)s.c_w(c,v,e?a:0);return s.c_r(c);");
```

Les installations de module externe doivent toujours faire l’objet de tests approfondis afin de s’assurer que la collecte des données fonctionne comme prévu avant son déploiement dans un environnement de production.
