---
title: account
description: Utilisez la variable de compte pour déterminer la suite de rapports à laquelle les données sont envoyées.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 100%

---


# account

>[!IMPORTANT]
>
>Cette variable a été abandonnée. Utilisez la fonction [`s.sa()`](../functions/sa-method.md) si votre mise en œuvre nécessite de modifier la destination de la suite de rapports.

Dans les versions précédentes d’Adobe Analytics, la variable `account` déterminait la suite de rapports à laquelle vous souhaitiez envoyer des données. Un identifiant de suite de rapports est nécessaire pour envoyer des données à Adobe Analytics.

* Si vous utilisez Adobe Experience Platform Launch, les suites de rapports résident sous l’accordéon [!UICONTROL Gestion des bibliothèques] lors de la configuration de l’extension Adobe Analytics.
* Si vous utilisez la fonction [`s_gi()`](../functions/s-gi.md) pour instancier un objet de suivi Analytics, les identifiants de suite de rapports existent déjà en tant qu’argument obligatoire dans la fonction.
