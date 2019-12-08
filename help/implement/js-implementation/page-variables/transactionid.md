---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# stockage

Les [!UICONTROL sources de données d’intégration] utilise une variable [!UICONTROL transactionID] pour lier les données hors ligne à une transaction en ligne (comme un prospect ou un achat généré en ligne).


<!-- 

transactionID.xml

 -->

Chaque variable *`transactionID`* unique envoyée à Adobe est enregistrée en vue d’un téléchargement des [!UICONTROL sources de données] des informations hors ligne concernant cette transaction. Voir [Sources de données](https://marketing.adobe.com/resources/help/en_US/sc/datasources/).

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | xact | n/d | "" |

**Activation du stockage d’ID de transaction** {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Avant que les valeurs *`transactionID`* ne soient enregistrées, le [!UICONTROL stockage d’ID de transaction] doit être activé pour la suite de rapports sélectionnée dans le gestionnaire de suites de rapports. Ce paramètre se trouve sous :

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

Pour déterminer si le *`transactionID Storage`* est activé pour une suite de rapports, sélectionnez

```
Analytics > Admin > Data Sources > Manage
```

**Syntaxe et valeurs possibles** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

La variable *`transactionID`* ne peut contenir que des caractères alphanumériques. Si plusieurs [!UICONTROL transactionID] doivent être enregistrés pour un seul accès, vous pouvez séparer les différentes valeurs par une virgule.

**Exemples** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**Pièges, questions et conseils** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* Si l’enregistrement de la variable *`transactionID`* n’est pas activé, les valeurs *`transactionID`* sont ignorées et ne peuvent pas être utilisées avec les [!UICONTROL sources de données d’intégration]. Veillez à définir une variable de conversion ou un événement (une eVar ou la variable « events ») dans la page sur laquelle la variable *`transactionID`* est définie. Dans le cas contraire, aucune donnée ne sera enregistrée pour *`transactionID`*.

* Si vous enregistrez des [!UICONTROL transactionIDs] pour plusieurs systèmes, tels que des achats et des prospects, assurez-vous que la valeur de *`transactionID`* est toujours unique. Pour ce faire, il vous suffit d’ajouter un préfixe à l’identifiant ; par exemple prospect_1234 et achat_1234. Les [!UICONTROL sources de données d’intégration] ne fonctionnent pas comme prévu (les données de la [!UICONTROL source de données] sont liées à des données incorrectes) si une variable *`transactionID`* est constatée à deux reprises.

* Par défaut, les valeurs *`transactionID`* sont mémorisées pendant 90 jours. Si votre processus d’interaction hors ligne dépasse 90 jours, demandez à un agent du service clientèle d’étendre cette limite.

> [!NOTE] La variable *`transactionID`* peut contenir n’importe quel caractère, à l’exception de la virgule. Elle doit se trouver au même emplacement que celui où est spécifiée la limite de caractères (100 octets). En cas d’utilisation de caractères multi-octets, cette prise en charge doit être activée afin d’éviter les problèmes liés aux caractères inattendus dans la variable *`transactionID`*.
