---
description: Le fichier .js peut être configuré pour sélectionner automatiquement l’identifiant (ID) d’une suite de rapports.
keywords: Analytics Implementation
title: 'Identifiants de suite de rapports : comptes dynamiques'
topic: Developer and implementation
uuid: 763a9741-309d-4795-8819-6543866047d5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Identifiants de suite de rapports : comptes dynamiques

Le fichier .js peut être configuré pour sélectionner automatiquement l’identifiant (ID) d’une suite de rapports. Le fichier .js envoie automatiquement la demande d’image à la suite de rapports en fonction de l’URL. Par exemple, si l’URL est `www.mysite.com`, la demande d’image est automatiquement envoyée à la suite de rapports A. Si l’URL est `www.mysite1.com`, la demande d’image est automatiquement envoyée à la suite de rapports B.

Ces chaînes peuvent être trouvées dans les éléments suivants :

* Hôte/domaine (paramètre par défaut)
* Chemin d’accès
* Chaîne de requête
* Hôte/domaine et chemin d’accès
* Chemin et chaîne de requête
* URL complète

Pour plus d’informations sur la configuration d’[!DNL Analytics] afin de sélectionner automatiquement un [!UICONTROL identifiant de suite de rapports], contactez les agents d’assistance en direct.

## Définition du segment d’URL à faire correspondre {#section_8099162F75F641CFBE46FD814450EF36}

Selon l’exemple d’URL donné ci-après, les parties de l’URL sont indiquées ci-dessous, avec la variable `s.dynamicAccountMatch` qui doit être définie. (Si la variable `s.dynamicAccountMatch` n’est pas définie, vous devez rechercher par défaut uniquement le nom de domaine/hôte).
Exemple d’URL : `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321`

| Partie | Exemple (à partir de l’exemple ci-dessus) |
|---|---|
| Nom de domaine/hôte | `www.client.com` |
| Chemin d’accès | `directory1/directory2/filename.html` |
| Chaîne de requête | `param1=1234&param2=4321` |
| Hôte/domaine et chemin d’accès | `www.client.com/directory1/directory2/filename.html` |
| Chemin et chaîne de requête | `directory1/directory2/filename.html?param1=1234&param2=4321` |
| URL | `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321` |
| Partie | `s.dynamicAccountmatch` |
| Nom de domaine/hôte | Non défini |
| Chemin d’accès | `window.location.pathname` |
| Chaîne de requête | `(window.location.search?window.location.search:"?")` |
| Hôte/domaine et chemin d’accès | `window.location.host+window.location.pathname` |
| Chemin et chaîne de requête | `window.location.pathname+(window.location.search?window.location.search:"?")` |
| URL | `window.location.href` |

Examinez l’exemple suivant :

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite2=clientdirectory;reportsuite1=client.com"`
* `s.dynamicAccountMatch=window.location.host+window.location.pathname`

## Plusieurs règles {#section_163FED1C1FA74C48BCB78B0D67EF36AE}

Si plusieurs règles sont sélectionnées (voir l’exemple ci-dessus), elles sont exécutées de la gauche vers la droite. Les règles s’interrompent dès qu’une correspondance a été trouvée, comme illustré ci-dessous (avec l’ensemble donné de règles).

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com"`

Le code vérifie d’abord si `qa.client.com` se trouve dans le nom de domaine/hôte. Si c’est le cas, la suite de rapports `devreportsuite1` est sélectionnée, et la recherche s’interrompt. Vous devez séparer les règles à l’aide d’un point-virgule.

## Suite de rapports par défaut {#section_0360D724929348B0B211708B5BA15647}

La variable `s_account` peut être définie en premier. Elle joue le rôle de valeur par défaut si les chaînes spécifiées sont introuvables. Voici un exemple :

```javascript
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

Dans l’exemple ci-dessus, si le nom du domaine/hôte ne contient pas `qa.client.com`, ni `client.com`, la suite de rapports *defaultreportsuiteid* est utilisée.
