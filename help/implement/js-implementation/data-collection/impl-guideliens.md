---
description: Si vous suivez ces instructions, les mêmes domaines de cookie sont utilisés, ce qui permet de suivre les visites entre différents types d’implémentation.
keywords: Mise en œuvre d’Analytics
seo-description: Si vous suivez ces instructions, les mêmes domaines de cookie sont utilisés, ce qui permet de suivre les visites entre différents types d’implémentation.
seo-title: Instructions relatives à la mise en œuvre
solution: Analytics
title: Instructions relatives à la mise en œuvre
topic: Développeur et mise en œuvre
uuid: 2917 f 4 af -19 bd -4666-ae 4 b -056 e 7 e 33 f 642
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Instructions relatives à la mise en œuvre

Si vous suivez ces instructions, les mêmes domaines de cookie sont utilisés, ce qui permet de suivre les visites entre différents types d’implémentation.

* **RSID** : [!UICONTROL identifiant de la suite de rapports]
* **VNS** : espace de noms du visiteur, sous-domaine de [!DNL 2o7.net] ou [!DNL omtrdc.net] utilisé pour stocker le cookie [!UICONTROL identifiant visiteur]
* **COOKIEDOMAIN :** votre VNS + trackingServer. Ces domaines peuvent varier sensiblement en fonction de la configuration RDC et du centre de données. [Contactez le service d'assistance](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics) clientèle si vous n'êtes pas sûr de votre domaine de collecte de données.

## Javascript

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## AppMeasurement

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## Demande d'image codée en dur

```javascript
<img border="0" alt="" src="https://VNS.COOKIEDOMAIN.net/b/ss/RSID/5?ns=VNS" width="1" height="1" /> 

<!-- Note that the visitor namespace is defined twice in hardcoded image requests; once in the http subdomain, and another using the ns= query string parameter! -->
```

Si vous utilisez une implémentation de cookies propriétaires, `VNS.COOKIEDOMAIN.net` peut être remplacé par le domaine de cookies propriétaires utilisé. Par exemple, des cookies propriétaires sur `adobe.com` sont remplacés par un élément semblable à `metrics.adobe.com`.
