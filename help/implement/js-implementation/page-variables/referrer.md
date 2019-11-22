---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# referrer

La variable peut être utilisée pour restaurer les informations de référent perdues.


<!-- 

referrer.xml

 -->

Les redirections JavaScript et côté serveur sont souvent utilisées pour acheminer les visiteurs vers les emplacements appropriés. Cependant, lorsqu’un navigateur est redirigé, l’URL de référence originale est perdue.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 255 octets | R | Trafic &gt; Conversion des méthodes de recherche &gt; Méthodes de recherche | document.referrer |

La plupart des entreprises utilise des redirections sur leurs sites Web. Un visiteur peut ainsi être redirigé à partir des résultats de recherche payante d’un moteur de recherche. Lorsqu’un navigateur est redirigé, il n’est pas rare que le référent soit perdu. La variable La variable *`referrer`* peut être utilisée pour restaurer la valeur d’origine *`referrer`* sur la première page après une redirection. La variable *`referrer`* peut être renseignée côté serveur ou via JavaScript à partir de la chaîne de requête.

Pour qu’Analytics enregistre un référent, celui-ci doit être « bien formé » ; en d’autres termes, il doit être conforme au format URL standard, avec un protocole et un emplacement approprié.

**Syntaxe et valeurs possibles** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

La variable *`referrer`*. Assurez-vous que la chaîne respecte le codage URL (pas d’espaces autorisés).

**Exemples** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**Paramètres de configuration** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

Aucun

**Pièges, questions et conseils** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

La variable *`referrer`* doit se présenter sous la forme d’une URL standard et inclure un protocole.
