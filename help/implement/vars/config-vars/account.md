---
title: account
description: (Retiré) Déterminez la suite de rapports vers laquelle les données sont envoyées.
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
TQID: https://experienceleague.adobe.com/TmNxbAFJXxEnMJZNNZKP1ldkmeYICEzKdNoptNChzko
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 131
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
