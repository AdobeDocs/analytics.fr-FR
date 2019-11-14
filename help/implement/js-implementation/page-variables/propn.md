---
description: Les variables de page renseignent directement un rapport (pageName, props de liste, variables de liste, etc.).
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de page
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# propN

Les variables de propriété ([!UICONTROL prop]) sont utilisées pour créer des rapports personnalisés dans le [!UICONTROL module Trafic].

<!-- 

propN.xml

 -->

Vous pouvez utiliser la variable props comme compteur (pour comptabiliser le nombre d’envois d’une page vue), pour les rapports de cheminement ou dans des rapports de corrélation.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | c1 - c75 | Trafic personnalisé | "" |

**Syntaxe et valeurs possibles** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

Les variables de [!UICONTROL propriété] ne sont concernées par aucune limite, à l’exception des limites standard.

**Exemples** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Paramètres de configuration** {#section_25FDEB6ECA8242A2A44EE540C083078A}

Contactez le service à la clientèle Adobe au sujet de l’affichage des mesures [!UICONTROL Visite], [!UICONTROL Visiteur] et [!UICONTROL Chemin] pour les variables [!UICONTROL prop].
