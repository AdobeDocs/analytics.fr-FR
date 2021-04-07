---
title: Groupement basé sur les champs
description: Comprenez les conditions préalables et les limites du groupement de données à l’aide du groupement basé sur les champs.
translation-type: ht
source-git-commit: beed7ffcc39b9b2628b1487b5e2eac42fa3a94d0
workflow-type: ht
source-wordcount: '499'
ht-degree: 100%

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

* Lʼassemblage basé sur les champs fonctionne mieux sur les suites de rapports qui présentent un taux dʼidentification/dʼauthentification utilisateur élevé.
* Bien que les variables prop et eVar contiennent chacune des règles de traitement des caractères majuscules et minuscules à des fins de comptes rendus des performances, lʼassemblage basé sur les champs ne transforme en aucune manière la variable prop ou eVar utilisée pour lʼassemblage. Lʼassemblage basé sur les champs utilise la valeur du champ spécifié telle quʼelle existe après les règles VISTA et après les règles de traitement. Le processus dʼassemblage est sensible à la casse. Par exemple, si le mot « Bob » apparaît dʼabord dans la variable prop ou eVar, et que le mot « BOB » apparaît ensuite, ils seront considérés comme deux personnes distinctes par le processus dʼassemblage.
* Étant donné que lʼassemblage basé sur les champs est sensible à la casse, Adobe recommande de revoir les règles VISTA ou de traitement qui sʼappliquent à la variable prop ou eVar utilisée pour lʼassemblage basé sur les champs. Elles doivent être revues pour sʼassurer quʼaucune dʼelles nʼintroduit de nouvelles formes du même identifiant. Par exemple, vous devez vous assurer quʼaucune règle VISTA ou de traitement nʼintroduit de minuscules dans la variable prop ou eVar sur une partie seulement des accès.
* Lʼassemblage basé sur les champs ne prend pas en charge lʼutilisation de plusieurs variables prop ou eVar à des fins dʼassemblage. Par exemple, si la variable eVar12 contient un identifiant de connexion et la variable eVar20 une adresse électronique, vous devez choisir lʼune des deux.
* Lʼassemblage basé sur les champs ne combine ni ne concatène les champs (par exemple, eVar10 + prop5).
* La variable prop ou eVar ne doit contenir quʼun seul type dʼidentifiant. Par exemple, la variable prop ou eVar ne doit pas contenir une combinaison dʼidentifiants de connexion et dʼadresses électroniques.
* Si plusieurs accès se produisent à la même date et heure pour le même visiteur, mais avec des valeurs différentes dans la variable dʼassemblage prop ou eVar, les CDA effectueront leur sélection en fonction de lʼordre alphabétique. Ainsi, si le visiteur A a deux accès à la même date et à la même heure et que lʼun des accès mentionne Bob et lʼautre Anne, les CDA sélectionneront Anne.


## Étapes suivantes

Une fois que toutes les conditions requises sont remplies et que vous avez compris les limites, vous pouvez commencer à [configurer les analyses entre appareils](setup.md).
