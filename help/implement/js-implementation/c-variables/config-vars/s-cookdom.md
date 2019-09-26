---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieDomain

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Généralement, `s.cookieDomainPeriods` est utilisé pour générer `s.cookieDomain` à partir de `window.location.hostname`.  Au lieu d’utiliser `s.cookieDomainPeriods`, vous pouvez définir explicitement `s.cookieDomain` ce que vous souhaitez utiliser dans votre implémentation. Par exemple, vous pourriez définir des cookies au nom complet de la page en utilisant :

`s.cookieDomain = window.location.hostname;`
