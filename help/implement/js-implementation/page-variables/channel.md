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


# marketing

La variable est généralement utilisée pour identifier une section de votre site.


<!-- 

channel.xml

 -->

Par exemple, un site commercial peut présenter des sections telles que « Electronique », « Jouets » ou « Vêtements ». Un site de médias peut présenter des sections comme « Infos », « Sports » ou encore « Affaires ».

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| 100 octets | CH | Contenu du site &gt; Sections du site | "" |

Adobe recommande de renseigner la variable channel sur chaque page. Vous pouvez également activer une corrélation entre les variables *`channel`* et [!UICONTROL page name].

Lorsque des sections comportent un ou plusieurs niveaux de sous-sections, vous pouvez les afficher dans la variable *`channel`* ou utiliser des variables distinctes pour identifier les niveaux.

**Syntaxe et valeurs possibles**

```js
s.channel="value"
```

Aucune autre limitation n’est appliquée au niveau des valeurs de la variable de *`channel`*.

**Exemples** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Pièges, questions et conseils** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

Si votre site contient plusieurs niveaux, utilisez la variable *`hierarchy`* ou une autre pour les désigner. La valeur *`channel`* n’est pas persistante, mais les événements de succès déclenchés sur la même page sont attribués à la valeur de la variable *`channel`*.
