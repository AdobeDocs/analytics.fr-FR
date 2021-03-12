---
title: Groupement basé sur les champs
description: Comprenez les conditions préalables et les limites du groupement de données à l’aide du groupement basé sur les champs.
translation-type: tm+mt
source-git-commit: beed7ffcc39b9b2628b1487b5e2eac42fa3a94d0
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 35%

---


# Groupement basé sur les champs

Analytics sur l’ensemble des appareils offre deux méthodes distinctes pour regrouper les données. Cette méthode repose sur une variable Analytics, telle qu’une [prop](/help/implement/vars/page-vars/prop.md) ou une [eVar](/help/implement/vars/page-vars/evar.md), pour contenir un identifiant de personne. Elle utilise cette variable comme base pour lier les appareils.

## Conditions préalables spécifiques au groupement basé sur les champs

Si vous envisagez d’implémenter les analyses entre appareils à l’aide du groupement basé sur les champs, les éléments suivants sont requis. Collaborez avec les équipes de votre entreprise et votre gestionnaire de compte Adobe pour vous assurer que vous remplissez toutes les conditions suivantes.

>[!IMPORTANT]
>
>Si vous ne remplissez pas toutes les conditions préalables requises, vous risquez de ne pas pouvoir activer les analyses entre appareils ou de ne pas obtenir de résultats satisfaisants lors du regroupement de données.

* Toutes les conditions préalables sont répertoriées dans la [page d’aperçu](overview.md).
* Votre implémentation doit définir une prop ou une eVar qui identifie de manière unique un individu chaque fois que cela est possible, par exemple lorsqu’un utilisateur se connecte ou ouvre un e-mail. Cette exigence s’applique à toutes les plates-formes, y compris les applications mobiles si elles sont utilisées. Communiquez la variable d’identification de votre choix à votre gestionnaire de compte lors de l’attribution du groupement basé sur les champs.

## Limites spécifiques au groupement basé sur les champs

* L’assemblage basé sur les champs fonctionne mieux sur les suites de rapports qui présentent un taux élevé d’identification/d’authentification des utilisateurs.
* Bien que les props et les eVars contiennent des règles de traitement des caractères en majuscules et en minuscules à des fins de rapports, l’assemblage basé sur des champs ne transforme en rien la prop ou l’eVar utilisé pour l’assemblage. L’assemblage basé sur les champs utilise la valeur du champ spécifié telle qu’elle existe après les règles VISTA et les règles de post-traitement. Le processus de raccordement est sensible à la casse. Par exemple, si le mot &quot;Bob&quot; apparaît parfois dans la prop/l&#39;eVar et que le mot &quot;BOB&quot; apparaît, il sera traité comme deux personnes distinctes par le processus de sélection.
* Etant donné que l’assemblage basé sur les champs est sensible à la casse, l’Adobe recommande de revoir les règles VISTA ou les règles de traitement qui s’appliquent à la variable prop ou à l’eVar utilisée pour l’assemblage basé sur les champs. Ils doivent être revus pour s&#39;assurer qu&#39;aucune de ces règles n&#39;introduit de nouvelles formes de même ID. Par exemple, vous devez vous assurer qu’aucune règle VISTA ou de traitement n’introduit une mise en minuscule de la prop ou de l’eVar sur une partie seulement des accès.
* L’assemblage basé sur les champs ne prend pas en charge l’utilisation de plusieurs prop ou eVar à des fins d’assemblage. Par exemple, si eVar12 contient un identifiant de connexion et eVar20 un identifiant de messagerie, vous devez en choisir un.
* L’assemblage basé sur les champs ne combine ni ne concatène les champs (par exemple, eVar10 + prop5).
* La prop ou l’eVar doit contenir un seul type d’identifiant. Par exemple, la prop ou l’eVar ne doit pas contenir une combinaison d’ID de connexion et d’ID d’adresse électronique.
* Si plusieurs accès se produisent avec le même horodatage pour le même visiteur, mais avec des valeurs différentes dans la prop de raccordement ou l’eVar, l’ADC choisit selon l’ordre alphabétique. Ainsi, si le visiteur A a deux accès avec le même horodatage et que l’un des accès spécifie Bob et l’autre spécifie Ann, CDA choisira Ann.


## Étapes suivantes

Une fois que votre entreprise a satisfait à toutes les exigences et a compris les limites, vous pouvez début [Configuration d’Analyses sur plusieurs périphériques](setup.md).
