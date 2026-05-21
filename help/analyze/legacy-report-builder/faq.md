---
description: Découvrez les questions fréquentes relatives à Report Builder.
title: FAQ sur Report Builder
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
TQID: https://experienceleague.adobe.com/vFQWGX3ojl070mQIg7GXhY87kxC-7d0dlYl-0rFU9Uk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 100%

---

# FAQ sur Report Builder

{{legacy-arb}}

Questions fréquentes relatives à Report Builder

## Puis-je utiliser la fonction `TODAY()` ou `DATERANGE()` dans les classeurs ? {#today}

Dans Excel, la fonction [`TODAY()`](https://support.microsoft.com/fr-fr/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) renvoie la date du jour. La fonction [`DATEVALUE()`](https://support.microsoft.com/fr-fr/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) convertit une chaîne de date en valeur série. En dépit de leur caractère utile à de nombreuses fonctionnalités dans Excel, Adobe déconseille fortement d’utiliser ces fonctions dans le cadre des requêtes planifiées de Report Builder. L’Assistance clientèle d’Adobe ne prend pas en charge les demandes de dépannage utilisant l’une ou l’autre de ces fonctions.

Les rapports planifiés sont traités sur des serveurs peu susceptibles de partager les mêmes fuseaux horaires que la suite de rapports. Souvent, la valeur `TODAY()` attendue par l’utilisateur et la valeur `TODAY()` utilisée par le serveur de traitement peuvent être différentes. En outre, la date utilisée dépend du moment où démarre le traitement. Si de nombreux rapports sont exécutés simultanément, des retards peuvent entraîner une modification de la date entre le moment où elle est demandée et celui où le traitement démarre. Ce problème se présente si l’heure planifiée est proche de minuit.

Les rapports planifiés sont également traités sur des serveurs peu susceptibles de partager la même syntaxe de date. Par exemple, `7/1/YYYY` peut faire référence au 1er juillet ou au 7 janvier, selon votre pays ou votre région. L’utilisation de la fonction `DATEVALUE()` à cette date entraînerait des valeurs de série différentes en fonction de l’ordinateur sur lequel elle est exécutée.

Plutôt que d’utiliser ces fonctions Excel, Adobe vous recommande vivement d’utiliser des périodes dans vos requêtes Report Builder. Sur la première page de l’assistant Requête, sélectionnez **[!UICONTROL Dates prédéfinies]** dans le menu déroulant, puis, sous Dates utilisées, cliquez sur **[!UICONTROL Aujourd’hui]** ou sur une autre période souhaitée. Ce paramètre intègre l’heure de la suite de rapports au moment de son exécution et non pas l’heure du serveur qui traite la requête.

## Quelle taille et quelle complexité puis-je donner à mes classeurs ? {#complexity}

Report Builder prend en charge les classeurs jusqu’aux limites suivantes :

* **1 000 demandes** : un seul classeur peut contenir jusquʼà 1 000 demandes de données. Si vous disposez de rapports ou de projets nécessitant plus de 1 000 requêtes, Adobe vous recommande de les séparer pour les incorporer dans plusieurs classeurs.
* **20 000 requêtes par heure pour chaque société** : Report Builder utilise l’API de création de rapports d’Analytics pour récupérer les données. Chaque requête utilise un appel d’API à chaque fois qu’elle est créée ou actualisée. Si votre organisation accumule plus de 20 000 appels d’API en une heure donnée, vous devez attendre l’heure suivante pour récupérer les données à nouveau.
* **Temps de traitement de 4 heures** : les rapports planifiés expirent après plus de 4 heures de traitement. Si votre classeur contient de nombreuses requêtes complexes qui utilisent des jeux de données volumineux, le rapport planifié peut échouer.

## Comment savoir si j’ai accès à Report Builder ? {#access}

Votre équipe d’administration Adobe Analytics doit vous accorder un accès à Report Builder. L’équipe d’administration configure les profils de produit dans [Adobe Admin Console](/help/admin/admin-console/home.md). Demandez à un administrateur ou une administratrice de vous accorder l’accès.
