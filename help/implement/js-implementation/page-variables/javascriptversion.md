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



# javascriptVersion

La variable indique la version de JavaScript prise en charge par le navigateur.


<!-- 

javascriptVersion.xml

 -->

Cette variable est complétée après le code de page et avant l’exécution de *`doPlugins`*.

> [!NOTE] Cette variable doit uniquement être lue et ne jamais être définie.

Vous pouvez lire ces valeurs et les copier dans props/eVars, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

| Paramètre de requête | Valeur | Exemple | Rapports concernés |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | Trafic &gt; Technologie &gt; Version de JavaScript |

Les versions H.10 et ultérieures du fichier JavaScript effectuent une détection précise jusqu’à la version 1.7 (soit la version la plus élevée au moment de la publication de H.10). Dans le cas des versions antérieures du fichier JavaScript, la détection n’est assurée que jusqu’à la version 1.3.
