---
title: Fonctions et méthodes
description: Découvrez comment utiliser les fonctions et méthodes proposées par Adobe dans votre mise en œuvre.
feature: Appmeasurement Implementation
exl-id: 9ef5bd92-fae1-4fe4-90ea-c735e8ff4b9c
role: Admin, Developer
TQID: https://experienceleague.adobe.com/dKPvTPeRa7-SIFyIDU-7Mlob-3jsrfvhWmKeAveHGEc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: c8add8f2-4250-4fd9-9cde-9707036c567did: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 100%

---

# Fonctions et méthodes

Adobe offre plusieurs fonctions et méthodes que vous pouvez utiliser dans votre implémentation. Lorsque vous référencez ces fonctions ou méthodes, elles effectuent des tâches courantes avec une seule ligne de code.

Certaines de ces lignes de code uniques appartiennent aux catégories suivantes :

* **Suivi des appels** : Les méthodes les plus courantes et essentielles dans de nombreuses implémentations. Elles incluent les méthodes [`t()`](t-method.md) et [`tl()`](tl-method.md).
* **Utilitaires AppMeasurement** : Dans les versions précédentes d’AppMeasurement, les implémentations devaient écrire leur propre code pour exécuter ces tâches. Adobe fournit ces méthodes d’utilitaire pour rationaliser ces tâches courantes. Les utilitaires AppMeasurement incluent [`Util.cookieRead()`](util-cookieread.md), [`Util.cookieWrite()`](util-cookiewrite.md) et [`Util.getQueryParam()`](util-getqueryparam.md).
* **Enregistrement des fonctions** : Vous pouvez créer vos propres fonctions et faire en sorte qu’AppMeasurement les exécute automatiquement avant ou après l’envoi d’un appel de suivi à Adobe. Les variables qui tombent dans cette catégorie sont [`doPlugins()`](doplugins.md), [`registerPreTrackCallback()`](registerpretrackcallback.md) et [`registerPostTrackCallback()`](registerposttrackcallback.md).
