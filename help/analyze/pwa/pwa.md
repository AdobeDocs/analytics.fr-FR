---
title: PWA pour Analytics
description: Applications web progressives pour Adobe Analytics
translation-type: tm+mt
source-git-commit: b36505c9fd7bf1d2da4d076d6b49298f01ad1cfc

---


# PWA pour Analytics

Cette page décrit l’utilisation d’Adobe Analytics avec des applications Web progressives (PWA).

## Introduction

Les PWA peuvent apporter une expérience d’application native ainsi que des fonctionnalités hors ligne pour un site web. En règle générale, les PWA incluent un service worker, la mise en cache de provisions ainsi qu’un fichier de manifeste qui peuvent tous aider à obtenir des temps de chargement plus rapides, une navigation plus facile et un comportement réactif.

Adobe Analytics fonctionne de manière aussi transparente avec les PWA qu’avec les sites web traditionnels. Bien que les PWA nécessitent quelques exigences supplémentaires pour se comporter de mieux en mieux dans l’absolu, ils ne créent aucune barrière ou limite sur la manière dont Analytics rassemble ou signale les données qu’ils contiennent par rapport aux sites web traditionnels. En fait, étant donné qu’Analytics inclut déjà des fonctionnalités de suivi hors ligne, les approches PWA peuvent vous aider à tirer parti de cette fonctionnalité intégrée plus facilement qu’avec les sites Web traditionnels.

## Obtention des données Analytics PWA

Pour collecter et analyser vos données PWA avec Analytics, vous n’avez pas besoin d’apporter de modifications aux configurations. Analytics fournit automatiquement les mêmes fonctionnalités que pour un site web traditionnel.

## Ajouter le suivi hors ligne pour améliorer l’efficacité des PWA

Vous pouvez augmenter l’efficacité de vos PWA en utilisant les [fonctionnalités de suivi hors ligne](https://docs.adobe.com/content/help/fr-FR/analytics/implementation/vars/functions/forceoffline.translate.html) d’Analytics. Cette fonctionnalité est désactivée par défaut, mais vous pouvez ajouter la propriété suivante au fichier AppMeasurement.js pour l’activer : `s.trackOffline=true;`.

Par exemple, dans le fichier AppMeasurement.js suivant, la propriété est ajoutée à la fin de `CONFIG SECTION` :

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

Pour plus d’informations sur la modification du fichier AppMeasurement.js, consultez la section [Insertion de code dans le fichier AppMeasurement.js](https://docs.adobe.com/content/help/fr-FR/analytics/implementation/other/dtm/analytics-tool/t-appmeasurement-code.translate.html).

Pour obtenir des exemples de configurations dans le fichier AppMeasurement.js, consultez la section [Configuration du fichier AppMeasurement.js](https://docs.adobe.com/content/help/fr-FR/analytics/implementation/js/overview.translate.html#section_042412C29CC249E298F19B2BC2F43CE7).

Pour plus d’informations sur les caractéristiques du fichier AppMeasurement.js, consultez la section [Aperçu de l’implémentation de JavaScript](https://docs.adobe.com/content/help/fr-FR/analytics/implementation/js/migrate-from-hcode.translate.html).
