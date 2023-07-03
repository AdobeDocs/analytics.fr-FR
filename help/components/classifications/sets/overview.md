---
title: Présentation des jeux de classifications
description: Utilisez des jeux de classifications pour gérer les données de classification.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 26%

---

# Présentation des jeux de classifications

Les jeux de classifications offrent une interface unique pour gérer les classifications et les règles. Ce processus associe le concept de création de classifications dans les paramètres de la suite de rapports au concept de l’importateur de classifications afin de fournir une interface plus intuitive pour créer et gérer les données de classification.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]**

L’architecture du serveur principal publiée avec les jeux de classifications contient plusieurs améliorations notables :

* Réduction du temps de traitement (72 heures → 24 heures)
* La possibilité d’utiliser l’interface utilisateur des jeux de classifications
* L’option d’utiliser des données de classification dans Adobe Experience Platform à l’avenir via le [connecteur source Adobe Analytics pour les données de classification](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=fr)

L’architecture du serveur principal publiée avec les jeux de classifications contient également plusieurs modifications notables :

* Lors de l’utilisation du navigateur ou de l’importation automatisée, &quot;[!UICONTROL Remplacer en cas de conflit]&quot; est toujours activé.
* Lorsque vous utilisez le navigateur ou l’importation automatisée, l’option permettant d’exporter immédiatement après l’importation n’est plus prise en charge. Les exportations doivent être lancées séparément.
* Le point d’entrée API Analytics 2.0 `GetDimensions` renvoie désormais des identifiants de chaîne pour les classifications au lieu des identifiants numériques. Les identifiants numériques peuvent toujours être utilisés, mais Adobe recommande d’utiliser les nouveaux identifiants de chaîne si possible. Les identifiants numériques peuvent être récupérés à l’aide du paramètre de chaîne de requête `?expansion=hidden`.

>[!IMPORTANT]
>
>Les performances des jeux de classifications dépendent principalement du nombre de valeurs de clé uniques qui contiennent des données. Adobe recommande d’être prudent lorsque vous traitez de variables contenant un grand nombre de valeurs uniques. Cette précaution s’applique tout particulièrement lorsque vous combinez des variables de plusieurs suites de rapports et dimensions dans un seul jeu de classifications.

Les ensembles de classifications se composent de trois zones principales :

* [**[!UICONTROL Gestionnaire de jeux de classifications]**](manage/set-manager.md): Créez, modifiez et supprimez des jeux de classifications.
* [**[!UICONTROL Gestionnaire des tâches de jeux de classifications]**](job-manager.md): Affichez l’état des tâches de jeu de classifications et téléchargez les fichiers d’exportation.
* [**[!UICONTROL Consolidation des ensembles de classifications]**](consolidations/manage.md): Combinez plusieurs jeux de classifications en un seul jeu de classifications.
