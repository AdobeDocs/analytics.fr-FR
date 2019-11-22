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


# server

La variable est utilisée pour afficher soit le domaine d’une page web (pour indiquer les domaines sur lesquels arrivent les utilisateurs), soit le serveur d’où provient la page (pour une référence rapide de l’équilibrage de charge).


<!-- 

server.xml

 -->

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | server | Serveurs | "" |

Si votre site possède plusieurs domaines qui diffusent le même contenu, vous pouvez utiliser la variable *`server`* pour déterminer ceux qui sont utilisés par les visiteurs. Le code JavaScript ci-dessous renseigne le domaine de la page dans la variable « server ».

```js
s.server=window.location.hostname
```

Si vous utilisez la variable « server » comme référence rapide pour l’équilibrage de charge, vous pouvez indiquer un nom ou un numéro de serveur dans cette variable. Reportez-vous à l’exemple suivant :

```js
s.server="server 14"
```

Bien que le rapport [!UICONTROL Serveurs les plus populaires] puisse être utilisé comme référence rapide de l’équilibrage de charge, il ne constitue pas une mesure précise de la charge serveur. Ainsi, le trafic généré par le bouton Précédent n’augmente pas la charge serveur, mais il est affiché dans les rapports. Le rapport n’indique pas les serveurs qui diffusent des images ou des téléchargements de grande taille.

**Syntaxe et valeurs possibles** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

La variable *`server`* n’est concernée par aucune limite, à l’exception des limites standard.

**Exemples** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**Paramètres de configuration** {#section_969DB379D5BD469FBEE8D505D3000E49}

Aucun

**Pièges, questions et conseils** {#section_42A28F9B01574F38891D9D54B411D8FE}

La variable *`server`* peut servir à indiquer les domaines les plus populaires ou les serveurs qui diffusent le plus de pages.

