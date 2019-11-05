---
description: valeur nulle
seo-description: valeur nulle
seo-title: Optimisation des performances d’Analysis Workspace
title: Optimisation des performances d’Analysis Workspace
uuid: de51d03d-d555-4f0e-b19c-4a8f140770fc
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Optimisation des performances d’Analysis Workspace

Certains facteurs peuvent influencer les performances d’un projet dans Analysis Workspace. Il est important de savoir ce que sont ces contributeurs avant de commencer à construire un projet afin que vous puissiez planifier et construire le projet de la manière la plus optimale. Vous trouverez ci-dessous une liste des facteurs influençant les performances, ainsi que des bonnes pratiques pour optimiser vos projets. Les performances d’Analysis Workspace sont l’une des principales priorités d’Adobe et nous continuons à les améliorer chaque jour.

## Complexité de la logique de segment

Des segments complexes peuvent avoir un impact significatif sur la performance des projets. Les facteurs qui rendent un segment plus complexe (dans l’ordre décroissant de l’impact) sont les suivants :

* Opérateurs de "contient", "contient l’un des", "correspond", "commence par" ou "se termine par"
* La segmentation séquentielle, en particulier lorsque des restrictions dimensionnelles (Within/After) sont utilisées
* Le nombre d’éléments de dimensions uniques dans les dimensions utilisées dans le segment (par exemple, Page = 'A' lorsque Page comporte 10 éléments uniques sera plus rapide que Page = 'A' lorsque la page a 100 000 éléments uniques)
* Le nombre de dimensions différentes utilisées (par exemple, Page = 'Home' et Page = 'Search results' seront plus rapides que eVar 1 = 'red' et eVar 2 = 'blue')
* Beaucoup d’opérateurs OR (au lieu de AND)
* Conteneurs imbriqués dont la portée varie (par exemple, "Accès" à l’intérieur de "Visite" à l’intérieur de "Visiteur")

**Meilleures pratiques pour la complexité logique**

Bien qu’il soit impossible d’éviter certains facteurs de complexité, pensez aux possibilités de réduire la complexité de vos segments. En général, plus vous pouvez être précis dans vos critères de segment, mieux c’est. Par exemple :

* Avec les conteneurs, l’utilisation d’un seul conteneur en haut du segment sera plus rapide qu’une série de conteneurs imbriqués.
* Avec les opérateurs, "est égal à" sera plus rapide que "contient" et "est égal à n’importe lequel" sera plus rapide que "contient aucun de".
* Avec de nombreux critères, les opérateurs AND seront plus rapides qu’une série d’opérateurs OR. De plus, recherchez des opportunités pour réduire plusieurs instructions OU en une seule instruction "est égal à n’importe laquelle".

En outre, l’utilisation de [classifications](/help/components/c-classifications2/c-classifications.md) peut contribuer à consolider de nombreuses valeurs en groupes concis à partir desquels vous pouvez créer des segments. La segmentation sur les groupes de classification offre des avantages sur les segments qui contiennent de nombreuses instructions OU ou des critères "contient".

## Plage de données demandée

La plage de données demandée lors d’un projet influence les performances d’Analysis Workspace.

**Meilleures pratiques pour la plage de données**

Dans la mesure du possible, n'extrayez pas plus de données que nécessaire.

N’oubliez pas que les plages de dates (composants violets) sont prioritaires sur la plage de dates du panneau. Si, par conséquent, vous utilisez d’autres plages de dates comme colonnes (par exemple, le mois dernier, la semaine dernière et hier), la plage de dates du panneau n’a pas à couvrir toutes les plages de dates des colonnes. Il suffit qu’elle soit définie sur « hier », puisque les plages de données utilisées dans le tableau à structure libre ont priorité sur celles du panneau. Pour en savoir plus sur l’utilisation des plages de dates dans Analysis Workspace, [regardez cette vidéo](https://www.youtube.com/watch?v=ybmv6EBmhn0) .

Use [date comparison options](/help/analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md) to pull in the specific time periods of data you want to compare. Si, par exemple, vous devez comparer les données du mois dernier à celles du même mois l’année précédente, utilisez simplement l’option de comparaison des périodes pour afficher les performances d’une année sur l’autre, plutôt que de définir les 13 derniers mois de données dans le panneau.

## Nombre de visualisations

Le nombre de visualisations graphiques contenues dans un projet affecte la réactivité globale d’Analysis Workspace.

**Meilleure pratique pour le nombre de visualisations**

Réduisez le nombre de visualisations dans votre projet. Pour chaque visuel que vous ajoutez, Analysis Workspace exécute un traitement conséquent en arrière-plan. Par conséquent, donnez la priorité aux visuels les plus importants pour l’utilisateur du rapport et, si nécessaire, répartissez les visuels connexes dans un projet distinct plus détaillé.

## Complexité des visualisations (segments, mesures, filtres)

Le type de visualisation (par exemple, abandon par rapport à un tableau à structure libre) ajouté à un projet en lui-même n’influe pas beaucoup sur les performances du projet. Le temps de traitement dépend de la complexité de la visualisation. Voici quelques-uns des facteurs qui rendent une visualisation plus complexe :

* Plage de données demandée, comme mentionné ci-dessus
* Nombre de segments appliqués ; par exemple, les segments utilisés comme des lignes d’un tableau à structure libre
* Utilisation de segments complexes
* Lignes ou colonnes de postes statiques dans les tableaux de forme libre
* Filtres appliqués aux lignes des tableaux à structure libre
* Nombre de mesures incluses, en particulier les mesures calculées qui utilisent des segments

**Meilleure pratique pour la complexité de la visualisation**

Si vos projets ne se chargent pas aussi rapidement que prévu, remplacez si possible certains segments par des eVars et des filtres.

Si vous utilisez constamment des segments et des mesures calculées pour les points de données importants dans le cadre de vos activités, envisagez d’améliorer votre mise en œuvre afin de capturer plus directement ces points de données. L’utilisation d’un gestionnaire de balises tel qu’Adobe Experience Platform Launch et les règles de traitement d’Adobe permet de modifier rapidement et facilement l’implémentation. Pour mieux comprendre comment simplifier des segments complexes, reportez-vous à « Complexité de la logique de segment » ci-dessus.

## Nombre de panneaux

Un panneau peut contenir de nombreuses visualisations et, par conséquent, le nombre de panneaux peut également influencer la réactivité globale d’Analysis Workspace.

**Meilleure pratique pour le nombre de panneaux**

N'essayez pas d'ajouter tout dans un seul projet, mais plutôt de créer des projets distincts qui servent un but spécifique ou un groupe d'intervenants. À l’aide des balises, classez les projets par thèmes clés et partagez avec les groupes de participants les projets connexes. 

Si vous devez classer davantage les projets, vous pouvez [lier directement](https://www.youtube.com/watch?v=6IOEewflG2U) votre projet. Créez un index interne des projets, de sorte que les participants puissent facilement trouver ce qu’ils recherchent.

Si vous devez ajouter de nombreux panneaux dans un espace de travail, réduisez-les avant d’enregistrer et de partager le projet. Quand un projet est chargé, Analysis Workspace charge seulement le contenu correspondant aux panneaux développés. Les panneaux réduits ne sont pas chargés tant que l’utilisateur ne les développe pas. Cette approche présente deux avantages :

* le temps de chargement général d’un projet est optimisé ; 
* grâce aux panneaux réduits, organisez vos projets de manière logique pour l’utilisateur du rapport.

## Taille de la suite de rapports

Même si la taille de la suite de rapports peut sembler être un facteur capital, son rôle en matière de performances du projet est en réalité mineur, en raison de la façon dont Adobe traite les données.

## Nombre d’utilisateurs accédant simultanément à Analysis Workspace

Le nombre d’utilisateurs accédant simultanément à Analysis Workspace ou à des projets spécifiques n’a pas d’effet important sur les performances d’Analysis Workspace si les utilisateurs accèdent à différentes suites de rapports. Si des utilisateurs simultanés accèdent à la même suite de rapports, les performances sont affectées.

## Messages d’erreur courants dans Analysis Workspace

Vous pouvez rencontrer des erreurs lors de l’interaction avec Analysis Workspace. Les erreurs peuvent se produire pour plusieurs raisons. Les erreurs répertoriées ci-dessous sont les plus courantes.

| Message d’erreur | Pourquoi cela se produit-il ? |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | Votre entreprise essaie d'exécuter trop de requêtes simultanées sur une suite de rapports spécifique. Les contributeurs à cette erreur sont les demandes d’API, les projets planifiés, les rapports planifiés, les alertes planifiées et les utilisateurs simultanés qui effectuent des demandes de création de rapports. Nous vous recommandons de répartir plus uniformément vos demandes et vos calendriers pour la suite de rapports tout au long de la journée. |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | Adobe rencontre un problème qui doit être résolu. Nous vous recommandons d’envoyer le code d’erreur via une demande du service à la clientèle. |
| `The request is too complex.` | Votre requête de création de rapports est trop volumineuse et ne peut pas être exécutée. Les contributeurs à cette erreur sont les dépassements de délai en raison de la taille de la requête, du nombre trop élevé d’éléments correspondants dans un segment ou un filtre de recherche, du nombre trop élevé de mesures incluses, des combinaisons de dimensions et de mesures incompatibles, etc. Nous vous recommandons de simplifier votre requête. |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | Nous vous recommandons de limiter vos critères de recherche de texte et de réessayer la requête. |
| `This dimension does not currently support non-default attribution models.` | Nous vous recommandons de remplacer la dimension de votre tableau par une dimension compatible avec le QI [](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html)d’attribution. |
| `Your request failed as a result of too many columns or pre-configured rows.` | Nous vous recommandons de supprimer certaines colonnes ou lignes ou de les diviser en visualisations distinctes. |
