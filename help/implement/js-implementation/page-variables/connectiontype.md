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




# connectionType

Dans Internet Explorer, la variable indique si le navigateur est configuré sur une connexion LAN (réseau local) ou modem.


<!-- 

conntype.xml

 -->

Cette variable est complétée après le code de page et avant l’exécution de *`doPlugins`*.

> [!NOTE] Cette variable doit uniquement être lue et ne jamais être définie.

Vous pouvez lire ces valeurs et les copier dans `props/eVars`, mais vous ne pouvez, en aucun cas, les modifier. Cette variable est apparue avec la version H.11 du fichier JavaScript.

| Paramètre de requête | Valeur | Exemple | Rapports concernés |
|---|---|---|---|
| ct | lan ou modem | lan | Trafic &gt; Technologie &gt; Type de connexion |
