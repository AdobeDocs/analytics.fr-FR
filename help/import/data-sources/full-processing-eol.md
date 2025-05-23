---
title: Fin de vie des sources de données à traitement complet
description: En savoir plus sur l’annonce de fin de vie pour les sources de données à traitement complet.
exl-id: 7dd6d518-156f-4bf5-86cb-04d0acc8ff0c
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 4%

---

# Fin de vie des sources de données à traitement complet

Les sources de données à traitement complet ont toujours permis aux entreprises d’envoyer des données au niveau de l’accès à Adobe Analytics. Ces données ont été traitées de la même manière que les données collectées par des moyens traditionnels de collecte de données, tels que l’AppMeasurement. En 2020, Adobe a publié l’[ API d’insertion de données en masse](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/), qui exécute les mêmes fonctions que les sources de données à traitement complet, mais avec des fonctionnalités supplémentaires. Cette page fournit des détails sur les fonctionnalités supplémentaires fournies par l’API d’insertion de données en bloc et décrit les différences dans les formats de fichier.

Le 25 mars 2021, Adobe a empêché la création de nouvelles connexions de sources de données à traitement complet. Le 31 janvier 2022, tous les services de données à traitement complet ont été désactivés.

## Principales différences entre les sources de données à traitement complet et l’API d’insertion de données en bloc

* L’insertion de données en bloc vous permet d’envoyer plusieurs fichiers en vue d’un traitement parallèle. Les groupes de visiteurs assurent la continuité des visiteurs et l’attribution de l’eVar.
* L’insertion de données en bloc comporte des fonctionnalités de validation des données et de gestion des erreurs, ce qui supprime certaines tâches administratives liées à l’envoi de données d’accès.
* L’insertion de données en bloc prend en charge plusieurs méthodes d’identification de l’identifiant visiteur.
* L’insertion de données en bloc comporte des champs obligatoires supplémentaires : une colonne d’identification des visiteurs, un `pageName` (ou équivalent de lien), `reportSuiteID`, `timestamp` et `userAgent`.
* Pour garantir la continuité et l’attribution des visiteurs, l’insertion de données en bloc nécessite le tri chronologique des lignes des fichiers. Voir [Groupes de visiteurs](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/visitor-groups/) pour en savoir plus sur l’ordre de l’activité Visiteur dans les fichiers.
* L’insertion de données en bloc nécessite que les fichiers soient compressés au format .csv au format .gzip.
* BDIA utilise `timestamp` au lieu de `date`.

## Comparaison de variables entre BDIA et sources de données à traitement complet

Les variables suivantes ont été introduites dans l’insertion de données en bloc, auparavant indisponibles dans les sources de données à traitement complet :

* **`aamlh`** : indice d’emplacement Adobe Audience Manager.
* **`contextData.key`** : [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md).
* **`customerID`** : variables du service d’ID Experience Cloud. Inclut `id`, `authState` et `isMCSeed`.
* **`hints`** : [ variables de conseil client](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=fr). Comprend `bitness`, `brands`, `mobile`, `model`, `platform`, `platformversion` et `wow64`.
* **`ipaddress`** : adresse IP du visiteur.
* **`language`** : dimension [Langue](/help/components/dimensions/language.md).
* **`list1`** - **`list3`** : [Variables de liste](/help/implement/vars/page-vars/list.md).
* **`marketingCloudVisitorID`** : identifiant Experience Cloud du visiteur.
* **`tnta`** : charge utile des données Target utilisée dans les intégrations [Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=fr).
* **`trackingServer`** : variable [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md).
* **`transactionID`** : variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md).
* **`userAgent`** : chaîne de l’agent utilisateur de l’appareil.

Les variables suivantes ne sont pas prises en charge par l’insertion de données en bloc :

* **`charSet`** : variable [`charSet`](/help/implement/vars/config-vars/charset.md). L’insertion de données en bloc ne prend en charge que le codage UTF-8.
* **`timezone`** : décalage du fuseau horaire du visiteur par rapport à GMT en heures.
* **`clickAction`**, **`clickActionType`**, **`clickContext`**, **`clickContextType`**, **`clickSourceID`**, **`clickTag`** : variables utilisées dans la collecte de données Activity Map.
