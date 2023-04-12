---
title: Présentation des ensembles de classifications
description: Utilisez les ensembles de classifications pour gérer les données de classification.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 100%

---

# Présentation des ensembles de classifications

Les ensembles de classifications fournissent une interface unique pour gérer les classifications et les règles. Ce workflow associe le concept de création de classifications dans les paramètres de la suite de rapports au concept de l’importateur de classifications afin de fournir une interface plus intuitive pour créer et gérer les données de classification.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]**

L’architecture backend publiée avec les jeux de classifications contient plusieurs améliorations notables :

* Réduction significative du temps de traitement (72 heures → 24 heures)
* Possibilité d’utiliser l’interface utilisateur des jeux de classifications
* L’option d’utiliser des données de classification dans Adobe Experience Platform à l’avenir via le [connecteur source Adobe Analytics pour les données de classification](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

L’architecture backend publiée avec les jeux de classifications contient également plusieurs modifications notables :

* Lors de l’utilisation du navigateur ou de l’importation FTP, « [!UICONTROL Remplacer en cas de conflit] » est toujours activé.
* Lors de l’utilisation du navigateur ou de l’importation FTP, l’option permettant d’exporter immédiatement après l’importation n’est plus prise en charge. Les exportations doivent être lancées séparément.
* Le point d’entrée API Analytics 2.0 `GetDimensions` renvoie désormais des identifiants de chaîne pour les classifications au lieu des identifiants numériques. Les identifiants numériques peuvent toujours être utilisés, mais Adobe recommande d’utiliser les nouveaux identifiants de chaîne si possible. Les identifiants numériques peuvent être récupérés à l’aide du paramètre de chaîne de requête `?expansion=hidden`.


Les ensembles de classifications se composent de deux zones principales :

* [**[!UICONTROL Gestionnaire des ensembles de classifications]**](set-manager.md) : créez, modifiez et supprimez des ensembles de classifications.
* [**[!UICONTROL Gestionnaire des tâches des ensembles de classifications]**](job-manager.md) : affichez le statut des tâches des ensembles de classifications et téléchargez les fichiers d’exportation.
