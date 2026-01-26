---
title: Règles des ensembles de classifications
description: Découvrez comment utiliser les règles des jeux de classifications pour définir des règles pour les données de classification.
feature: Classifications
source-git-commit: 1a07d14d11e3353c5f45fb26463168a75fe11ddf
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 13%

---


# Règles des ensembles de classifications

Vous utilisez des règles pour prendre en charge les classifications automatiques dans les scénarios où votre dimension clé change constamment. La mise à jour des classifications par le biais du [chargement](/help/components/classifications/sets/manage/schema.md#upload) ou de l’[automatisation](/help/components/classifications/sets/manage/schema.md#automate) devient un processus laborieux ou retarde la classification appropriée des nouvelles valeurs de dimension. Par exemple, les campagnes internes, les codes de suivi ou les SKU de produit.

La dimension doit contenir des valeurs qui vous permettent d’appliquer une ou plusieurs règles afin que vous puissiez dériver des données de classification des valeurs de dimension.

Vous définissez des règles dans le contexte d’un ensemble de classifications. Ce contexte implique que les règles sont appliquées (lorsqu’elles sont activées) à toutes les combinaisons de suites de rapports et de dimensions clés qui sont abonnées à l’ensemble de classifications. Cette implémentation est différente du fonctionnement de l’ancien créateur de règles de classification. Dans le créateur de règles de classification, définissez séparément une ou plusieurs règles dans le cadre d’un jeu de règles, puis associez le jeu de règles à une ou plusieurs suites de rapports. Dans la nouvelle interface, les règles de l’ensemble de classifications sont également appelées ensemble de règles. Toutefois, les ensembles de règles sont définis dans la même interface que celle où vous configurez d’autres attributs d’ensemble de classifications.


Pour définir un ensemble de règles pour un ensemble de classifications, procédez comme suit :

1. Sélectionnez **[!UICONTROL Composants]** dans la barre de menus supérieure d’Adobe Analytics, puis sélectionnez **[!UICONTROL Ensembles de classifications]**.
1. Dans **[!UICONTROL Ensembles de classifications]**, sélectionnez l’onglet **[!UICONTROL Ensembles de classifications]**.
1. Dans le gestionnaire **[!UICONTROL Ensembles de classifications]**, sélectionnez l’ensemble de classifications pour lequel vous souhaitez définir les règles.
1. Dans la boîte de dialogue **[!UICONTROL Ensemble de classifications : _nom de l’ensemble de classifications_]**, sélectionnez l’onglet **[!UICONTROL Règles]**.

   * Si vous accédez à l’interface **[!UICONTROL Rules]** pour la première fois pour un ensemble de classifications, ou si vous avez décidé jusqu’à présent de continuer à utiliser l’interface du créateur de règles héritée, une boîte de dialogue s’affiche et vous permet de sélectionner comment commencer. Les options sont les suivantes :

      * **Migration des règles existantes**. Importez vos règles de classification actuelles et continuez à travailler avec ces règles dans la nouvelle interface. Vos règles existantes sont conservées et converties au nouveau format.
         * Sélectionnez **[!UICONTROL Migrer les règles]** pour continuer.
         * Dans la boîte de dialogue **[!UICONTROL Confirmer la migration]**, lisez les implications de la migration.
            * Sélectionnez **[!UICONTROL Migrer les règles]** pour confirmer la migration. Une fois la migration terminée, utilisez l’interface [Ensemble de règles](#rule-set-interface) pour créer de nouvelles règles et modifier vos règles migrées existantes.
            * Sélectionnez **[!UICONTROL Annuler]** pour annuler la migration

      * **Recommencer**. Créez des règles de classification à partir de zéro à l’aide de notre nouveau créateur de règles. La solution idéale pour revoir votre logique de classification ou prendre un nouveau départ.
         * Sélectionnez **[!UICONTROL Créer de nouvelles règles]** pour continuer.
         * Dans la boîte de dialogue **[!UICONTROL Confirmer le nouveau démarrage]**, lisez les implications d’un nouveau démarrage.
            * Sélectionnez **[!UICONTROL Démarrer à nouveau]** pour confirmer un nouveau démarrage et ignorer les règles existantes. Utilisez l’interface [Ensemble de règles](#rule-set-interface) pour créer des règles.
            * Sélectionnez **[!UICONTROL Annuler]** pour annuler.


      * **Utiliser l’interface héritée**. Continuez à utiliser l’ancienne interface de création de règles. Vous pouvez migrer vers la nouvelle expérience à tout moment lorsque cela vous convient.
         * Sélectionnez **[!UICONTROL Accéder à l’interface héritée]** pour continuer. Vous accédez à l’interface héritée **[!UICONTROL Créateur de règles de classification]**.

   * Si vous avez déjà migré des règles ou créé de nouvelles règles pour un ensemble de classifications, vous accédez directement à l’interface Ensemble de règles .



## Interface de l’ensemble de règles {#rule-set-interface}

>[!CONTEXTUALHELP]
>id="classificationsets_rules_samplekeys"
>title="Exemples de clés"
>abstract="Saisissez ou collez des clés de test pour tester l’ensemble de règles. Chaque ligne est une valeur de clé distincte. Sélectionnez **[!UICONTROL Tester l’ensemble de règles]** pour afficher une boîte de dialogue avec les résultats."


Pour créer ou modifier des règles, utilisez l’interface Ensemble de règles .

![Interface du jeu de règles](assets/rulesets-ui.png)

| | Nom | Description |
|---|---|---|
| 1 | **[!UICONTROL Fonctions]** | Utilisez la zone **[!UICONTROL Fonctions]** pour sélectionner vos fonctions, puis faites-les glisser vers le créateur d’ensembles de règles. |
| 2 | **Créateur de jeux de règles** | Vous créez votre jeu de règles à l’aide d’une ou de plusieurs règles. Une règle est l’implémentation d’une fonction et est toujours associée à une seule fonction. Une fonction peut comporter plusieurs opérateurs et opératrices. Vous créez une règle en faisant glisser et en déposant une fonction dans le créateur d’ensembles de règles. Le type de fonction définit l’interface de la règle. <br/>Voir la section [Interface des règles](#rule-interface) pour plus d’informations.<br/>Vous pouvez insérer des fonctions n’importe où, et les fonctions sont exécutées en séquence pour déterminer les valeurs finales des classifications.<br/>Utilisez **[!UICONTROL Tout réduire]** pour réduire toutes les règles et **[!UICONTROL Tout développer]** pour développer toutes les règles. |
| 3 | **[!UICONTROL Statut]** | Affichez le statut et la date de dernière modification de l’ensemble de règles. <br/>Sélectionnez **[!UICONTROL Activer]** pour activer l’ensemble de règles. <br/>Sélectionnez **[!UICONTROL Désactiver]** pour désactiver l’ensemble de règles. |
| 4 | **[!UICONTROL Recherche en amont]** | Spécifiez l’intervalle de recherche en amont pour l’ensemble de règles.<br/>Sélectionnez une option (de 1 mois à 6 mois) dans le menu déroulant.<br/>Sélectionnez **[!UICONTROL Effectuer une recherche en amont]** pour effectuer une recherche en amont à l’aide de la période de recherche en amont sélectionnée. |
| 5 | **[!UICONTROL Options de test]** | Utilisez des exemples de valeurs de dimension clés pour tester les classifications : <ul><li>Ajoutez ou collez des valeurs dans la zone de texte **[!UICONTROL Exemples de clés]**.<br/>Cochez la case **[!UICONTROL Mémoriser les exemples de clés]** pour vous assurer que les exemples de clés persistent dans différentes utilisations de l’interface de l’ensemble de règles.</li><li>Sélectionnez **[!UICONTROL Tester l’ensemble de règles]** pour tester l’ensemble de règles.</li></ul> |


## Interface des règles

Vous définissez chaque règle individuelle dans le jeu de règles de l’interface Règle. L’interface se compose des éléments suivants :

![ Interface des règles ](assets/rule-ui.png)

| | Description |
|---|---|
| 1 | Nom de la fonction sélectionnée et entrée saisie pour la fonction. |
| 2 | Entrée de la fonction sélectionnée. L’entrée dépend de la fonction sélectionnée. Par exemple, pour la fonction **[!UICONTROL Expression régulière]**, l’entrée est une expression régulière. Et pour la fonction **[!UICONTROL Split]**, l’entrée est un jeton. Saisissez l’entrée appropriée pour la fonction spécifique. Par exemple, `^(.+)\:(.+)\:(.+)$` une expression régulière qui identifie trois classifications dans un code de campagne interne. |
| 3 | Chaque opération définit une classification spécifique sur une valeur. <br/>Sélectionnez une classification dans le menu déroulant **[!UICONTROL Définir la classification]** et saisissez une valeur pour **[!UICONTROL à]**. <br/>Utilisez ![CrossSize400](/help/assets/icons/CrossSize400.svg) pour supprimer une opération de la liste. |
| 4 | Sélectionnez ![Ajouter](/help/assets/icons/Add.svg) **[!UICONTROL Ajouter une opération]** pour ajouter une opération supplémentaire à la fonction. |
| 5 | Sélectionnez ![ChevronDown](/help/assets/icons2/ChevronDown.svg) pour réduire la règle. Sélectionnez ![ChevronLeft](/help/assets/icons/ChevronLeft.svg) pour développer la règle.<br/>Sélectionnez ![CrossSize400](/help/assets/icons/CrossSize400.svg) pour supprimer la règle. |

## Référence de fonction

Pour chaque fonction prise en charge, trouvez des détails ci-dessous sur l’entrée requise et des exemples de cas d’utilisation.


### Commence Par...

Définit une classification basée sur une valeur spécifique avec laquelle la dimension clé commence.

+++ Détails 

#### Entrée requise

Saisissez une valeur pour **[!UICONTROL Commence par]**. Par exemple : `em`.

#### Cas d’utilisation

Vous souhaitez définir une règle pour affecter la `Email` comme valeur de la classification **[!UICONTROL Canal]** lorsque la valeur de la dimension clé Campagne interne commence par `em` (par exemple : `em:FY2025:Summer Sale`).

>[!BEGINTABS]

>[!TAB Règle ]

![Règle - Commence Par](assets/rule-startswith.png)

>[!TAB Résultats du test]

![Règle - Commence Par Les Résultats Du Test](assets/rule-startswith-test.png)

>[!ENDTABS]

+++



### Se Termine Par...

Définit une classification basée sur une valeur spécifique à laquelle se termine la dimension de clé.

+++ Détails 

#### Entrée requise

Saisissez une valeur pour **[!UICONTROL Se termine par]**. Par exemple : `2025`.

#### Cas d’utilisation

Vous souhaitez définir une règle pour affecter la `2025` comme valeur à la classification **[!UICONTROL Year]** lorsque la valeur de la dimension clé Internal Campaign contient des `2025` (par exemple : `em:Summer Sale:FY2025`).

>[!BEGINTABS]

>[!TAB Règle ]

![Règle - Se Termine Par](assets/rule-endswith.png)

>[!TAB Résultats du test]

![Règle - Se Termine Par Les Résultats Du Test](assets/rule-endswith-test.png)

>[!ENDTABS]

+++


### Contient...

Définit une classification en fonction d’une valeur spécifique que la dimension de clé contient.

+++ Détails 

#### Entrée requise

Saisissez une valeur pour **[!UICONTROL Contient]**. Par exemple : `Winter`.

#### Cas d’utilisation

Vous souhaitez définir une règle pour affecter des `Winter Sale` en tant que valeur à la classification **[!UICONTROL Type]** lorsque la valeur de la dimension clé que contient Internal Campaign est `Winter` (par exemple : `fb:Winter:FY2024`).


>[!BEGINTABS]

>[!TAB Règle ]

![ Règle - Contient ](assets/rule-contains.png)

>[!TAB Résultats du test]

![Règle - Contient Des Résultats](assets/rule-contains-test.png)

>[!ENDTABS]

+++


### Correspond à 

Définit une classification basée sur une valeur spécifique qui correspond à la valeur de la dimension clé.

+++ Détails 

#### Entrée requise

Saisissez une valeur pour **[!UICONTROL Correspond]**. Par exemple : `em:Summer:2025`.

#### Cas d’utilisation

Vous souhaitez définir une règle pour affecter des `Email` en tant que valeur à la classification **[!UICONTROL Canal]**, `Summer Sale` en tant que valeur à la classification **[!UICONTROL Type]** et `2025` à la classification **[!UICONTROL Année]**. Mais uniquement lorsque la valeur de la dimension clé Campagne interne correspond à `em:Summer:2025`.


>[!BEGINTABS]

>[!TAB Règle ]

![Règle - Correspond](assets/rule-matches.png)

>[!TAB Résultats du test]

![Règle - Correspond](assets/rule-matches-test.png)

>[!ENDTABS]

+++


### Expression régulière

Définit une ou plusieurs classifications en fonction d’une expression régulière appliquée à la valeur de dimension clé.

+++ Détails 

#### Entrée requise

Saisissez une valeur pour **[!UICONTROL Expression régulière]**. Par exemple : `^(.+)\:(.+)\:FY(.+)$`.

#### Cas d’utilisation

Vous souhaitez définir une règle pour affecter des valeurs aux classifications **[!UICONTROL Canal]**, **[!UICONTROL Type]** et **[!UICONTROL Année]** en appliquant le `^(.+)\:(.+)\:FY(.+)$` d’expression régulière et en utilisant des groupes de correspondance (`$1`, `$2` et `$3`) aux valeurs de la dimension clé Campagne interne.

>[!BEGINTABS]

>[!TAB Règle ]

![Règle - Expression régulière ](assets/rule-regex.png)

>[!TAB Résultats du test]

![Règle - Résultats du test d’expression régulière](assets/rule-regex-test.png)

>[!ENDTABS]



#### Tableau de référence

Consultez ci-dessous un tableau de référence des expressions régulières.

| Expression régulière | Description |
|---|---|
| `(?ms)` | Faites correspondre l’ensemble de l’expression régulière par rapport à une entrée multiligne, ce qui permet au caractère générique `.` de correspondre à n’importe quel caractère de nouvelle ligne |
| `(?i)` | Faites correspondre l’expression régulière entière pour qu’elle ne respecte pas la casse |
| `[abc]` | N’importe quel caractère parmi a, b ou c |
| `[^abc]` | N’importe quel caractère sauf a, b ou c |
| `[a-z]` | N’importe quel caractère entre a et z |
| `[a-zA-Z]` | N’importe quel caractère entre a et z ou A et Z |
| `^` | Début de ligne (correspond au début de la ligne) |
| `$` | Correspond à la fin de la ligne (ou avant la nouvelle ligne à la fin) |
| `\A` | Début de chaîne. |
| `\z` | Fin de chaîne. |
| `.` | Correspondance avec n’importe quel caractère (sauf une nouvelle ligne) |
| `\s` | N’importe quel espace |
| `\S` | N’importe quel caractère sauf espace |
| `\d` | N’importe quel chiffre |
| `\D` | N’importe quel caractère non numérique |
| `\w` | N’importe quel caractère d’un mot (lettre, chiffre, caractère de soulignement) |
| `\W` | N’importe quel caractère n’appartenant pas à un mot |
| `\b` | N’importe quelle limite de mot |
| `(...)` | Acquérir tout ce qui est compris |
| `(a\b)` | a ou b |
| `a?` | Zéro ou un de : a |
| `a*` | Zéro ou plus de : a |
| `a+` | Un ou plus de : a |
| `a{3}` | Exactement 3 de : a |
| `a{3,}` | 3 ou plus de : a |
| `a{3,6}` | Entre 3 et 6 de : a |

+++


### Partage

Divise la valeur de la dimension clé, en fonction d’un jeton, en une ou plusieurs classifications.

+++ Détails

#### Entrée requise

Saisissez une valeur pour **[!UICONTROL Fractionner]**. Par exemple : `:`.

#### Cas d’utilisation

Vous souhaitez définir une règle qui fractionne les valeurs de la dimension clé Campagne interne vers les classifications **[!UICONTROL Canal]**, **[!UICONTROL Type]** et **[!UICONTROL Année]** en fonction du `:` **[!UICONTROL Jeton]**.

>[!BEGINTABS]

>[!TAB Règle ]

![Règle - Fractionner](assets/rule-split.png)

>[!TAB Résultats du test]

![Règle - Fractionner les résultats du test](assets/rule-split-test.png)

>[!ENDTABS]

+++

## Priorité de la règle

La dernière règle détermine la valeur de la classification si :

* Une valeur de dimension de clé est mise en correspondance avec plusieurs règles.
* L’ensemble de règles contient des règles avec la même opération **[!UICONTROL Définir la classification]**.

Vous devez donc classer l’opération **[!UICONTROL Définir la classification]** la plus importante dans le cadre de la dernière règle de votre ensemble de règles.

Si vous créez plusieurs règles qui ne partagent pas la même opération **[!UICONTROL Définir la classification]**, l’ordre de traitement n’a pas d’importance.


### Exemple

Vous souhaitez classer avec la classification **[!UICONTROL Type]** la manière dont les utilisateurs recherchent un athlète à l’aide de la chaîne de recherche comme dimension clé. Par exemple, en utilisant cet ensemble de règles :

![ Priorité des règles ](assets/rule-priority.png)

* Lorsqu’un utilisateur ou une utilisatrice recherche des `Cowboys Fantasy Tony Romo`, `Romo` est classé comme **[!UICONTROL Type]**.
* Lorsqu’un utilisateur ou une utilisatrice recherche des `Cowboys Fantasy Tony Romeo`, `Fantasy` est classé comme **[!UICONTROL Type]**.
* Lorsqu’un utilisateur ou une utilisatrice recherche des `Cowboys vs. Broncos`, `Team` est classé comme **[!UICONTROL Type]**.

