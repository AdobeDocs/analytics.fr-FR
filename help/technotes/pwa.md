---
title: PWA pour Analytics
description: Applications web progressives pour Adobe Analytics
role: User, Admin
feature: Progressive Web Apps
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
TQID: 'https://experienceleague.adobe.com/IKf2D1AqfbD6qurNczyJWaZIOzQyOTURfJFSJNDucnU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b9fe5dd8-e052-4fb5-86db-a5f6ced5bbb8
    internal-label: Progressive web apps
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 100%
---
# PWA pour Adobe Analytics

Cette page décrit comment utiliser Adobe Analytics avec les applications web progressives (PWA).

## Introduction

Les PWA peuvent apporter une expérience d’application native ainsi que des fonctionnalités hors ligne pour un site web. En règle générale, les PWA incluent un service worker, le provisionnement du cache ainsi qu’un fichier de manifeste, qui peuvent tous contribuer à des temps de chargement plus rapides, une navigation plus facile et un comportement en responsive design.

Adobe Analytics fonctionne de manière aussi transparente avec les PWA qu’avec les sites Web traditionnels. Bien que les PWA aient quelques exigences supplémentaires pour se comporter de manière progressive en elles-mêmes, elles ne créent aucune barrière ni limitation quant à la façon dont Analytics collecte ou restitue les données, par rapport aux sites web traditionnels. En fait, étant donné qu’Analytics inclut déjà des fonctionnalités de suivi hors ligne, les PWA peuvent vous aider à tirer profit de cette fonctionnalité intégrée plus facilement qu’avec les sites web traditionnels.

## Obtenez vos données Analytics pour les PWA

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

Pour plus d’informations sur la configuration du fichier AppMeasurement.js, consultez [Présentation des variables de configuration](/help/implement/vars/config-vars/configuration-variables.md) ainsi que les pages spécifiques aux variables dans le même sous-chapitre.

Pour plus d’informations sur les caractéristiques du fichier AppMeasurement.js, consultez la section [Aperçu de l’implémentation de JavaScript](/help/implement/js/overview.md).
