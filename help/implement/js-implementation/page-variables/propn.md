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


# propN

Les variables de propriété (`prop`) sont utilisées pour créer des rapports personnalisés dans le module Trafic.


<!-- 

propN.xml

 -->

Vous pouvez utiliser la variable props comme compteur (pour comptabiliser le nombre d’envois d’une page vue), pour les rapports de cheminement ou dans des rapports de corrélation.

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | c1 - c75 | Trafic personnalisé | "" |

**Syntaxe et valeurs possibles**

```js
s.propN="value"
```

Les variables de [!UICONTROL propriété] ne sont concernées par aucune limite, à l’exception des limites standard.

**Exemples**

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Paramètres de configuration**

Contactez le service à la clientèle Adobe au sujet de l’affichage des mesures Visite, Visiteur et Chemin pour les variables `prop`.
