---
title: Pwas pour Analytics
seo-title: Pwas pour Analytics
description: Applications Web progressives pour Adobe Analytics
seo-description: Utilisation de pwas avec Analytics
translation-type: tm+mt
source-git-commit: f64e5d9977bebd0e9db4af0f7118e9e64978c1c7

---


# Pwas pour Analytics

Ce guide décrit l'utilisation d'Adobe Analytics avec les applications Web progressive (pwas).

## Introduction

Le pwas peut offrir une expérience d'application native, ainsi que des fonctionnalités hors ligne, pour un site Web. En règle générale, pwas inclut un opérateur de service, des dispositions de mise en cache et un fichier de manifeste, ce qui peut accélérer le chargement, la navigation et le comportement réactif.

Adobe Analytics fonctionne de manière identique avec le pdid comme avec les sites Web traditionnels. Bien que la fonction pwas ait quelques autres exigences pour se comporter progressivement, elles ne créent pas d'obstacles ou de limites quant à la manière dont Analytics rassemble ou rapporte les données de celles-ci différemment des sites Web traditionnels. En fait, Analytics intégrant déjà les fonctionnalités de suivi hors ligne, pwas peut vous aider à tirer parti plus facilement de cette fonctionnalité intégrée qu'avec les sites Web traditionnels.

## Obtention des données PWA Analytics

Pour collecter et analyser vos données PWA avec Analytics, vous n'avez pas besoin de modifier les configurations. Analytics fournit automatiquement les mêmes fonctionnalités et fonctionnalités qu'avec un site Web traditionnel.

## Ajout du suivi hors ligne pour augmenter l'efficacité PWA

Vous pouvez accroître l'efficacité de votre PWA à l'aide des fonctionnalités de suivi [hors ligne d'Analytics](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) . Par défaut, cette fonctionnalité est désactivée, mais vous pouvez ajouter la propriété suivante au fichier appmeasurement. js pour l'activer : `s.trackOffline=true;`.

Par exemple, dans le fichier appmeasurement. js suivant, la propriété est ajoutée à la fin de :`CONFIG SECTION`

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.trackOffline=true
***
    
```


Pour plus d'informations sur la modification du fichier appmeasurement. js, voir [Insertion de code dans le fichier appmeasurement. js](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html).

Pour obtenir des exemples de configurations dans le fichier appmeasurement. js, voir [Configuration du fichier appmeasurement. js](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7).

Pour plus d'informations sur les caractéristiques du fichier appmeasurement. js, voir Présentation de l'implémentation [Javascript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).
