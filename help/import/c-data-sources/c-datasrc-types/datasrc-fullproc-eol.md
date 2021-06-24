---
title: Fin de vie des sources de données à traitement complet
description: Raisons de la fin de vie et comparaisons entre l’API d’insertion de données en bloc et les sources de données à traitement complet.
exl-id: 24a44b7a-64fd-4a99-975f-4887f4638812
source-git-commit: f120c189228892e57e38e4d0e106eb3190326ff1
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 32%

---

# Fin de vie des sources de données à traitement complet

Depuis plusieurs années, les sources de données à traitement complet vous permettent d’envoyer des données au niveau de l’accès à Adobe Analytics. Ces données ont été traitées de la même manière que les données collectées via nos bibliothèques JavaScript et notre SDK d’applications mobiles. En 2020, Adobe a publié l’[API d’insertion de données en bloc](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md), qui exécute les mêmes fonctions que les sources de données à traitement complet, mais avec des fonctionnalités supplémentaires. Cette rubrique fournit des détails sur les fonctionnalités supplémentaires fournies par l’API Bulk Data Insertion et décrit les différences de formats de fichier.

À compter du 25 mars 2021, Adobe empêchera la création de nouvelles connexions de sources de données à traitement complet. Les connexions existantes continueront à être prises en charge jusqu’à ce que le service soit complètement abandonné le 31 juillet 2021. Outre notre documentation standard, nous vous proposons une présentation des [étapes nécessaires à l’envoi de données via l’API Bulk Data Insertion](http://adobe.ly/aabdia).

## Pourquoi cette fonctionnalité est-elle abandonnée ?

L’API Bulk Data Insertion (BDIA) fournit des fonctionnalités supplémentaires tout en couvrant tous les cas d’utilisation pris en charge par le traitement complet. Nous pensons que vous serez mieux servi en utilisant l’API Bulk Data Insertion.

## Principales différences entre les sources de données à traitement complet et l’API d’insertion de données en bloc

* L’insertion de données en bloc permet l’envoi de plusieurs fichiers qui peuvent être traités en parallèle. Vous pouvez utiliser les groupes de visiteurs pour assurer la continuité des visiteurs et l’attribution en eVar.
* L’insertion de données en bloc dispose de fonctionnalités de validation des données et de gestion des erreurs, ce qui supprime certaines tâches administratives liées à l’envoi de données d’accès.
* L’insertion de données en bloc prend en charge plusieurs options pour les identifiants visiteur. Vous pouvez envoyer Analytics ID et ID de Marketing Cloud (voir [Service d’identité](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr) pour en savoir plus). De plus, vous pouvez utiliser votre propre ID comme source [pour générer un ECID](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#customer-id-and-experience-cloud-visitor-id-seeds).
* L’insertion de données en bloc prend en charge les variables de liste et de données contextuelles.
* L’insertion de données en bloc ne prend pas en charge les données de Activity Map.

## Principales différences en termes de format et de contenu de fichier

* L’insertion de données en bloc comporte d’autres champs obligatoires. Pour plus d’informations, voir la [documentation](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) .
* Pour garantir la continuité et l’attribution des visiteurs, l’insertion de données en bloc nécessite que les lignes des fichiers soient triées par ordre chronologique. Voir [Groupes de visiteurs](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md#visitor-groups) pour en savoir plus sur l’ordre d’activité des visiteurs dans les fichiers.
* L’insertion de données en bloc nécessite que les fichiers soient compressés au format .csv au format .gzip.
* BDIA utilise &quot;horodatage&quot; au lieu de &quot;date&quot;.

Pour plus d’informations, reportez-vous à la comparaison suivante des valeurs de champ disponibles dans les sections Bulk Data Insertion (BDIA) et Full Processing Data Sources (FPDS).

## Comparaison des valeurs de champ disponibles dans BDIA et FPDS

| Variable BDIA | Variable de colonne Traitement complet | Description |
| --- | --- | --- |
| aamlh | Non pris en charge | Conseil d’emplacement de Adobe Audience Manager. |
| browserHeight | browserHeight | Hauteur du navigateur en pixels (par exemple, 768) |
| browserWidth | browserWidth | Largeur du navigateur en pixels (par exemple, 1 024) |
| campaign | campaign | Code de suivi de campagne de conversion |
| channel | channel | Chaîne de canal (par exemple, section Sports) |
| colorDepth | colorDepth | Intensité de couleur du moniteur en bits (par exemple, 24) |
| connectionType | connectionType | Type de connexion du visiteur (LAN ou modem) |
| contextData.key | Non pris en charge | Les paires clé-valeur sont spécifiées dans en nommant l’en-tête &quot;contextData.product&quot; ou &quot;contextData.color&quot;. |
| cookiesEnabled | cookiesEnabled | `Y` ou  `N` pour savoir si le visiteur prend en charge les cookies de session propriétaires |
| currencyCode | currencyCode | Code de devise du revenu (par exemple, `USD`) |
| customerID.[customerIDType].authState | Non pris en charge | État authentifié du visiteur. Les valeurs prises en charge sont les suivantes : 0, 1, 2, UNKNOWN, AUTHENTICATED, LOGGED_OUT ou &quot;&quot; (non-respect de la casse). Deux guillemets simples consécutifs (&#39;&#39;) entraînent l’omission de la valeur de la chaîne de requête, qui se traduit par 0 lorsque l’accès est effectué. Notez que les valeurs numériques authState prises en charge indiquent ce qui suit : 0 = INCONNU, 1 = AUTHENTICATED, 2 = LOGGED_OUT. customerIDType peut être n’importe quelle chaîne alphanumérique, mais doit être considéré comme sensible à la casse. |
| customerID.[customerIDType].id | Non pris en charge | ID de client à utiliser. customerIDType peut être n’importe quelle chaîne alphanumérique, mais doit être considéré comme sensible à la casse. |
| customerID.[customerIDType].isMCSeed | Non pris en charge | Indique s’il s’agit de l’adresse de contrôle de l’identifiant visiteur Marketing Cloud. Les valeurs prises en charge sont les suivantes : 0, 1, TRUE, FALSE, &quot;&quot; (non-respect de la casse). Si vous utilisez 0, FALSE ou deux guillemets simples consécutifs (&#39;&#39;), la valeur est omise dans la chaîne de requête. customerIDType peut être n’importe quelle chaîne alphanumérique, mais doit être considéré comme sensible à la casse. |
| eVarN | eVarN, c’est-à-dire `<eVar2>`..`<eVar>` | Nom de la variable eVar de conversion. Vous pouvez avoir jusqu’à 75 eVars ( eVar1 - eVar75 ) Vous pouvez spécifier le nom de l’eVar (eVar12) ou un nom convivial (Campagne publicitaire 3). |
| events | events | [Chaîne d’événements](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en#vars), formatée selon la même syntaxe que la variable s.events. Par exemple : scAdd,event1,event7 |
| hierN | hierN, c’est-à-dire `<hier2>`..`</hier2>` | Nom de la hiérarchie. Vous pouvez avoir jusqu’à 5 hiérarchies ( hier1 - hier5 ). Vous pouvez spécifier le nom de hiérarchie par défaut `hier2` ou un nom convivial (yankees). |
| homePage | homePage | Y ou N – Page active de la page d’accueil du visiteur. |
| ipaddress | Non pris en charge | Adresse IP du visiteur. |
| javaEnabled | javaEnabled | Y ou N – selon que Java est activé sur l’ordinateur du visiteur. |
| javaScriptVersion | javaScriptVersion | Version JavaScript (par exemple, 1.3). |
| langue | Non pris en charge | La langue prise en charge par le navigateur. Par exemple : `en-us`. |
| linkName | linkName | Nom du lien. |
| linkType | linkType | Type de lien. Les valeurs acceptables sont : `d: Download link`, `e: Exit link`, `o: Custom link`. |
| linkURL | linkURL | HREF du lien. |
| liste Par exemple, list2. | Non pris en charge | Liste délimitée de valeurs transmises à une variable, puis signalées comme lignes individuelles pour la création de rapports |
| marketingCloudVisitorID | Non pris en charge | Marketing Cloud ID. Voir [Identification des visiteurs](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en#id-service-api) et le service d’identification des visiteurs par Marketing Cloud |
| Non pris en charge | charSet | Jeu de caractères pris en charge pour votre site Web. Par exemple, UTF-8, ISO-8859-1, etc. |
| Non pris en charge | clickAction | Identificateur d’objet pour la carte des clics des visiteurs (oid). |
| Non pris en charge | clickActionType | Type d’identificateur d’objet pour la carte des clics des visiteurs (oidt). |
| Non pris en charge | clickContext | Identificateur de page pour la carte des clics des visiteurs (pid). |
| Non pris en charge | clickContextType | Type d’identificateur de page pour la carte des clics des visiteurs (pidt). |
| Non pris en charge | clickSourceID | Index source pour la carte des clics des visiteurs (oi). |
| Non pris en charge | clickTag | Nom de balise d’objet pour la carte des clics des visiteurs (ot). |
| Non pris en charge | scXmlVer | Numéro de version de requête XML des rapports marketing (par exemple, 1.0). |
| Non pris en charge | timezone | Décalage du fuseau horaire du visiteur par rapport à GMT, en heures (ex. : -8). |
| pageName | pageName | Nom de la page |
| pageType | pageType | Type de page (par exemple, &quot;Page d’erreur&quot;). |
| pageURL | pageURL | URL de la page (par exemple, https://www.example.com/index.html). |
| plugins | plugins | Liste des noms des modules externes de navigateur séparés par des points-virgules. |
| products | products | Liste de tous les produits de la page. Séparez les produits par une virgule. Par exemple : Sports;Balle;1;5.95,Jouets; Haut;1:1.99. |
| prop1 - prop75 | propN, c’est-à-dire `<prop2>`..`</prop2>` | Chaîne du numéro de propriété (par exemple, section Sports). |
| propN | propN | Valeurs de vos propriétés. |
| purchaseID | purchaseID | ID d’achat. |
| referrer | referrer | URL du référent de la page. |
| reportSuiteID | s_account | Indique les suites de rapports auxquelles vous souhaitez envoyer des données. Vous devez séparer plusieurs identifiants de suite de rapports par une virgule. |
| resolution | resolution | Résolution de l’écran (par exemple, 1 024 x 768). |
| server | server | Chaîne du serveur. |
| state | state | Chaîne d’état de conversion. |
| timestamp | date | Utilisez le format de date ISO 8601 AAAA-MM-DDThh:mm:ss±décalage_UTC (par exemple, 2021-09-01T12:00:00-07:00 ) ou le format d’heure Unix (nombre de secondes écoulées depuis le 1er janvier 1970). |
| trackingServer | Non pris en charge | Ne peut être fourni que par le biais de l’en-tête de colonne. |
| transactionID | Non pris en charge | Valeur couramment utilisée pour associer des activités d’utilisateur multicanaux en vue de la génération de rapports. Pour plus d’informations, consultez le [Guide de l’utilisateur des sources de données](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html?lang=en#data-sources). |
| userAgent | Non pris en charge | Chaîne de l’agent utilisateur |
| visitorID | visitorID | Analytics ID du visiteur. Voir [Identification des visiteurs](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en). |
| zip | zip | Code postal de conversion. |
