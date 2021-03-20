---
title: Fin de vie des sources de données à traitement complet
description: Raisons de la fin de vie et comparaisons entre l’API d’insertion de données en bloc et les sources de données à traitement complet.
translation-type: tm+mt
source-git-commit: 2e077db74b7719f49aec513fc99dad33a4d5b831
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 13%

---


# Fin de vie des sources de données à traitement complet

Depuis plusieurs années, la fonctionnalité Sources de données à traitement complet vous permet d’envoyer des données au niveau de l’accès à Adobe Analytics. Ces données ont été traitées de la même manière que les données collectées via nos bibliothèques JavaScript et notre SDK d’application mobile. En 2020, Adobe a publié l&#39;[API d&#39;insertion de données en bloc](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), qui exécute les mêmes fonctions que les sources de données à traitement complet, mais avec des fonctionnalités supplémentaires. Cette rubrique fournit des détails sur les fonctionnalités supplémentaires fournies par l&#39;API d&#39;insertion de données en bloc et décrit les différences de formats de fichier.

À compter du 25 mars 2021, l’Adobe empêchera la création de nouvelles connexions de sources de données à traitement complet. Les connexions existantes continueront d’être prises en charge jusqu’à ce que le service soit complètement abandonné. La dépréciation aura lieu en 2021, bien qu&#39;une date précise n&#39;ait pas encore été fixée.

## Pourquoi cette fonctionnalité est-elle abandonnée ?

L’API d’insertion de données en bloc (BDIA) fournit des fonctionnalités supplémentaires tout en couvrant tous les cas d’utilisation pris en charge par le traitement complet. Nous pensons que vous serez mieux servi en utilisant l&#39;API d&#39;insertion de données en bloc.

## Principales différences entre les sources de données à traitement complet et l’API d’insertion de données en bloc

* L&#39;insertion de données en bloc permet l&#39;envoi de plusieurs fichiers qui peuvent être traités en parallèle. Vous pouvez utiliser des groupes de Visiteurs pour assurer la continuité du visiteur et l’attribution de l’eVar.
* L&#39;insertion de données en bloc offre des fonctionnalités de validation des données et de gestion des erreurs, ce qui supprime certaines tâches administratives liées à l&#39;envoi de données d&#39;accès.
* L&#39;insertion de données en bloc prend en charge plusieurs options pour les ID de visiteur. Vous pouvez envoyer à la fois l’identifiant Analytics et l’identifiant de Marketing Cloud (voir [Service d’identité](https://experienceleague.adobe.com/docs/id-service/using/home.html) pour en savoir plus). De plus, vous pouvez utiliser votre propre ID comme base [pour générer un ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds).
* L&#39;insertion de données en bloc prend en charge les variables de Liste et de données contextuelles.
* L&#39;insertion de données en bloc ne prend pas en charge les données Activity Map.

## Principales différences de format et de contenu des fichiers

* L&#39;insertion de données en bloc comporte d&#39;autres champs obligatoires. Voir la [documentation](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) pour plus de détails.
* Pour assurer la continuité et l’attribution des visiteurs, l’insertion de données en bloc nécessite le tri chronologique des lignes des fichiers. Voir [Groupes de Visiteurs](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) pour en savoir plus sur l’ordre d’activité des Visiteurs entre les fichiers.
* L&#39;insertion de données en bloc nécessite que les fichiers soient compressés au format .csv au format .gzip.
* BDIA utilise &quot;horodatage&quot; au lieu de &quot;date&quot;.

Pour plus d’informations, voir la comparaison suivante des valeurs de champ disponibles dans la section Insertion de données en bloc (BDIA) et Sources de données à traitement complet (FPDS).

## Comparaison des valeurs de champ disponibles dans BDIA et FPDS

| BDIA, FPDS, les deux | Variable BDIA | Variable de colonne Traitement complet | Description |
| --- | --- | --- | --- |
| BDIA | aamlh | Non pris en charge | Conseil de localisation de Adobe Audience Manager. Voir les valeurs d’ID valides dans le tableau de la liste des régions AAM ci-dessous. |
| Les variables | browserHeight | browserHeight | Hauteur du navigateur en pixels (par exemple, 768) |
| Les variables | browserWidth | browserWidth | Largeur du navigateur en pixels (par exemple, 1 024) |
| Les variables | campaign | campaign | Code de suivi de campagne de conversion |
| Les variables | channel | canal | Chaîne de canal (par exemple, section Sports) |
| Les variables | colorDepth | colorDepth | Intensité de couleur du moniteur en bits (par exemple, 24) |
| Les variables | connectionType | connectionType | type de connexion du visiteur (LAN ou modem) |
| BDIA | contextData.key | Non pris en charge | Les paires clé-valeur sont spécifiées dans en nommant l’en-tête &quot;contextData.product&quot; ou &quot;contextData.color&quot;. |
| Les variables | cookiesEnabled | cookiesEnabled | `Y` ou  `N` pour si le visiteur prend en charge les cookies de session propriétaires |
| Les variables | currencyCode | currencyCode | Code de devise du revenu (par exemple, `USD`) |
| BDIA | customerID.[customerIDType].authState | Non pris en charge | Etat authentifié du visiteur. Les valeurs prises en charge sont : 0, 1, 2, UNKNOWN, AUTHENTICATED, LOGGED_OUT ou &#39;&#39; (non sensible à la casse). Deux guillemets simples consécutifs (’) font que la valeur est omise dans la chaîne de requête, ce qui se traduit par 0 lorsque l’accès est effectué. Veuillez noter que les valeurs numériques authState prises en charge indiquent ce qui suit : 0 = INCONNU, 1 = AUTHENTICATED, 2 = LOGGED_OUT. La variable customerIDType peut être n’importe quelle chaîne alphanumérique, mais doit être considérée comme sensible à la casse. |
| BDIA | customerID.[customerIDType].id | Non pris en charge | ID de client à utiliser. La variable customerIDType peut être n’importe quelle chaîne alphanumérique, mais doit être considérée comme sensible à la casse. |
| BDIA | customerID.[customerIDType].isMCSeed | Non pris en charge | Indique s’il s’agit de la valeur initiale de l’ID de Visiteur de Marketing Cloud. Les valeurs prises en charge sont : 0, 1, TRUE, FALSE, &#39;&#39; (non-respect de la casse). Si vous utilisez 0, FALSE ou deux guillemets simples consécutifs (&#39;&#39;), la valeur est omise dans la chaîne de requête. La variable customerIDType peut être n’importe quelle chaîne alphanumérique, mais doit être considérée comme sensible à la casse. |
