---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieDomain

La variable détermine le domaine sur lequel les cookies [!DNL Analytics] `s_cc` et `s_sq` sont définis.

En général, `s.cookieDomainPeriods` est utilisé pour générer `s.cookieDomain` à partir de `window.location.hostname`. Au lieu d’utiliser `s.cookieDomainPeriods`, vous pouvez définir `s.cookieDomain` explicitement sur ce que vous voulez utiliser dans votre mise en œuvre. Par exemple, vous pourriez définir des cookies au nom complet de la page en utilisant :

`s.cookieDomain = window.location.hostname;`
