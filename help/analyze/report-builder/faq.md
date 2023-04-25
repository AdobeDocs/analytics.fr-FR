---
title: FAQ sur Report Builder
description: Questions fréquentes sur Report Builder
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 93%

---

# FAQ sur Report Builder

Questions fréquentes relatives à Report Builder

## Puis-je utiliser la fonction `TODAY()` ou `DATERANGE()` dans les classeurs ?

Dans Excel, la fonction [`TODAY()`](https://support.microsoft.com/fr-fr/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) renvoie la date du jour. La fonction [`DATEVALUE()`](https://support.microsoft.com/fr-fr/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) convertit une chaîne de date en valeur série. En dépit de leur caractère utile à de nombreuses fonctionnalités dans Excel, Adobe déconseille fortement d’utiliser ces fonctions dans le cadre des requêtes planifiées de Report Builder. L’Assistance clientèle d’Adobe ne prend pas en charge les demandes de dépannage utilisant l’une ou l’autre de ces fonctions.

Les rapports planifiés sont traités sur des serveurs peu susceptibles de partager les mêmes fuseaux horaires que la suite de rapports. Souvent, la valeur `TODAY()` attendue par l’utilisateur et la valeur `TODAY()` utilisée par le serveur de traitement peuvent être différentes. En outre, la date utilisée dépend du moment où démarre le traitement. Si de nombreux rapports sont exécutés simultanément, des retards peuvent entraîner une modification de la date entre le moment où elle est demandée et celui où le traitement démarre. Ce problème se présente si l’heure planifiée est proche de minuit.

Les rapports planifiés sont également traités sur des serveurs peu susceptibles de partager la même syntaxe de date. Par exemple, `7/1/YYYY` peut faire référence au 1er juillet ou au 7 janvier, selon votre pays ou votre région. L’utilisation de la fonction `DATEVALUE()` à cette date entraînerait des valeurs de série différentes en fonction de l’ordinateur sur lequel elle est exécutée.

Plutôt que d’utiliser ces fonctions Excel, Adobe vous recommande vivement d’utiliser des périodes dans vos requêtes Report Builder. Sur la première page de l’assistant de requête, sélectionnez **[!UICONTROL Préconfigurer les dates]** dans la liste déroulante, puis sous Dates courantes, sélectionnez **[!UICONTROL Aujourd&#39;hui]** ou une autre période. Ce paramètre intègre l’heure de la suite de rapports au moment de son exécution et non pas l’heure du serveur qui traite la requête.

## Quelle taille et quelle complexité puis-je donner à mes classeurs ?

Report Builder prend en charge les classeurs jusqu’aux limites suivantes :

* **1 000 demandes** : un seul classeur peut contenir jusquʼà 1 000 demandes de données. Si vous disposez de rapports ou de projets nécessitant plus de 1 000 requêtes, Adobe vous recommande de les séparer pour les incorporer dans plusieurs classeurs.
* **20 000 requêtes par heure pour chaque société** : Report Builder utilise l’API de création de rapports d’Analytics pour récupérer les données. Chaque requête utilise un appel d’API à chaque fois qu’elle est créée ou actualisée. Si votre organisation accumule plus de 20 000 appels d’API en une heure donnée, vous devez attendre l’heure suivante pour récupérer les données à nouveau.
* **Temps de traitement de 4 heures** : les rapports planifiés expirent après plus de 4 heures de traitement. Si votre classeur contient de nombreuses requêtes complexes qui utilisent des jeux de données volumineux, le rapport planifié peut échouer.
