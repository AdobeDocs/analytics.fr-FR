---
description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
keywords: Mise en œuvre d’Analytics
seo-description: Les variables dynamiques vous permettent de copier des valeurs d’une variable vers une autre sans entrer les valeurs complètes à plusieurs reprises dans les demandes d’image sur votre site.
solution: null
title: Variables dynamiques
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---



# s.mandatoryLinkTrackingTimeout

Nombre maximal de millisecondes d’attente pour la fin du suivi avant d’exécuter doneAction transmis dans `s.tl`. Cette valeur spécifie la durée d’attente maximale. Si l’appel de suivi de liens se termine avant l’expiration de ce délai, doneAction est exécuté immédiatement. Vous devrez peut-être allonger ce délai si vous constatez que les appels de lien de suivi ne s’exécutent pas.

Valeur par défaut = 250

Exemple : `s.forcedLinkTrackingTimeout = 500`
