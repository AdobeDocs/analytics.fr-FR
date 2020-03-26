---
title: PWA pour Analytics
description: Applications Web progressives pour Adobe Analytics
translation-type: tm+mt
source-git-commit: b36505c9fd7bf1d2da4d076d6b49298f01ad1cfc

---


# PWA pour Analytics

Cette page décrit l’utilisation d’Adobe Analytics avec des applications Web progressives (PWA).

## Introduction

Les PWA peuvent fournir une expérience applicative native, ainsi que des fonctionnalités hors ligne, pour un site Web. En règle générale, les PWA comprennent un agent de service, des dispositions de mise en cache et un fichier manifeste, qui peuvent tous aider à accélérer le temps de chargement, à faciliter la navigation et à adopter un comportement réactif.

Adobe Analytics fonctionne de manière aussi transparente avec les approches PWA qu’avec les sites Web traditionnels. Bien que les AAP aient quelques exigences supplémentaires pour se comporter progressivement en elles-mêmes, elles ne créent pas d’obstacles ou de limitations quant à la manière dont Analytics les rassemble ou leur rapporte des données d’une manière différente de celle des sites Web traditionnels. En fait, étant donné qu’Analytics inclut déjà des fonctionnalités de suivi hors ligne, les approches PWA peuvent vous aider à tirer parti de cette fonctionnalité intégrée plus facilement qu’avec les sites Web traditionnels.

## Obtention des données Analytics PWA

Pour collecter et analyser vos données PWA avec Analytics, il n’est pas nécessaire d’effectuer des modifications de configuration. Analytics fournit automatiquement toutes les mêmes fonctionnalités et fonctionnalités qu’un site Web traditionnel.

## Ajouter le suivi hors ligne pour accroître l&#39;efficacité des approches PWA

Vous pouvez accroître l’efficacité de votre approche par domaine en utilisant les fonctionnalités [de suivi](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) hors ligne d’Analytics avec. Par défaut, cette fonctionnalité est désactivée, mais vous pouvez ajouter la propriété suivante au fichier AppMeasurement.js pour l’activer : `s.trackOffline=true;`.

Par exemple, dans le fichier AppMeasurement.js suivant, la propriété est ajoutée à la fin de la `CONFIG SECTION`:

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

Pour plus d’informations sur la modification du fichier AppMeasurement.js, voir [Insertion de code dans le fichier AppMeasurement.js](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html).

Pour des exemples de configurations dans le fichier AppMeasurement.js, voir [Configuration du fichier](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7)AppMeasurement.js.

Pour plus d’informations sur les caractéristiques du fichier AppMeasurement.js, voir la présentation [de l’implémentation de](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)JavaScript.
