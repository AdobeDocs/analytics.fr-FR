---
title: Vue d’ensemble des jeux de classifications
description: Utilisez les jeux de classifications pour gérer les données de classification.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: ht
source-wordcount: '290'
ht-degree: 100%

---

# Vue d’ensemble des jeux de classifications

Les jeux de classifications fournissent une interface unique pour gérer les classifications et les règles. Ce workflow associe le concept de création de classifications dans les paramètres de la suite de rapports au concept de l’importateur de classifications afin de fournir une interface plus intuitive pour créer et gérer les données de classification.

**[!UICONTROL Composants]** > **[!UICONTROL Jeux de classifications]**

L’architecture backend publiée avec les jeux de classifications contient plusieurs améliorations notables :

* Réduction du temps de traitement (72 heures → 24 heures)
* Possibilité d’utiliser l’interface utilisateur des jeux de classifications
* Option d’utiliser des données de classification dans Adobe Experience Platform à l’avenir via le [connecteur source Adobe Analytics pour les données de classification](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=fr)

L’architecture backend publiée avec les jeux de classifications contient également plusieurs modifications notables :

* Lors de l’utilisation du navigateur ou de l’import automatisé, « [!UICONTROL Remplacer en cas de conflit] » est toujours activé.
* Lors de l’utilisation du navigateur ou de l’import automatisé, l’option permettant d’exporter immédiatement après l’import n’est plus prise en charge. Les exportations doivent être lancées séparément.
* Le point d’entrée API Analytics 2.0 `GetDimensions` renvoie désormais des identifiants de chaîne pour les classifications au lieu des identifiants numériques. Les identifiants numériques peuvent toujours être utilisés, mais Adobe recommande d’utiliser les nouveaux identifiants de chaîne si possible. Les identifiants numériques peuvent être récupérés à l’aide du paramètre de chaîne de requête `?expansion=hidden`.

>[!IMPORTANT]
>
>Les performances des jeux de classifications dépendent principalement du nombre de valeurs de clés uniques qui contiennent des données. Adobe recommande de faire preuve de prudence lorsque vous traitez des variables contenant un grand nombre de valeurs uniques. Cette précaution s’applique tout particulièrement lorsque vous combinez des variables de plusieurs suites de rapports et dimensions dans un seul jeu de classifications.

Les jeux de classifications se composent de trois zones principales :

* [**[!UICONTROL Gestionnaire des jeux de classifications]**](manage/set-manager.md) : créez, modifiez et supprimez des jeux de classifications.
* [**[!UICONTROL Gestionnaire des traitements des jeux de classifications]**](job-manager.md) : affichez le statut des traitements des jeux de classifications et téléchargez les fichiers d’export.
* [**[!UICONTROL Consolidations des jeux de classifications]**](consolidations/manage.md) : combinez plusieurs jeux de classifications en un seul jeu de classifications.
