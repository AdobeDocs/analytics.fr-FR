---
title: Accrochage basé sur les champs
description: Comprendre les conditions préalables et les limites de l’assemblage de données à l’aide de l’assemblage basé sur des champs.
translation-type: tm+mt
source-git-commit: 2e7ec3b2e4401b02005b3099dae2bb34c64a6846
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 23%

---


# Accrochage basé sur les champs

L’Analytics sur plusieurs périphériques fournit deux méthodes distinctes pour assembler les données. Cette méthode repose sur une variable Analytics, telle qu’une [prop](/help/implement/vars/page-vars/prop.md) ou une [eVar](/help/implement/vars/page-vars/evar.md), pour contenir un identifiant de personne. Il utilise cette variable comme base pour lier les périphériques ensemble.

## Conditions préalables spécifiques à l’assemblage basé sur les champs

Si vous prévoyez d’implémenter des Analytics sur plusieurs périphériques à l’aide d’un assemblage basé sur des champs, les éléments suivants sont requis. Collaborez avec les équipes de votre entreprise et votre gestionnaire de compte Adobe pour vous assurer que vous remplissez toutes les conditions suivantes.

>[!IMPORTANT] Si vous ne remplissez pas toutes les conditions préalables requises, vous risquez de ne pas pouvoir activer les analyses entre appareils ou de ne pas obtenir de résultats satisfaisants lors du regroupement de données.

* Toutes les conditions préalables sont répertoriées dans la page [](overview.md)d’aperçu.
* Votre implémentation doit définir une prop ou une eVar qui identifie de manière unique un individu chaque fois que cela est possible, par exemple lorsqu’un utilisateur se connecte ou ouvre un courrier électronique. Cette exigence s’applique à toutes les plates-formes, y compris les applications mobiles si elles sont utilisées. Communiquez la variable d’identification de votre choix à votre gestionnaire de compte lors de l’attribution de privilèges d’accès basés sur les champs.

## Limites spécifiques à l’assemblage basé sur les champs

* L’assemblage basé sur les champs fonctionne mieux sur les suites de rapports qui présentent un taux d’identification élevé. Si votre suite de rapports présente un faible taux d’identification ou de connexion, pensez à utiliser le graphique [](device-graph.md)Co-op.

## Étapes suivantes

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).