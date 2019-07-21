---
description: Le module externe getAndPersistValue obtient la valeur de votre choix et l’insère dans une variable Analytics pour une période déterminée. Une utilisation courante consiste à voir combien de consultations de pages sont générées par une campagne après un clic publicitaire, ce qui vous permet d’identifier les pages les plus courantes de chaque campagne.
keywords: Mise en œuvre d’Analytics
seo-description: Le module externe getAndPersistValue obtient la valeur de votre choix et l’insère dans une variable Analytics pour une période déterminée. Une utilisation courante consiste à voir combien de consultations de pages sont générées par une campagne après un clic publicitaire, ce qui vous permet d’identifier les pages les plus courantes de chaque campagne.
seo-title: getAndPersistValue
solution: Analytics
subtopic: Modules externes
title: getAndPersistValue
topic: Développeur et mise en œuvre
uuid: ddeab 80 c -260 e -44 b 6-8483-8 b 8 b 369 ec 19 b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getAndPersistValue

Le module externe getAndPersistValue obtient la valeur de votre choix et l’insère dans une variable Analytics pour une période déterminée. Une utilisation courante consiste à voir combien de consultations de pages sont générées par une campagne après un clic publicitaire, ce qui vous permet d’identifier les pages les plus courantes de chaque campagne.

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).

For example, you might use this plug-in to set a campaign tracking code from the *`campaign`* variable into a Custom Traffic ( *`s.prop`*) variable on each visitor's page view made for the next 30 days. Cela vous permet de déterminer le nombre de pages vues que le code de suivi a générées à la suite du clic publicitaire initial.

>[!NOTE]
>
>Les instructions suivantes vous demandent de modifier le code de collecte de données sur votre site. Cela peut avoir une incidence sur la collecte des données sur votre site. Aussi, cette opération ne doit-elle être réalisée que par un développeur maîtrisant l’utilisation et l’implémentation d’[!DNL Analytics].

## Implémentation et code du module externe {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION** : aucune modification n’est requise pour cette section.

**Plugin Config**

Placez le code suivant dans la fonction *`s_doPlugins()`* qui se trouve dans la section du *`s_code.js`* fichier intitulée *Plugin Config*. Sélectionnez une variable Trafic personnalisé (s.prop) ou Conversion personnalisée (s.eVar) à utiliser dans le cadre de la capture de données de valeurs persistantes. Il doit s’agir d’une variable que vous avez activée à l’aide d’Admin Console, mais qui, pour l’heure, n’est affectée à aucun autre usage. Vous pouvez utiliser l’exemple suivant et l’adapter en fonction de vos besoins.

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* possède trois arguments :

1. Currently populated variable or value to persist ( *`s.campaign`* shown above).
1. Cookie name, used to store the value ( *`s_getval`* shown above).
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

Les installations de plug-in doivent toujours faire l’objet de tests approfondis afin de s’assurer que la collecte des données fonctionne comme prévu avant son déploiement dans un environnement de production.
