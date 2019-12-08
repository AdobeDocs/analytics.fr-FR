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


# maxDelay

La variable s.maxDelay est principalement utilisée dans les intégrations Genesis DFA pour déterminer le délai d’inactivité lors du contact de l’hôte DFA. Si Adobe ne reçoit pas de réponse des serveurs de DFA dans le délai spécifié qui est défini dans la variable  , la connexion est établie, et les données sont traitées normalement. Implémentez cette variable si le temps de réponse de DFA sur chaque page vous préoccupe. Il est conseillé de tester cette valeur pour déterminer le délai d’inactivité optimal.


<!-- 

maxDelay.xml

 -->

**Exemple d’implémentation**

```
s.maxDelay="750";
```

**Propriétés**

* Cette variable est une mesure d’événement facultative qui est renseignée via le code JavaScript implémenté sur votre site.
* Si l’hôte DFA ne répond pas dans le délai imparti, l’événement désigné pour le délai dépassé s’exécute (attribué via l’assistant d’intégration Genesis).
* Cette variable ne peut contenir qu’une valeur numérique.
* La durée spécifiée est mesurée en millisecondes.
* L’augmentation du délai d’attente permet de collecter des données DFA supplémentaires, mais augmente aussi le risque de perte des données d’accès Analytics.

   La perte de ces données Analytics peut se produire lorsque l’utilisateur quitte la page pendant le délai *`s.maxDelay`*.

* La diminution du délai d’attente limite le risque de perte des données d’accès Analytics, mais peut diminuer le nombre de données DFA envoyées avec les données d’accès.

   La perte des données d’intégration DFA peut survenir lorsque la période *`s.maxDelay`* ne permet pas à l’hôte DFA de répondre.

> [!NOTE] Adobe ne contrôle pas le temps de réponse de DFA. Si vous rencontrez des problèmes même après avoir augmenté le délai de la variable, contactez l’administrateur de compte DFA de votre société.
