---
title: account
description: (Retiré) Déterminez la suite de rapports à laquelle les données sont envoyées.
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 38%

---

# account

>[!IMPORTANT]
>
>Cette variable a été abandonnée. Utilisez la fonction [`s.sa()`](../functions/sa-method.md) si votre mise en œuvre nécessite de modifier la destination de la suite de rapports.

Dans les versions précédentes d’Adobe Analytics, la variable `account` déterminait la suite de rapports à laquelle vous souhaitiez envoyer des données. Un identifiant de suite de rapports est nécessaire pour envoyer des données à Adobe Analytics.

* Si vous utilisez le SDK Web, les suites de rapports se trouvent dans les paramètres du service Adobe Analytics dans la banque de données à laquelle le SDK Web envoie des données.
* Si vous utilisez l’extension Adobe Analytics, les suites de rapports résident sous la variable [!UICONTROL Gestion des bibliothèques] en accordéon lors de la configuration de l’extension Adobe Analytics.
* Si vous utilisez la variable [`s_gi()`](../functions/s-gi.md) pour instancier un objet de suivi Analytics, les identifiants de suite de rapports existent déjà en tant qu’argument obligatoire dans la fonction.
