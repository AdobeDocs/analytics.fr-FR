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


# media.trackVars

La variable identifie les variables qui doivent être envoyées avec un accès au média.


<!-- 

media_trackVars.xml

 -->

Elle s’applique uniquement à JavaScript et [!UICONTROL ActionSource].

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| S.O. | S.O. | S.O. | s.Media.trackVars="None" |

**Syntaxe et valeurs possibles** {#section_7374684A7EB34AE685E8C40A66CFD289}

Noms de variables tels que [!UICONTROL propN], *`eVarN`*, *`events`*, *`channel`*, etc.

**Exemples** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars="prop2,events,eVar3"
```

**Pièges, questions et conseils** {#section_615AE1B696124B00B78F651B03813EAB}

* Même si eVar3 est spécifiée dans [!UICONTROL trackVars], elle est envoyée avec un accès au média.

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

La variable spécifie l’ordre dans lequel les cookies et les identifiants d’abonnés sont utilisés pour identifier les visiteurs.

<!-- 

mobile.xml

 -->

Reportez-vous à la section [Protocoles de réseau mobile](/help/implement/js-implementation/c-additional-libraries/network-protocols.md).

| Taille maximale | Paramètre du débogueur | Rapports renseignés | Valeur par défaut |
|---|---|---|---|
| S.O. | /5/ ou /1/ dans le chemin de l’URL de l’image | S.O. | Aucun |

**Syntaxe et valeurs possibles** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**Pièges, questions et conseils** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Utilisez l’identification entre visiteurs pour atténuer les pics possibles du trafic des visiteurs lors de l’utilisation de la variable *`s.mobile`* avec l’implémentation des cookies JavaScript.
