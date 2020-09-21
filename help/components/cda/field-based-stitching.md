---
title: Groupement basé sur les champs
description: Comprenez les conditions préalables et les limites du groupement de données à l’aide du groupement basé sur les champs.
translation-type: ht
source-git-commit: 322e2e87ab532d5e8a864dc06613a9b275c71df5
workflow-type: ht
source-wordcount: '226'
ht-degree: 100%

---


# Groupement basé sur les champs

Les analyses entre appareils offrent deux méthodes distinctes pour regrouper les données. Cette méthode repose sur une variable Analytics, telle qu’une [prop](/help/implement/vars/page-vars/prop.md) ou une [eVar](/help/implement/vars/page-vars/evar.md), pour contenir un identifiant de personne. Elle utilise cette variable comme base pour lier les appareils.

## Conditions préalables spécifiques au groupement basé sur les champs

Si vous envisagez d’implémenter les analyses entre appareils à l’aide du groupement basé sur les champs, les éléments suivants sont requis. Collaborez avec les équipes de votre entreprise et votre gestionnaire de compte Adobe pour vous assurer que vous remplissez toutes les conditions suivantes.

>[!IMPORTANT]
>
>Si vous ne remplissez pas toutes les conditions préalables requises, vous risquez de ne pas pouvoir activer les analyses entre appareils ou de ne pas obtenir de résultats satisfaisants lors du regroupement de données.

* Toutes les conditions préalables sont répertoriées dans la [page d’aperçu](overview.md).
* Votre implémentation doit définir une prop ou une eVar qui identifie de manière unique un individu chaque fois que cela est possible, par exemple lorsqu’un utilisateur se connecte ou ouvre un e-mail. Cette exigence s’applique à toutes les plates-formes, y compris les applications mobiles si elles sont utilisées. Communiquez la variable d’identification de votre choix à votre gestionnaire de compte lors de l’attribution du groupement basé sur les champs.

## Limites spécifiques au groupement basé sur les champs

* Le groupement basé sur les champs fonctionne mieux sur les suites de rapports qui présentent un taux d’identification élevé. Si votre suite de rapports présente un taux d’identification ou de connexion faible, privilégiez le [graphique Co-op](device-graph.md).

## Étapes suivantes

Une fois que toutes les conditions requises sont remplies et que vous avez compris les limites, vous pouvez commencer à [configurer les analyses entre appareils](setup.md).