---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Analytics Implementation
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 0c7093518933a88c5057ba95cb3564d6ca0ebcad

---



# s.mandatoryLinkTrackingTimeout

Cette valeur spécifie la durée d’attente maximale. Specifically, it sets the maximum number of milliseconds to wait for tracking to finish before performing the `doneAction` that was passed into `s.tl`. Si l’appel de suivi de liens se termine avant l’expiration de ce délai, `doneAction` est exécuté immédiatement. Vous devrez peut-être allonger ce délai si vous constatez que les appels de lien de suivi ne s’exécutent pas.

Valeur par défaut = 250

Exemple : `s.forcedLinkTrackingTimeout = 500`
