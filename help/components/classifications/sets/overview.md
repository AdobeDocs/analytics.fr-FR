---
title: Présentation des ensembles de classifications
description: Utilisez les ensembles de classifications pour gérer les données de classification.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: 4824170ae2465f3fa04ee588d9571e1cc73d11fc
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 46%

---

# Présentation des ensembles de classifications

Les ensembles de classifications fournissent une interface unique pour gérer les classifications et les règles. Ce workflow associe le concept de création de classifications dans les paramètres de la suite de rapports au concept de l’importateur de classifications afin de fournir une interface plus intuitive pour créer et gérer les données de classification.

**[!UICONTROL Composants]** > **[!UICONTROL Ensembles de classifications]**

>[!NOTE]
>
>Les ensembles de classifications seront disponibles pour tous les clients dont les suites de rapports ont été migrées vers la nouvelle architecture des classifications. Pour plus d’informations, contactez l’Assistance clientèle d’Adobe ou votre gestionnaire de compte.

L’architecture du serveur principal publiée avec les jeux de classifications contient plusieurs améliorations notables :

* Réduction significative du temps de traitement (72 heures → 24 heures)
* Possibilité d’utiliser l’interface utilisateur des jeux de classifications
* L’option permettant d’utiliser des données de classification dans Adobe Experience Platform à l’avenir via le [Connecteur source Adobe Analytics pour les données de classification](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

L’architecture du serveur principal publiée avec les jeux de classifications contient également plusieurs modifications notables :

* Lors de l’utilisation de l’importation du navigateur, &quot;[!UICONTROL Remplacer en cas de conflit]&quot; est toujours activé.
* Lors de l’utilisation de l’importation dans le navigateur, l’option permettant d’exporter immédiatement après l’importation n’est plus prise en charge. Les exportations doivent être lancées séparément.
* API Analytics 2.0 `GetDimensions` Le point de terminaison renvoie désormais des identifiants de chaîne pour les classifications au lieu des identifiants numériques. Les identifiants numériques peuvent toujours être utilisés, mais Adobe recommande d’utiliser les nouveaux identifiants de chaîne si possible. Les identifiants numériques peuvent être récupérés à l’aide de la variable `?expansion=hidden` paramètre de chaîne de requête.


Les ensembles de classifications se composent de deux zones principales :

* [**[!UICONTROL Gestionnaire des ensembles de classifications]**](set-manager.md) : créez, modifiez et supprimez des ensembles de classifications.
* [**[!UICONTROL Gestionnaire des tâches des ensembles de classifications]**](job-manager.md) : affichez le statut des tâches des ensembles de classifications et téléchargez les fichiers d’exportation.
