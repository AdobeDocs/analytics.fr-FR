---
title: account
description: Utilisez la variable de compte pour déterminer la suite de rapports à laquelle les données sont envoyées.
translation-type: tm+mt
source-git-commit: f179292abae9cf7986d61da89a86e3e88111943e

---


# account

> [!IMPORTANT] Cette variable est retirée. Utilisez la [`s.sa()`](../functions/sa-method.md) fonction si votre implémentation nécessite de modifier la destination de la suite de rapports.

Dans les versions précédentes d’Adobe Analytics, la `account` variable déterminait la suite de rapports à laquelle vous souhaitez envoyer des données. Un identifiant de suite de rapports est nécessaire pour envoyer des données à Adobe Analytics.

* Si vous utilisez Adobe Experience Platform Launch, les suites de rapports résident sous l’accordéon Gestion des  bibliothèques lors de la configuration de l’extension Adobe Analytics.
* Si vous utilisez la `s_gi()` fonction pour instancier un objet de suivi Analytics, les identifiants de suite de rapports existent déjà en tant qu’argument obligatoire dans la fonction.
