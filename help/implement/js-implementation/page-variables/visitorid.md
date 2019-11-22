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


# visitorID

Les visiteurs peuvent être identifiés par la variable ou par Adresse IP/Agent utilisateur.


<!-- 

visitorID.xml

 -->

La variable *`visitorID`* peut contenir jusqu’à 100 caractères alphanumériques, mais pas de trait d’union.

Si vous avez spécifiquement défini un identifiant personnalisé, celui-ci sera toujours utilisé avant d’autres méthodes d’identification.

Voici l’ordre à utiliser : s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA.

| ** Taille maximale** | ** Paramètre du débogueur** | ** Rapports renseignés** | ** Valeur par défaut** |
|---|---|---|---|
| 100 octets | vid | n/d | "" |

**Syntaxe et valeurs possibles** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

> [!NOTE] La variable *`visitorID`* ne peut pas contenir de trait d’union.

**Exemples** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**Paramètres de configuration** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

Aucun
