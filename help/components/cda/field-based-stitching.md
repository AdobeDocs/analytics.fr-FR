---
title: Groupement basé sur les champs
description: Comprenez les conditions préalables et les limites du groupement de données à l’aide du groupement basé sur les champs.
exl-id: 81f2768c-53c2-40b4-8d3b-8d3b94cd7318
feature: CDA
role: Admin
source-git-commit: de8977e7ed7bf6bf93f75f608db34a7a3520ada7
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 80%

---

# Groupement basé sur les champs

{{available-existing-customers}}

Analytics sur l’ensemble des appareils offre deux méthodes distinctes pour regrouper les données. Cette méthode repose sur une variable Analytics, telle qu’une [prop](/help/implement/vars/page-vars/prop.md) ou une [eVar](/help/implement/vars/page-vars/evar.md), pour contenir un identifiant de personne. Elle utilise cette variable comme base pour lier les appareils. Adobe recommande cette option de regroupement pour plus de transparence et de prévisibilité dans le suivi des visiteurs.

## Conditions préalables spécifiques au groupement basé sur les champs

Si vous envisagez d’implémenter les analyses entre appareils à l’aide du groupement basé sur les champs, les éléments suivants sont requis. Collaborez avec les équipes de votre entreprise et de votre compte Adobe pour vous assurer de respecter toutes les conditions suivantes.

>[!WARNING]
>
>Si vous ne remplissez pas toutes les conditions préalables requises, vous risquez de ne pas pouvoir activer les analyses entre appareils ou de ne pas obtenir de résultats satisfaisants lors du regroupement de données.

* Toutes les conditions préalables sont répertoriées dans la [page d’aperçu](overview.md).
* Votre implémentation doit définir une prop ou une eVar qui identifie de manière unique un individu chaque fois que cela est possible, par exemple lorsqu’un utilisateur se connecte ou ouvre un e-mail. Cette exigence s’applique à toutes les plateformes, y compris les applications mobiles si elles sont utilisées.<br/>Évitez d’attribuer une valeur par défaut à cette prop ou eVar. Lorsque 2 000 appareils différents ou plus se voient attribuer la même valeur par défaut, la personne est ajoutée à une liste de « personnes malveillantes » et ces événements sont ignorés de la suite de rapports virtuelle activée pour Analytics sur l’ensemble des appareils, ce qui entraîne une analyse erronée.
* Communiquez la variable d’identification souhaitée à l’équipe de votre compte Adobe lorsqu’elle est configurée pour le groupement basé sur les champs.

## Limites spécifiques au groupement basé sur les champs

* Lʼassemblage basé sur les champs fonctionne mieux sur les suites de rapports qui présentent un taux dʼidentification/dʼauthentification utilisateur élevé.
* Bien que les variables prop et eVar contiennent chacune des règles de traitement des caractères majuscules et minuscules à des fins de comptes rendus des performances, lʼassemblage basé sur les champs ne transforme en aucune manière la variable prop ou eVar utilisée pour lʼassemblage. Lʼassemblage basé sur les champs utilise la valeur du champ spécifié telle quʼelle existe après les règles VISTA et après les règles de traitement. Le processus dʼassemblage est sensible à la casse. Par exemple, si le mot « Bob » apparaît dʼabord dans la variable prop ou eVar, et que le mot « BOB » apparaît ensuite, ils seront considérés comme deux personnes distinctes par le processus dʼassemblage.
* Étant donné que lʼassemblage basé sur les champs est sensible à la casse, Adobe recommande de revoir les règles VISTA ou de traitement qui sʼappliquent à la variable prop ou eVar utilisée pour lʼassemblage basé sur les champs. Elles doivent être revues pour sʼassurer quʼaucune dʼelles nʼintroduit de nouvelles formes du même identifiant. Par exemple, vous devez vous assurer quʼaucune règle VISTA ou de traitement nʼintroduit de minuscules dans la variable prop ou eVar sur une partie seulement des accès.
* Lʼassemblage basé sur les champs ne prend pas en charge lʼutilisation de plusieurs variables prop ou eVar à des fins dʼassemblage. Par exemple, si la variable eVar12 contient un identifiant de connexion et la variable eVar20 une adresse e-mail, vous devez choisir lʼune des deux.
* Lʼassemblage basé sur les champs ne combine ni ne concatène les champs (par exemple, eVar10 + prop5).
* La variable prop ou eVar ne doit contenir quʼun seul type dʼidentifiant. Par exemple, la variable prop ou eVar ne doit pas contenir une combinaison dʼidentifiants de connexion et dʼadresses électroniques.
* Si plusieurs accès se produisent à la même date et heure pour le même visiteur, mais avec des valeurs différentes dans la variable dʼassemblage prop ou eVar, les CDA effectueront leur sélection en fonction de lʼordre alphabétique. Ainsi, si le visiteur A a deux accès à la même date et à la même heure et que lʼun des accès mentionne Bob et lʼautre Anne, les CDA sélectionneront Anne.


## Étapes suivantes

Une fois que toutes les conditions requises sont remplies et que vous avez compris les limites, vous pouvez commencer à [configurer les analyses entre appareils](setup.md).
