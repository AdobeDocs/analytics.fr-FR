---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.cookieDomain

La variable détermine le domaine sur lequel les cookies [!DNL Analytics] `s_cc` et `s_sq` sont définis.

En général, `s.cookieDomainPeriods` est utilisé pour générer `s.cookieDomain` à partir de `window.location.hostname`. Au lieu d’utiliser `s.cookieDomainPeriods`, vous pouvez définir `s.cookieDomain` explicitement sur ce que vous voulez utiliser dans votre mise en œuvre. Par exemple, vous pourriez définir des cookies au nom complet de la page en utilisant :

`s.cookieDomain = window.location.hostname;`
