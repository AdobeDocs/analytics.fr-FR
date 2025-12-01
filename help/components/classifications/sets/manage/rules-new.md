---
title: Règles des ensembles de classifications
description: Découvrez comment utiliser les règles des jeux de classifications pour définir des règles pour les données de classification.
feature: Classifications
hide: true
hidefromtoc: true
source-git-commit: bccb3409875336a092ab641ad69b866b43621984
workflow-type: tm+mt
source-wordcount: '1530'
ht-degree: 13%

---


# Règles des ensembles de classifications

Vous utilisez des règles pour prendre en charge les classifications automatiques dans les scénarios où votre dimension clé change constamment. La mise à jour des classifications par chargement ou automatisation devient un processus laborieux ou prend du retard par rapport à la classification appropriée des nouvelles valeurs de dimension. Par exemple, les campagnes internes, les codes de suivi ou les SKU de produit. La dimension doit contenir des valeurs qui vous permettent d’appliquer une ou plusieurs règles afin que vous puissiez dériver des données de classification des valeurs.

Vous définissez des règles dans le contexte d’un ensemble de classifications, ce qui implique que les règles sont appliquées (lorsqu’elles sont activées) à toutes les combinaisons de suites de rapports et de dimensions clés auxquelles vous êtes abonné. Cette implémentation est quelque peu différente du fonctionnement de l’ancien créateur de règles de classification. Dans le créateur de règles de classification, vous définissez séparément une ou plusieurs règles dans le cadre d’un jeu de règles, puis vous associez le jeu de règles à une ou plusieurs suites de rapports. Dans la nouvelle interface, les règles de l’ensemble de classifications sont également appelées ensemble de règles, mais sont définies dans la même interface que celle dans laquelle vous configurez d’autres attributs d’ensemble de classifications.


Pour définir un ensemble de règles pour un ensemble de classifications, procédez comme suit :

1. Sélectionnez **[!UICONTROL Composants]** dans la barre de menus supérieure d’Adobe Analytics, puis sélectionnez **[!UICONTROL Ensembles de classifications]**.
1. Dans **[!UICONTROL Ensembles de classifications]**, sélectionnez l’onglet **[!UICONTROL Ensembles de classifications]**.
1. Dans le gestionnaire **[!UICONTROL Ensembles de classifications]**, sélectionnez l’ensemble de classifications pour lequel vous souhaitez définir les règles.
1. Dans la boîte de dialogue **[!UICONTROL Ensemble de classifications : _nom de l’ensemble de classifications_]**, sélectionnez l’onglet **[!UICONTROL Règles]**.

   * Si vous accédez à l’interface **[!UICONTROL Rules]** pour la première fois pour un ensemble de classifications, ou si vous avez décidé jusqu’à présent de continuer à utiliser l’interface héritée du créateur de règles, une boîte de dialogue s’affiche et vous permet de sélectionner la manière de commencer. Les options sont les suivantes :

      * **Migration des règles existantes**. Importez vos règles de classification actuelles et continuez à travailler avec ces règles dans la nouvelle interface. Vos règles existantes seront conservées et converties au nouveau format.
         * Sélectionnez **[!UICONTROL Migrer les règles]** pour continuer.
         * Dans la boîte de dialogue **[!UICONTROL Confirmer la migration]**, lisez les implications de la migration.
            * Sélectionnez **[!UICONTROL Migrer les règles]** pour confirmer la migration. Une fois la migration terminée, utilisez l’interface [Ensemble de règles](#rule-set-interface) pour créer de nouvelles règles et modifier vos règles migrées existantes.
            * Sélectionnez **[!UICONTROL Annuler]** pour annuler la migration

      * **Recommencer**. Créez de toutes pièces des règles de classification à l’aide du nouveau créateur de règles. Sélectionnez cette option si vous souhaitez reconcevoir votre logique de classification ou repartir de zéro avec de nouvelles règles de classification.
         * Sélectionnez **[!UICONTROL Créer de nouvelles règles]** pour continuer.
         * Dans la boîte de dialogue **[!UICONTROL Confirmer le nouveau démarrage]**, lisez les implications d’un nouveau démarrage.
            * Sélectionnez **[!UICONTROL Démarrer à nouveau]** pour confirmer un nouveau démarrage et ignorer les règles existantes. Utilisez l’interface [Ensemble de règles](#rule-set-interface) pour créer des règles.
            * Sélectionnez **[!UICONTROL Annuler]** pour annuler.


      * **Utiliser l’interface héritée**. Continuez à utiliser l’interface précédente du créateur de règles. Vous pouvez migrer vers la nouvelle expérience à tout moment lorsque vous êtes prêt(e).
         * Sélectionnez **[!UICONTROL Accéder à l’interface héritée]** pour continuer. Vous accédez à l’interface héritée **[!UICONTROL Créateur de règles de classification]**.

   * Si vous avez déjà migré des règles ou créé de nouvelles règles pour un ensemble de classifications, vous accédez directement à l’interface Ensemble de règles .



## Interface de l’ensemble de règles

Lorsque vous créez ou modifiez des règles, vous utilisez l’interface d’ensemble de règles.

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

![&#x200B; Interface des règles &#x200B;](assets/rule-ui.png)

| | Description |
|---|---|
| 1 | Nom de la fonction sélectionnée et entrée saisie pour la fonction. |
| 2 | Entrée de la fonction sélectionnée. L’entrée dépend de la fonction sélectionnée. Par exemple, pour la fonction Expression régulière, l’entrée est une expression régulière et pour la fonction Partage, l’entrée est un jeton. Saisissez l’entrée appropriée pour la fonction spécifique. Par exemple, `^(.+)\:(.+)\:(.+)$` une expression régulière qui identifie trois classifications dans un code de campagne interne. |
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

Vous souhaitez définir une règle pour affecter automatiquement des `Email` en tant que valeur à la classification **[!UICONTROL Canal]** lorsque la valeur de la dimension clé Campagne interne commence par `em` (par exemple : `em:FY2025:Summer Sale`).

![Règle - Commence Par](assets/rule-startswith.png)

+++



### Se Termine Par...

Définit une classification basée sur une valeur spécifique à laquelle se termine la dimension de clé.

+++ Détails 

#### Entrée requise

Saisissez une valeur pour **[!UICONTROL Se termine par]**. Par exemple : `Sale`.

#### Cas d’utilisation

Vous souhaitez définir une règle pour affecter automatiquement des `Sale` en tant que valeur à la classification **[!UICONTROL Type]** lorsque la valeur de la dimension clé Campagne interne contient des `Sale` (par exemple : `em:FY2025:Summer Sale`).

![Règle - Se Termine Par](assets/rule-endswith.png)

+++


### Contient...

Définit une classification en fonction d’une valeur spécifique que la dimension de clé contient.

+++ Détails 

#### Entrée requise

Saisissez une valeur pour **[!UICONTROL Contient]**. Par exemple : `2025`.

#### Cas d’utilisation

Vous souhaitez définir une règle pour affecter automatiquement des `2025` en tant que valeur à la classification **[!UICONTROL Année]** lorsque la valeur de la dimension clé Campagne interne se termine par `2025` (par exemple : `em:FY2025:Summer Sale`).

![&#x200B; Règle - Contient &#x200B;](assets/rule-contains.png)

+++


### Correspond à

Définit une classification en fonction d’une valeur spécifique à laquelle la dimension clé correspond.

+++ Détails 

#### Entrée requise

Saisissez une valeur pour **[!UICONTROL Correspondance]**. Par exemple : `em:FY2025:Summer`.

#### Cas d’utilisation

Vous souhaitez définir une règle pour affecter automatiquement des `2025 Summer Email` en tant que valeur à la classification **[!UICONTROL Type]** lorsque la valeur de la dimension clé Campagne interne correspond `em:FY2025:Summer`.

![Règle - Correspond](assets/rule-match.png)

+++


### Expression régulière

Définit une ou plusieurs classifications en fonction d’une expression régulière appliquée à la valeur de dimension clé.

+++ Détails 

#### Entrée requise

Saisissez une valeur pour **[!UICONTROL Expression régulière]**. Par exemple : `^(.+)\:(.+)\:(.+)$`.

#### Cas d’utilisation

Vous souhaitez définir une règle pour affecter automatiquement des valeurs aux classifications **[!UICONTROL Canal]**, **[!UICONTROL Type]** et **[!UICONTROL Année]** en appliquant le `^(.+)\:(.+)\:(.+)$` d’expression régulière et en utilisant des groupes de correspondance (`$1`, `$2` et `$3`) aux valeurs de la dimension clé Campagne interne.

![Règle - Expression régulière &#x200B;](assets/rule-regex.png)


#### Tableau de référence {#section_0211DCB1760042099CCD3ED7A665D716}

| Expression régulière | Description |
|---|---|
| `(?ms)` | Rend toute l’expression régulière correspondant à une entrée à plusieurs lignes, permettant au caractère générique correspondant à n’importe quel caractère de saut de page |
| `(?i)` | Fait en sorte que toute l’expression régulière ne respecte pas la casse |
| `[abc]` | N’importe quel caractère parmi a, b ou c |
| `[^abc]` | N’importe quel caractère sauf a, b ou c |
| `[a-z]` | N’importe quel caractère entre a et z |
| `[a-zA-Z]` | N’importe quel caractère entre a et z ou A et Z |
| `^` | Début de ligne (correspond au début de la ligne) |
| `$` | Correspondance avec la fin de la ligne (ou avant la nouvelle ligne à la fin) |
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


## Priorité de la règle

Si une valeur de dimension de clé est mise en correspondance avec plusieurs règles et que les ensembles de règles contiennent des règles avec la même opération Définir la classification , la dernière règle détermine la valeur de la classification. Vous devez donc classer l’opération Définir la classification la plus importante dans le cadre de la dernière règle de votre ensemble de règles.

Si vous créez plusieurs règles qui ne partagent pas la même opération Définir la classification, l’ordre de traitement n’a pas d’importance.


### Exemple

Vous souhaitez classer avec la classification **[!UICONTROL Type]** la manière dont les utilisateurs recherchent un athlète à l’aide de la chaîne de recherche comme dimension clé. Par exemple, en utilisant cet ensemble de règles :

![&#x200B; Priorité des règles &#x200B;](assets/rule-priority.png)

* Lorsqu’un utilisateur ou une utilisatrice recherche des `Cowboys Fantasy Tony Romo`, `Romo` est classé comme **[!UICONTROL Type]**.
* Lorsqu’un utilisateur ou une utilisatrice recherche `Cowboys Fantasy Tony Romeo`, `Fantasy` est classé comme **[!UICONTROL Type]**.
* Lorsqu’un utilisateur ou une utilisatrice recherche `Cowboys vs. Broncos`, `Team` est classé comme **[!UICONTROL Type]**.

