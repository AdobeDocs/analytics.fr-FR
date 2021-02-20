---
title: FAQ sur Report Builder
description: Questions fréquentes pour le Report Builder.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 1%

---


# FAQ sur Report Builder

Questions fréquentes au Report Builder.

## Puis-je utiliser la fonction `TODAY()` ou `DATERANGE()` dans les classeurs ?

La fonction [`TODAY()`](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) dans Excel renvoie le jour en cours. La fonction [`DATEVALUE()`](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) convertit une chaîne de date en valeur série. Bien qu&#39;il soit utile pour de nombreuses fonctionnalités dans Excel, l&#39;Adobe recommande vivement de ne pas utiliser ces fonctions dans le cadre des demandes Reports Builder planifiées. Le service à la clientèle d’Adobe ne prend pas en charge les demandes de dépannage utilisant l’une ou l’autre de ces fonctions.

Les rapports planifiés sont traités sur des serveurs qui ne partagent probablement pas de fuseaux horaires en tant que suite de rapports. Le `TODAY()` attendu par un utilisateur et le `TODAY()` utilisé par le serveur de traitement peuvent souvent être différents. En outre, la date utilisée dépend du moment où les débuts de traitement sont traités. Si de nombreux rapports sont exécutés simultanément, la date peut changer entre le moment où elle est demandée et celui où elle début le traitement en raison de retards. Ce problème est présent si l’heure planifiée est proche de minuit.

Les rapports planifiés sont également traités sur des serveurs qui ne partagent probablement pas la syntaxe de date. Par exemple, `7/1/YYYY` peut se référer au 1er juillet ou au 7 janvier selon votre pays ou votre région. L&#39;utilisation de la fonction `DATEVALUE()` à cette date entraînerait des valeurs de série différentes selon l&#39;ordinateur qui l&#39;exécute.

Au lieu d&#39;utiliser ces fonctions Excel, l&#39;Adobe recommande vivement d&#39;utiliser des plages de dates dans les demandes de Report Builder. Sur la première page de l’assistant de requête, sélectionnez **[!UICONTROL Préconfigurer les dates]** dans la liste déroulante, puis sous Dates courantes, sélectionnez **[!UICONTROL Aujourd’hui]** ou une autre plage de dates souhaitée. Ce paramètre prend le temps de la suite de rapports au moment de son exécution et non celui du serveur qui traite la requête.

## Quelle taille et quelle complexité puis-je faire mes classeurs ?

Report Builder prend en charge les classeurs jusqu’aux limites suivantes :

* **1 000 demandes** : Un classeur peut contenir jusqu’à 1 000 requêtes de données dans un seul classeur. Si vous disposez de rapports ou de projets nécessitant plus de 1 000 requêtes, l’Adobe vous recommande de les séparer en plusieurs classeurs.
* **20 000 demandes par heure par société** : Report Builder utilise l’API du rapports Analytics pour récupérer les données. Chaque requête individuelle utilise un appel d’API chaque fois qu’il est créé ou actualisé. Si votre entreprise accumule plus de 20 000 appels d’API en une heure donnée, vous devez attendre l’heure suivante pour récupérer les données à nouveau.
* **Durée** de traitement de 4 heures : Les rapports planifiés expirent après 4 heures de traitement. Si votre classeur contient de nombreuses requêtes complexes utilisant des jeux de données volumineux, le rapport planifié peut échouer.
