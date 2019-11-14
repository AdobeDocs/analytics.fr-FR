---
description: Avec adobe.com utilisé comme exemple, les implémentations décrites ici référencent le même cookie visid.
keywords: Analytics Implementation
solution: Analytics
title: Exemple de mise en œuvre
topic: Developer and implementation
uuid: 17d8d2b2-2303-495a-b0f9-d8d3c05f3893
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Exemple de mise en œuvre

Avec adobe.com utilisé comme exemple, les implémentations décrites ici référencent le même cookie visid.

**Javascript:**

```js
var s_account="omniturecom" 
s.visitorNamespace="omniture" 
s.trackingServer="omniture.112.2o7.net"
```

**Demande d’image codée en dur:**

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

**Javascript:**

```js
var s_account="omniturecom" 
s.visitorNamespace"omniture" 
s.trackingServer="metrics.omniture.com"
```

**Demande d’image codée en dur:**

```
<img border="0" alt="" src="https://metrics.omniture.com/b/ss/omniturecom/5" width="1" height="1" />
```

**AppMeasurement :**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="metrics.omniture.com";
```

