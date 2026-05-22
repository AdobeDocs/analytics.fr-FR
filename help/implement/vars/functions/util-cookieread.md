---
title: Util.cookieRead
description: Obtient la valeur d’un cookie.
feature: Appmeasurement Implementation
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/puEimpy5b-hdgo186YqHzsgxC-LGKPluxN5mVdxFer4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 184
ht-degree: 72%

---

# Util.cookieRead

Les cookies peuvent stocker et récupérer des informations sur plusieurs pages du même domaine. Utilisez la méthode `Util.cookieRead()` pour récupérer une valeur d’un cookie.

## Lire les cookies à l’aide des extensions Adobe Analytics et Web SDK

Vous pouvez lire les cookies en définissant des valeurs dans les éléments de données.

1. Connectez-vous à [la collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise de votre choix.
3. Accédez à l’onglet [!UICONTROL Éléments de données], puis cliquez sur l’élément de données souhaité (ou créez un élément de données).
4. Définissez la liste déroulante [!UICONTROL Extension] sur **[!UICONTROL Core]** et le [!UICONTROL Type d’élément de données] sur **[!UICONTROL Cookie]**.
5. Entrez le nom du cookie dans le champ de texte.

La valeur du cookie est stockée dans l’élément de données. Vous pouvez ensuite référencer l’élément de données dans les règles pour affecter les variables souhaitées.

## s.Util.cookieRead() dans AppMeasurement et l’éditeur de code personnalisé de l’extension Analytics

Appelez la méthode `s.Util.cookieRead()` pour lire une valeur de cookie. Son seul argument est une chaîne obligatoire. Cette méthode renvoie une chaîne contenant la valeur du cookie. Si les cookies n’existent pas, une chaîne vide est renvoyée.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
