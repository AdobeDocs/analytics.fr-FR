---
title: account
description: (Retiré) Déterminez la suite de rapports vers laquelle les données sont envoyées.
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 38%

---

# account

>[!IMPORTANT]
>
>Cette variable a été abandonnée. Utilisez la fonction [`s.sa()`](../functions/sa-method.md) si votre mise en œuvre nécessite de modifier la destination de la suite de rapports.

Dans les versions précédentes d’Adobe Analytics, la variable `account` déterminait la suite de rapports à laquelle vous souhaitiez envoyer des données. Un identifiant de suite de rapports est nécessaire pour envoyer des données à Adobe Analytics.

* Si vous utilisez le SDK Web, les suites de rapports se trouvent dans les paramètres du service Adobe Analytics du flux de données auquel le SDK Web envoie des données.
* Si vous utilisez l’extension Adobe Analytics, les suites de rapports résident sous l’accordéon [!UICONTROL Gestion des bibliothèques] lors de la configuration de l’extension Adobe Analytics.
* Si vous utilisez la fonction [`s_gi()`](../functions/s-gi.md) pour instancier un objet de suivi Analytics, le ou les identifiants de suite de rapports existent déjà en tant qu’argument obligatoire dans la fonction.
