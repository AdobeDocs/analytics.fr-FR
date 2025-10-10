---
description: Les règles de traitement simplifient la collecte de données et gèrent le contenu lorsqu’il est envoyé pour la création de rapports.
subtopic: Processing rules
title: Règles de traitement - Aperçu
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 3%

---

# Règles de traitement - Aperçu

Les règles de traitement vous permettent de modifier la manière dont vos données sont collectées avant leur écriture dans une suite de rapports.

**[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > Sélectionner une suite de rapports > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de traitement]**

>[!WARNING]
>
>Les règles de traitement affectent directement la collecte de données et peuvent entraîner une perte de données si elles sont utilisées de manière incorrecte. Testez toujours les règles de traitement dans une suite de rapports de développement avant de les activer dans une suite de rapports de production afin de limiter les problèmes de qualité des données.

Les deux principaux cas d’utilisation des règles de traitement sont les suivants :

* **Utiliser le processus d’implémentation des variables de données contextuelles** : au lieu de définir directement des variables dans votre implémentation, vous pouvez utiliser [Variables de données contextuelles](/help/implement/vars/page-vars/contextdata.md) pour définir des paires clé/valeur. Par exemple, au lieu de définir :

  ```js
  s.eVar1 = "Robert Munch";
  s.eVar2 = "Books";
  s.eVar3 = "Youth";
  ```

  Vous pouvez plutôt définir :

  ```js
  s.contextData['author'] = "Robert Munch";
  s.contextData['section'] = "Books";
  s.contextData['genre'] = "Youth";
  ```

  Vous pouvez ensuite mapper les variables de données contextuelles aux dimensions et mesures souhaitées dans l’interface utilisateur d’Analytics.

  Lorsque vous communiquez avec les développeurs de votre organisation pour implémenter Analytics sur une propriété, l’utilisation de variables de données contextuelles simplifie le processus de communication. L’équipe de développement peut simplement implémenter chaque paire clé/valeur une fois, puis vous, en tant qu’administrateur/administratrice Analytics, pouvez vous assurer que les données se rendent à la variable d’implémentation correcte.

* **Modifier les données au fur et à mesure qu’elles sont collectées** : ce cas d’utilisation a un large éventail d’applications, telles que des correctifs temporaires pour la qualité des données ou pour aider à combler les lacunes d’implémentation. Voir [Cas d’utilisation des règles de traitement](pr-use-cases.md) pour plus d’informations et des exemples spécifiques.

## Autorisations

Les administrateurs de produit ont accès aux règles de traitement par défaut. Vous pouvez accorder l’accès aux règles de traitement à des non-administrateurs en les incluant dans un profil de produits qui inclut l’élément d’autorisation **[!UICONTROL Règles de traitement]**. Pour plus d’informations, voir [Autorisations de profil de produit pour les outils de suites de rapports](/help/admin/admin-console/permissions/report-suite-tools.md).

## Remarques concernant la création ou la modification de règles de traitement

Lors de la création ou de la modification des règles de traitement, tenez compte des points suivants :

* **Valeurs vides possibles** : lorsque vous créez une règle, tenez compte des cas où la valeur de remplacement est vide. Par exemple, si une règle remplace eVar1 par eVar2 et qu’eVar2 est vide, les deux variables sont masquées. Adobe recommande d’ajouter une condition qui vérifie une valeur de variable avant de l’utiliser pour remplacer une autre valeur.
* **Appliquer immédiatement à l’enregistrement** : les règles de traitement s’appliquent aux données collectées au moment de leur enregistrement. Elles ne s’appliquent pas rétroactivement aux données déjà collectées.
* **Ordre de traitement dans les règles** : si vous disposez de plusieurs règles de traitement, l’ordre dans lequel elles s’exécutent a son importance. Assurez-vous que si vous utilisez une variable donnée dans plusieurs règles, elles sont exécutées dans le bon ordre. Si vous remplacez eVar3 dans la règle 1, cette valeur eVar3 d’origine n’est disponible dans aucune règle suivante.
* **Ordre de traitement dans le pipeline de collecte de données** : consultez la section [Ordre de traitement des données dans Adobe Analytics](/help/technotes/processing-order.md) pour savoir où les règles de traitement s’appliquent dans le pipeline de collecte de données global.
* **Encodage** : utilisez le codage UTF-8 dans presque tous les cas.
* **Respect de la casse** : les comparaisons de chaînes dans les règles de traitement ne sont pas sensibles à la casse. Les valeurs de chaîne que vous utilisez pour remplacer des valeurs utilisent les mêmes règles que pour renseigner directement la variable.
* **Suite de rapports unique** : lorsque vous modifiez des règles de traitement, elles s’appliquent à une seule suite de rapports. La sélection de plusieurs suites de rapports dans le gestionnaire de suites de rapports vous force à sélectionner une seule suite de rapports. Une fois les règles de traitement souhaitées créées ou modifiées, vous pouvez [copier ces règles dans d’autres suites de rapports](pr-copy.md).
* **Aucune exclusion de données** : l’exclusion de données n’est pas une fonctionnalité prévue des règles de traitement. Envisagez d’utiliser [`abort`](/help/implement/vars/config-vars/abort.md) au niveau de la collecte de données ou utilisez [règles VISTA](/help/technotes/vista.md) une fois les données collectées.
* **Variables disponibles** : toutes les dimensions et mesures ne sont pas disponibles dans les règles de traitement. Consultez [Dimensions et mesures disponibles pour les règles de traitement](pr-variables.md) pour obtenir la liste complète des éléments pris en charge.
* **Nombre de règles autorisées** : chaque suite de rapports peut contenir jusqu’à 150 règles. Chaque règle peut contenir jusqu’à 30 conditions.

>[!MORELIKETHIS]
>
>![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Mappez les variables de données contextuelles en props et eVars avec des règles de traitement](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/implementation/implementation-basics/map-contextdata-variables-into-props-and-evars-with-processing-rules){target="_blank"}
