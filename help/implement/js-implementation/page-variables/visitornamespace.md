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


# visitorNamespace

La variable identifie le domaine avec lequel les cookies sont définis.


<!-- 

visitorNamespace.xml

 -->

Si la variable *`visitorNamespace`* est utilisée dans votre fichier JavaScript, abstenez-vous de la supprimer ou de la modifier. Si la variable *`visitorNamespace`* change, tous les visiteurs signalés dans Analytics peuvent devenir de nouveaux visiteurs. L’historique des visiteurs est déconnecté du trafic actuel et futur. Ne modifiez pas cette variable sans l’accord d’un représentant Adobe.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| S.O. | ns | S.O. | "" |

Analytics utilise un cookie pour identifier de façon unique les visiteurs de votre site. Si la variable *`visitorNamespace`* n’est pas utilisée, le cookie est associé à 2o7.net. Si la variable *`visitorNamespace`* est utilisée, le cookie est associé à un sous-domaine de 2o7.net. Les cookies de tous les visiteurs de votre site doivent être associés au même domaine ou sous-domaine.

L’utilisation de la variable *`visitorNamespace`*&#x200B;évite la surcharge potentielle de la limite des cookies du navigateur. Internet Explorer impose une limite de 20 cookies par domaine. En utilisant la variable *`visitorNamespace`* les cookies Analytics des autres sociétés n’entreront pas en conflit avec ceux de vos visiteurs.

**Syntaxe et valeurs possibles** {#section_EE247FE371784CA4B6058182181F3EA1}

La valeur de la variable *`visitorNamespace`* doit être fournie par Adobe. Il s’agit d’une chaîne de caractères ASCII ne contenant pas de virgules, de points, d’espaces ou de caractères spéciaux.

```js
s.visitorNamespace="company_specific_value"
```

**Identification des visiteurs dans les suites de rapports** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

Si vous ne spécifiez aucune variable `visitorNamespace`, chaque suite de rapports dans votre société reçoit son propre cookie d’identifiant visiteur écrit sous la forme `s_vi_[random string]`. Si vous spécifiez la variable `visitorNamespace`, le même cookie `s_vi` sera utilisé pour toutes les suites de rapports qui envoient des données à la variable `trackingServer` spécifiée. Si vous avez mis en œuvre un balisage multisuite, veillez à spécifier l’espace de noms du visiteur afin que le même cookie soit utilisé par chaque suite de rapports.

**Exemples** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**Paramètres de configuration** {#section_1128A2531ECC43DFA6749ECC21F050A2}

Aucun
