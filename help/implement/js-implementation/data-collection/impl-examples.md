---
description: Avec adobe.com utilisé comme exemple, les implémentations décrites ici référencent le même cookie visid.
keywords: Mise en œuvre d’Analytics
seo-description: Avec adobe.com utilisé comme exemple, les implémentations décrites ici référencent le même cookie visid.
seo-title: Exemple de mise en œuvre
solution: Analytics
title: Exemple de mise en œuvre
topic: Développeur et mise en œuvre
uuid: 17 d 8 d 2 b 2-2303-495 a-b 0 f 9-d 8 d 3 c 05 f 3893
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Exemple de mise en œuvre

Avec adobe.com utilisé comme exemple, les implémentations décrites ici référencent le même cookie visid.

**Javascript :**

```js
var s_account="omniturecom" 
s.visitorNamespace="omniture" 
s.trackingServer="omniture.112.2o7.net"
```

**Demande d’image codée en dur :**

```
<img border="0" alt="" src="https://omniture.112.2o7.net/b/ss/omniturecom/5?ns=omniture" width="1" height="1" /> 
```

**AppMeasurement :**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="omniture.112.2o7.net";
```

Si des cookies propriétaires sont utilisés :

**Javascript :**

```js
var s_account="omniturecom" 
s.visitorNamespace"omniture" 
s.trackingServer="metrics.omniture.com"
```

**Demande d’image codée en dur :**

```
<img border="0" alt="" src="https://metrics.omniture.com/b/ss/omniturecom/5" width="1" height="1" />
```

**AppMeasurement :**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="metrics.omniture.com";
```

