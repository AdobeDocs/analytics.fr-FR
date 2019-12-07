---
description: Les sections ci-dessous décrivent les erreurs courantes des comptes dynamiques.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Erreurs courantes
topic: Developer and implementation
uuid: 04345355-60cc-4678-81c3-390c86752df1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Erreurs courantes

Les sections ci-dessous décrivent les erreurs courantes des comptes dynamiques.

## Compte codé en dur {#section_FB6F89BF317F45D387C00986ACA690BC}

Si vous souhaitez toujours envoyer les données à une suite de rapports en particulier, définissez [!UICONTROL s_dynamicAccountSelection] sur la valeur « false » (les variables peuvent être également supprimées ensemble :

```js
var s_account="defaultreportsuiteid" 
REMOVE: s.dynamicAccountSelection=true 
REMOVE: s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

Dans le cas ci-dessus, defaultreportsuiteid est toujours utilisé après la suppression des deux autres lignes.

## Placement du code {#section_05375CB2EF5A414794BC8209C906AEEB}

La définition de *`s_account`* après les lignes de code n’entraîne pas le remplacement de la sélection de compte dynamique, comme illustré ci-dessous.

```js
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
s_account="anotherreportsuiteid" 
```

Dans l’exemple ci-dessus, le compte « anotherreportsuiteid » remplace « defaultreportsuiteid », mais il ne remplace pas les correspondances dans [!UICONTROL s.dynamicAccountList]. La fonction qui évalue [!UICONTROL s.dynamicAccountList] est exécutée bien plus tard dans le fichier .JS.

## Marquage multisuite {#section_6C014FA9B87D4622B483BCDE4281D2A9}

Le marquage multisuite peut être utilisé avec la sélection de compte dynamique, comme illustré ci-dessous.

```js
s.dynamicAccountSelection=true 
s.dynamicAccountList="suiteid1,suiteid2=client.com" 
```

## Correspondance des comptes dynamiques {#section_647AB47B38D640D6BCC853FDA4E4342D}

Ne placez pas les variables de [!UICONTROL correspondance de comptes dynamiques] entre guillemets. Ces options sont affichées ci-dessous.

| Nom de domaine/hôte | Aucun |
|---|---|
| Chaîne de requête | s.dynamicAccountMatch=(window.location.search?window.location.search:"?") |
| Hôte/domaine et chemin d’accès | s.dynamicAccountMatch=window.location.host+window.lcation.pathname |
| Chemin et chaîne de requête | s.dynamicAccountMatch=window.location.pathname+(window.location.search?window.location.search""?") |
| URL complète | s.dynamicAccountMatch=window.location.href |

