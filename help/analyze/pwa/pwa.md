---
title: PWA pour Analytics
description: Applications web progressives pour Adobe Analytics
role: Business Practitioner, Administrator
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
translation-type: tm+mt
source-git-commit: 960274fde798287568ada9e6d8ec96783449dd99
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 88%

---

# PWA pour Adobe Analytics

Cette page décrit comment utiliser Adobe Analytics avec les applications web progressives (PWA).

## Introduction

Les PWA peuvent apporter une expérience d’application native ainsi que des fonctionnalités hors ligne pour un site web. En règle générale, les PWA incluent un service worker, la mise en cache de provisions ainsi qu’un fichier de manifeste qui peuvent tous aider à obtenir des temps de chargement plus rapides, une navigation plus facile et un comportement réactif.

Adobe Analytics fonctionne de manière aussi transparente avec les PWA qu’avec les sites web traditionnels. Bien que les PWA nécessitent quelques exigences supplémentaires pour se comporter de mieux en mieux dans l’absolu, ils ne créent aucune barrière ou limite sur la manière dont Analytics rassemble ou signale les données qu’ils contiennent par rapport aux sites web traditionnels. En fait, étant donné qu’Analytics inclut déjà des fonctionnalités de suivi hors ligne, les PWA peuvent vous aider à tirer profit de cette fonctionnalité intégrée plus facilement qu’avec les sites web traditionnels.

## Obtenez vos données d’analyses PWA

Pour collecter et analyser vos données PWA avec [!UICONTROL Analytics], vous n’avez pas besoin d’apporter de modifications aux configurations. [!UICONTROL Analytics] fournit automatiquement les mêmes fonctionnalités que pour un site web traditionnel.

## Ajouter le suivi hors ligne pour améliorer l’efficacité des PWA

Vous pouvez augmenter l’efficacité de vos PWA en utilisant les [fonctionnalités de suivi hors ligne](/help/implement/vars/config-vars/trackoffline.md) d’Adobe Analytics. Cette fonctionnalité est désactivée par défaut, mais vous pouvez ajouter la propriété suivante au fichier AppMeasurement.js pour l’activer : `s.trackOffline=true;`.

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

Pour plus d’informations sur la modification du fichier AppMeasurement.js, voir [Insertion du code AppMeasurement de base](/help/implement/other/dtm/c-aa-tool/t-appmeasurement-code.md).

Pour plus d’informations sur la configuration du fichier AppMeasurement.js, voir [Présentation des variables de configuration](/help/implement/vars/config-vars/configuration-variables.md) et les pages spécifiques aux variables individuelles dans le même sous-chapitre.

Pour plus d’informations sur les caractéristiques du fichier AppMeasurement.js, consultez la section [Aperçu de l’implémentation de JavaScript](/help/implement/js/overview.md).
