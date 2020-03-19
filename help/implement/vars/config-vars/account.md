---
title: account
description: Utilisez la variable de compte pour déterminer la suite de rapports à laquelle les données sont envoyées.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# account

> [!IMPORTANT] Cette variable est retirée. Utilisez la [`s.sa()`](../functions/sa-method.md) fonction si votre implémentation nécessite de modifier la destination de la suite de rapports.

Dans les versions précédentes d’Adobe Analytics, la `account` variable déterminait la suite de rapports à laquelle vous souhaitez envoyer des données. Un identifiant de suite de rapports est nécessaire pour envoyer des données à Adobe Analytics.

* Si vous utilisez Adobe Experience Platform Launch, les suites de rapports résident sous l’ [!UICONTROL Library Management] accordéon lors de la configuration de l’extension Adobe Analytics.
* Si vous utilisez la [`s_gi()`](../functions/s-gi.md) fonction pour instancier un objet de suivi Analytics, les identifiants de suite de rapports existent déjà en tant qu’argument obligatoire dans la fonction.
