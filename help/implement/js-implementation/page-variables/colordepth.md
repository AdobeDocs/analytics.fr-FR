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


# colorDepth

La variable sert à afficher le nombre de bits utilisés pour l’affichage de la couleur sur chaque pixel de l’écran.


<!-- 

colordepth.xml

 -->

Par exemple, la valeur 32 représente 32 bits de couleur à l’écran. Cette variable est complétée après le code de page et avant l’exécution de *`doPlugins`*.

> [!NOTE] Cette variable doit uniquement être lue et ne jamais être définie.

Vous pouvez lire ces valeurs et les copier dans `props/eVars`, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

| Paramètre de requête | Valeur | Exemple | Rapports concernés |
|---|---|---|---|
| c | 8, 16 et 32 | 32 | Trafic &gt; Technologie &gt; Profondeur de couleur d’écran |
