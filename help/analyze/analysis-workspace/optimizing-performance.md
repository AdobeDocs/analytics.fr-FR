---
description: valeur nulle
seo-description: valeur nulle
seo-title: Optimisation des performances de l'espace de travail d'analyse
title: Optimisation des performances de l'espace de travail d'analyse
uuid: de 51 d 03 d-d 555-4 f 0 e-b 19 c -4 a 8 f 140770 fc
translation-type: tm+mt
source-git-commit: 9cd6a17db45c139765bea70fa27f37526334bcd0

---


# Optimisation des performances de l'espace de travail d'analyse

Certains facteurs peuvent influencer les performances d’un projet dans Analysis Workspace. Il convient de savoir quels sont ces facteurs avant de démarrer un projet, afin de planifier et d’élaborer le projet d’une manière optimale. Vous trouverez ci-dessous une liste des facteurs influençant les performances, ainsi que des bonnes pratiques pour optimiser vos projets. Adobe accorde une importance particulière aux performances d’Analysis Workspace et s’efforce continuellement de les améliorer.

## Complexité de la logique du segment

Des segments complexes peuvent avoir un impact significatif sur la performance des projets. Les facteurs qui ajoutent une complexité à un segment (dans l'ordre décroissant de l'impact) incluent :

* Les opérateurs de type « contains », « contains any of », « matches », « starts with » ou « ends with »
* La segmentation séquentielle, en particulier lorsque des restrictions dimensionnelles (Within/After) sont utilisées
* Le nombre d’éléments de dimensions uniques dans les dimensions utilisées dans le segment (par exemple, Page = 'A' lorsque Page comporte 10 éléments uniques sera plus rapide que Page = 'A' lorsque la page a 100 000 éléments uniques)
* Le nombre de dimensions différentes utilisées (par exemple, Page = 'Home' et Page = 'Search results' seront plus rapides que eVar 1 = 'red' et eVar 2 = 'blue')
* Beaucoup d’opérateurs OR (au lieu de AND)
* Les conteneurs imbriqués qui varient selon la portée (ex. : Accès au sein de la « Visite » à l'intérieur de « Visiteur »).

**Recommandations relatives à la complexité logique**

Bien qu’il soit impossible d’éviter certains facteurs de complexité, pensez aux possibilités de réduire la complexité de vos segments. En général, plus vous pouvez être précis dans vos critères de segment, mieux c’est. Par exemple :

* Avec les conteneurs, l’utilisation d’un seul conteneur en haut du segment sera plus rapide qu’une série de conteneurs imbriqués.
* Avec les opérateurs, « égal » est plus rapide que « contient » et « égal à » sera plus rapide que « contient un des ».
* Avec de nombreux critères, les opérateurs AND seront plus rapides qu’une série d’opérateurs OR. Recherchez également les opportunités de réduire de nombreuses instructions OU dans un seul relevé « égal à ».

En outre, l’utilisation de [classifications](/help/components/c-classifications2/c-classifications.md) peut contribuer à consolider de nombreuses valeurs en groupes concis à partir desquels vous pouvez créer des segments. La segmentation appliquée aux groupes de classifications optimise les performances par rapport aux segments qui contiennent de nombreuses instructions OU ou de critères « contient ».

## Plage de données demandée

La plage de données demandée lors d’un projet influence les performances d’Analysis Workspace.

**Recommandations relatives à la plage de données**

Si possible, n’extrayez que les données dont vous avez besoin.

N’oubliez pas que les plages de dates (composants violets) sont prioritaires sur la plage de dates du panneau. Si, par conséquent, vous utilisez d’autres plages de dates comme colonnes (par exemple, le mois dernier, la semaine dernière et hier), la plage de dates du panneau n’a pas à couvrir toutes les plages de dates des colonnes. Il suffit qu’elle soit définie sur « hier », puisque les plages de données utilisées dans le tableau à structure libre ont priorité sur celles du panneau. Pour en savoir plus sur l’utilisation des plages de dates dans Analysis Workspace, [regardez cette vidéo](https://www.youtube.com/watch?v=ybmv6EBmhn0) .

Use [date comparison options](../../analyze/analysis-workspace/components/calendar-date-ranges/time-comparison.md#concept_93BCAD81B7A54ABBBA5CD9E419F6F764) to pull in the specific time periods of data you want to compare. Si, par exemple, vous devez comparer les données du mois dernier à celles du même mois l’année précédente, utilisez simplement l’option de comparaison des périodes pour afficher les performances d’une année sur l’autre, plutôt que de définir les 13 derniers mois de données dans le panneau.

## Nombre de visualisations

Le nombre de visualisations graphiques contenues dans un projet affecte la réactivité globale d’Analysis Workspace.

**Meilleure pratique pour le nombre de visualisations**

Réduisez le nombre de visualisations dans votre projet. Pour chaque visuel que vous ajoutez, Analysis Workspace exécute un traitement conséquent en arrière-plan. Par conséquent, donnez la priorité aux visuels les plus importants pour l’utilisateur du rapport et, si nécessaire, répartissez les visuels connexes dans un projet distinct plus détaillé.

## Complexité des visualisations (segments, mesures, filtres)

Le type de visualisation (abandons ou tableau à structure libre) ajouté à un projet n’a pas de réelle incidence sur les performances du projet. Le temps de traitement dépend de la complexité de la visualisation. Voici quelques-uns des facteurs qui rendent une visualisation plus complexe :

* Plage de données demandée, comme mentionné ci-dessus
* Nombre de segments appliqués ; par exemple, les segments utilisés comme des lignes d’un tableau à structure libre
* Utilisation de segments complexes
* Lignes ou colonnes de postes statiques dans les tableaux de forme libre
* Filtres appliqués aux lignes des tableaux à structure libre
* Nombre de mesures incluses, en particulier les mesures calculées qui utilisent des segments

**Meilleure pratique pour la complexité de visualisation**

Si vos projets ne se chargent pas aussi rapidement que prévu, remplacez si possible certains segments par des eVars et des filtres.

Si vous utilisez constamment des segments et des mesures calculées pour les points de données importants dans le cadre de vos activités, envisagez d’améliorer votre mise en œuvre afin de capturer plus directement ces points de données. L'utilisation d'un gestionnaire de balises comme le lancement d'Adobe Experience Platform et les règles de traitement d'Adobe peut rendre les modifications d'implémentation rapides et faciles à mettre en œuvre. Pour mieux comprendre comment simplifier des segments complexes, reportez-vous à « Complexité de la logique de segment » ci-dessus.

## Nombre de panneaux

Un panneau peut contenir de nombreuses visualisations. Par conséquent, le nombre de panneaux peut également influencer la réactivité globale d'Analysis Workspace.

**Meilleure pratique pour le nombre de panneaux**

N’ajoutez rien à un projet. Créez plutôt des projets distincts ayant un objectif ou un groupe de participants spécifique. À l’aide des balises, classez les projets par thèmes clés et partagez avec les groupes de participants les projets connexes. 

Si vous devez classer davantage les projets, vous pouvez [lier directement](https://www.youtube.com/watch?v=6IOEewflG2U) votre projet. Créez un index interne des projets, de sorte que les participants puissent facilement trouver ce qu’ils recherchent.

Si vous devez ajouter de nombreux panneaux dans un espace de travail, réduisez-les avant d’enregistrer et de partager le projet. Quand un projet est chargé, Analysis Workspace charge seulement le contenu correspondant aux panneaux développés. Les panneaux réduits ne sont pas chargés tant que l’utilisateur ne les développe pas. Cette approche présente deux avantages :

* le temps de chargement général d’un projet est optimisé ; 
* grâce aux panneaux réduits, organisez vos projets de manière logique pour l’utilisateur du rapport.

## Taille de la suite de rapports

Même si la taille de la suite de rapports peut sembler être un facteur capital, son rôle en matière de performances du projet est en réalité mineur, en raison de la façon dont Adobe traite les données.

## Nombre d'utilisateurs accédant simultanément à Analysis Workspace

Le nombre d'utilisateurs accédant à Analysis Workspace ou à des projets spécifiques ne joue pas un rôle important sur les performances d'Analysis Workspace, si les utilisateurs accèdent à différentes suites de rapports. Si les utilisateurs simultanés accèdent à la même suite de rapports, les performances seront affectées.

## Messages d'erreur courants dans Analysis Workspace

Vous pouvez rencontrer des erreurs lors de l'interaction avec Analysis Workspace. Des erreurs peuvent se produire pour plusieurs raisons et énumérées ci-dessous sont les plus courantes.

| Message d'erreur | Pourquoi cela se produit-il ? |
|---|---|
| `The report suite is experiencing unusually heavy reporting. Please try again later.` | Votre entreprise essaie d'exécuter trop de requêtes simultanées par rapport à une suite de rapports spécifique. Les contributeurs à cette erreur sont les demandes d'API, les projets planifiés, les rapports planifiés, les alertes planifiées et les utilisateurs simultanés qui génèrent des requêtes de rapport. Nous vous recommandons de répartir les requêtes et les planifications de la suite de rapports de manière plus uniforme tout au long de la journée. |
| `A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.` | Adobe rencontre un problème qui doit être résolu. Nous vous recommandons d'envoyer le code d'erreur par le biais d'une demande d'assistance clientèle. |
| `The request is too complex.` | Votre requête de rapport est trop volumineuse et ne peut pas être exécutée. Les contributeurs à cette erreur sont des dépassements de délai dus à la taille de la requête, trop d'éléments correspondants dans un segment ou un filtre de recherche, trop de mesures incluses, des combinaisons de dimension et de mesure incompatibles, etc. Nous vous recommandons de simplifier votre requête. |
| `One of the segments or the search in this visualization contains a text search that returned too many results.` | Nous vous recommandons de limiter les critères de texte de recherche et d'essayer de nouveau la requête. |
| `This dimension does not currently support non-default attribution models.` | Il est recommandé de remplacer la dimension dans votre tableau par celle qui est compatible avec [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution.html). |
| `Your request failed as a result of too many columns or pre-configured rows.` | Il est recommandé de supprimer certaines des colonnes ou des lignes ou de les diviser en visualisations distinctes. |
