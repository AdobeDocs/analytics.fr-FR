---
description: Découvrez les segments séquentiels qui utilisent l’opérateur THEN pour définir une séquence de conditions de segment.
title: SequentialSegments
feature: Segmentation
exl-id: 2ac4e6db-3111-45e5-bedf-7d9b7b1ae352
source-git-commit: acc32dc1589a08c20eaf414cd6f1a760ec8e2a56
workflow-type: tm+mt
source-wordcount: '2375'
ht-degree: 5%

---

# Segments séquentiels

Vous créez des segments séquentiels à l’aide de l’opérateur logique [!UICONTROL Then] entre les composants, les conteneurs et les composants, ou les conteneurs. L’opérateur logique [!UICONTROL Then] implique qu’une condition de segment se produit, suivie d’une autre.

De plus, vous pouvez limiter les segments séquentiels à une durée, une granularité et un nombre spécifiques entre les points de contrôle à l’aide des opérateurs **[!UICONTROL Après]** et **[!UICONTROL Dans]**.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentation séquentielle](https://video.tv.adobe.com/v/25405?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

Un segment séquentiel comporte des [fonctionnalités de base](#basics) et des options supplémentaires que vous pouvez configurer pour ajouter plus de complexité au segment séquentiel :

![Segment séquentiel](assets/sequential-segment.gif)


## Concepts de base

Les principes de base de la création d’un segment séquentiel ne sont pas différents de la création d’un segment normal à l’aide du [créateur de segments](seg-build.md). Un segment standard devient automatiquement un segment séquentiel dès que vous sélectionnez l’opérateur **[!UICONTROL Then]** dans la définition principale ou dans l’un des conteneurs que vous utilisez dans le [créateur de segments](seg-build.md).

### Exemples

Les exemples ci-dessous illustrent la manière dont vous utilisez les segments séquentiels dans divers cas d’utilisation.

#### Séquence simple

Identifiez les visiteurs qui ont consulté une page, puis consulté une autre page. Les données au niveau de l’accès sont segmentées à l’aide de cette séquence. Indépendamment des visites de visiteurs précédentes, passées ou intermédiaires, ou de la durée ou du nombre de pages vues entre les visites.

![Les segments séquentiels incluent tout le monde](assets/sequence-include-everyone.png)

#### Séquence entre les visites

Identifier les visiteurs qui ont consulté une page au cours d’une visite, puis consulté une autre page au cours d’une autre visite. Pour différencier les visites, utilisez des conteneurs pour créer la séquence et définir le niveau ![Visite](/help/assets/icons/Visit.svg) **[!UICONTROL Visite]** pour chaque conteneur.

![Séquence du segment entre les visites](assets/sequence-filter-session.png)

#### Séquence de niveau mixte

Identifiez les visiteurs qui consultent deux pages pour un nombre indéterminé de visites, puis qui consultent une troisième page au cours d’une visite distincte. Là encore, utilisez des conteneurs pour créer la séquence et définir le niveau ![Visite](/help/assets/icons/Visit.svg) **[!UICONTROL Visite]** sur le conteneur qui définit la visite distincte.

![Segment de séquence avec visite finale distincte](assets/sequence-filter-final-session.png)

#### Séquence agrégée

Identifiez les visiteurs et visiteuses qui, lors de leur première visite, ont visité une page spécifique, puis ont visité ultérieurement d’autres pages. Pour différencier la séquence d’accès, utilisez des conteneurs afin de séparer la logique au niveau du conteneur ![WebPage](/help/assets/icons/WebPage.svg) **[!UICONTROL Visite]**.

![consultez les conteneurs d’agrégats](assets/session-aggregate-containers.png)


#### Imbrication d’une séquence

Identifier toutes les visites au cours desquelles un visiteur visite une page avant une autre, puis effectuer des visites de suivi qui impliquent deux autres pages. Par exemple, identifiez toutes les visites au cours desquelles un visiteur visite d’abord la page d’accueil, puis une page de catégorie 1, et qui comportent d’autres visites au cours desquelles les pages de catégorie 2 et de catégorie 3 sont visitées.

![séquence imbriquée](assets/sequence-nested.png)

## [!UICONTROL Après] et [!UICONTROL Dans]

Vous pouvez utiliser ![Horloge](/help/assets/icons/Clock.svg) **[!UICONTROL Après]** et ![Horloge](/help/assets/icons/Clock.svg) **[!UICONTROL Dans]** l’opérateur **[!UICONTROL Alors]** pour définir des [contraintes de temps](#time-constraints) ou [contraintes supplémentaires pour les accès, les visites ou les dimensions](#event-session-and-dimension-constraints).

### Contraintes de temps

Pour appliquer des contraintes de temps à l’opérateur **[!UICONTROL Then]** :

1. Sélectionnez ![ Horloge ](/help/assets/icons/Clock.svg).
1. Sélectionnez **[!UICONTROL Dans]** ou **[!UICONTROL Après]** dans le menu contextuel.
1. Spécifiez une période (**[!UICONTROL Minute]**, **[!UICONTROL Heure]**, jusqu’à **[!UICONTROL Années]**).
1. Sélectionnez le ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL *nombre *]**&#x200B;pour ouvrir une fenêtre contextuelle qui vous permet de saisir ou de spécifier un nombre à l’aide de&#x200B;**[!UICONTROL -]**&#x200B;ou&#x200B;**[!UICONTROL +]**.

Pour supprimer une contrainte de temps, utilisez ![CrossSize75](/help/assets/icons/CrossSize75.svg).

Le tableau ci-dessous explique plus en détail les opérateurs de contrainte de temps.

| Opérateurs | Description |
|--- |--- |
| **[!UICONTROL Après]** | L’opérateur [!UICONTROL After] est utilisé pour spécifier une limite minimale de temps entre deux points de contrôle. Lors de la définition des valeurs Après, le délai commence à courir lorsque le segment est appliqué. Par exemple, si l’opérateur [!UICONTROL After] est défini sur un conteneur pour identifier les visiteurs qui visitent la page A, mais ne reviennent pas sur la page B avant un jour, ce jour commence lorsque le visiteur quitte la page A.  Pour que le visiteur soit inclus dans le segment, un minimum de 1 440 minutes (un jour) doit s’écouler après avoir quitté la page A pour afficher la page B. |
| **[!UICONTROL Dans]** | L’opérateur [!UICONTROL Dans] est utilisé pour spécifier une limite de temps maximale entre deux points de contrôle. Par exemple, si l’opérateur [!UICONTROL Within] est défini sur un conteneur pour identifier les visiteurs qui visitent la page A, puis reviennent visiter la page B dans la journée, alors ce jour commence lorsque le visiteur quitte la page A. Pour être inclus dans le segment, le visiteur dispose d’une durée maximale d’un jour avant l’ouverture de la page B. Pour que le visiteur soit inclus dans le segment, l’ouverture de la page B doit avoir lieu dans un délai maximal de 1 440 minutes (un jour) après avoir quitté la page A pour afficher la page B. |
| **[!UICONTROL Après mais dans]** | Lors de l’utilisation des opérateurs [!UICONTROL After] et [!UICONTROL Within], les deux opérateurs commencent et se terminent en parallèle, et non de manière séquentielle. <br/>Par exemple, vous créez un segment dont le conteneur est défini sur : `After = 1 Week(s) and Within = 2 Week(s)`.<br/>Les conditions d’identification des visiteurs dans ce segment sont remplies uniquement entre une et deux semaines. Les deux conditions sont appliquées à partir de la première page vue. |


#### Exemples

Quelques exemples d’utilisation des contraintes de temps.

##### Opérateur [!UICONTROL After]

Identifiez les visiteurs qui ont visité une page, puis une autre page uniquement après deux semaines. Par exemple, les visiteurs et visiteuses qui ont visité la page d’accueil, mais les femmes | Chaussures page seulement après deux semaines.

![Séquence après](assets/sequence-after.png)

Si une page vue de l’Accueil est affichée le 1er juin 2024 à 00:01, une page vue est alors affichée pour les femmes | Les chaussures correspondent tant que cette page vue a lieu après le 15 juin 2024 00:01.

##### Opérateur [!UICONTROL Within]

Identifiez les visiteurs qui ont visité une page, puis une autre page dans les cinq minutes. Par exemple, les visiteurs et visiteuses qui ont visité la page d’accueil , puis les femmes | Page de chaussures dans les 5 minutes.

![Séquence dans](assets/sequence-within.png)

Si une page vue de l’Accueil se produit le 1er juin 2024 à 12 h 01, une page vue est alors affichée pour les femmes | Les chaussures correspondent si cette page vue est antérieure au 15 juin 2024 12:16.

##### Opérateur [!UICONTROL After] but [!UICONTROL Within]

Identifiez les visiteurs et visiteuses qui ont consulté une page, puis qui ont consulté une autre page après deux semaines, mais dans un délai d’un mois. Par exemple, les visiteuses qui ont consulté la page d’accueil d’, puis, après deux semaines et dans un délai d’un mois, les | Page Chaussures.

![Séquence après mais dans](assets/sequence-afterbutwithin.png)

Toutes les visiteuses qui accèdent à la page d’accueil le 1er juin 2024 et qui reviennent visiter les femmes | Page de chaussures après le 15 juin 2019 00:01, mais avant le 1er juillet 2019 pour le segment.


### Contraintes [!UICONTROL Accès], [!UICONTROL Visite] et [!UICONTROL Dimension]

Les contraintes ![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL After]** et ![Clock](/help/assets/icons/Clock.svg) **[!UICONTROL Within]** vous permettent non seulement de spécifier une contrainte de temps, mais aussi une contrainte d’accès, de visite ou de dimension. Sélectionnez **[!UICONTROL Accès(s)]** **[!UICONTROL Visite(s)]** ou **[!UICONTROL Autres dimensions]** ![ChevronRight](/help/assets/icons/ChevronRight.svg) **[!UICONTROL *Nom du Dimension *]**. Vous pouvez utiliser le champ [!UICONTROL *Rechercher*] pour rechercher une dimension.

#### Exemple

Vous trouverez ci-dessous un exemple de segment séquentiel recherchant les visiteurs qui ont visité une page de catégorie de produits (Femmes) | Chaussures), suivie d’une page de passage en caisse (passage en caisse | Merci) sur une seule page.

![Segment de séquence dans](assets/sequence-filter-within.png)

Les exemples de séquences suivants correspondent ou ne correspondent pas :

| Séquence | ![ApproveReject](/help/assets/icons/ApproveReject.svg) |
|--- | :---: |
| Page `Women \| Shoes` suivie de page `Checkout \| Thank You` | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| Page `Women \| Shoes` suivie de page `Women \| Tops` suivie de page `Checkout \| Thank You` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) |

## [!UICONTROL Inclure]

Vous pouvez spécifier les données à inclure dans votre segment séquentiel ou dans un conteneur séquentiel qui fait partie de votre segment séquentiel.

### [!UICONTROL &#x200B; Tout le monde &#x200B;] {#include_everyone}

Pour créer un segment séquentiel qui inclut tout le monde, sélectionnez l’option ![UserGroup](/help/assets/icons/UserGroup.svg) **[!UICONTROL Inclure tout le monde]**.

Le segment séquentiel identifie les données qui correspondent au modèle donné dans son ensemble.  Vous trouverez ci-dessous un exemple de segment de séquence de base recherchant les visiteurs qui ont visité une page de catégorie de produits (Femmes) | Chaussures), suivie d’une page de passage en caisse (passage en caisse | Merci). Le segment est défini sur ![UserGroup](/help/assets/icons/UserGroup.svg) **[!UICONTROL Inclure tout le monde]**.

![Les segments séquentiels incluent tout le monde](assets/sequence-include-everyone.png)

Les exemples de séquences suivants correspondent ou ne correspondent pas :

| | Séquence | ![ApproveReject](/help/assets/icons/ApproveReject.svg) |
|---:|--- | --- |
| 1 | `Women \| Shoes` ensuite `Checkout \| Thank You` la même visite | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| 2 | `Women \| Shoes` puis `Men \| Shoes` puis `Checkout \| Thank You` (à travers différentes visites) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| 3 | `Checkout \| Thank You` puis `Women \| Shoes` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) |

### [!UICONTROL Seulement avant la séquence] et [!UICONTROL Seulement après la séquence]

Les options ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **[!UICONTROL Only Before Sequence]** et ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **[!UICONTROL Only After Sequence]** segmentent les données en un sous-ensemble avant ou après la séquence spécifiée.

* ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **Only Before Sequence** : inclut toutes les données précédant une séquence et les premières données de la séquence elle-même. Si une séquence apparaît plusieurs fois dans le cadre des données, [!UICONTROL Uniquement avant la séquence] inclut le premier accès de la dernière occurrence de la séquence et tous les accès précédents.
* ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **Only After Sequence** : inclut tous les accès suivant une séquence et les dernières données de la séquence elle-même. Si une séquence apparaît plusieurs fois dans le cadre des données, [!UICONTROL Uniquement après la séquence] inclut le dernier accès de la première occurrence de la séquence et tous les accès suivants.

Prenons une définition spécifiant une séquence d’un composant avec des critères identifiés par B, suivie (Then) d’un composant avec des critères identifiés par D. Les trois options identifieraient les données comme suit :


| B Puis D | A | B | C | D | E | F |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| Inclure tout le monde | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| Seulement avant la séquence | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |  |  |  |  |
| Seulement après la séquence |  |  |  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |



| B Puis D (se produit plusieurs fois) | A | B | C | D | B | C | D | E |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Inclure tout le monde | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |
| Seulement avant la séquence | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |  |  |  |
| Seulement après la séquence |  |  |  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) |

#### Exemple

Vous avez défini trois versions d’un segment séquentiel pour les sections du site. Une avec l’option ![UserGroup](/help/assets/icons/UserGroup.svg) **[!UICONTROL Inclure tout le monde]**, une avec l’option ![SequenceBefore](/help/assets/icons/SequenceBefore.svg) **[!UICONTROL Only Before Sequence]** et une avec l’option ![SequenceAfter](/help/assets/icons/SequenceAfter.svg) **[!UICONTROL Only After Sequence]**. Vous avez nommé les trois segments en conséquence.

![Segment de séquence](assets/site-section-filters.png)

Lors de la création de rapports sur les sections de site à l’aide de ces trois segments, l’exemple de sortie dans un tableau à structure libre ressemble à ceci :

![Rapport sur les segments séquentiels](assets/sequential-filter-freeform-table.png)

## [!UICONTROL Exclure]

Les définitions de segment incluent toutes les données, sauf si vous excluez spécifiquement les données ![Utilisateur](/help/assets/icons/User.svg) [!UICONTROL Personne], ![Visite](/help/assets/icons/Visit.svg) [!UICONTROL Visite] ou ![PageWeb](/help/assets/icons/WebPage.svg) [!UICONTROL Hit] à l’aide de **[!UICONTROL Exclure]**.

[!UICONTROL Exclure] vous permet d’ignorer les données courantes et de créer des segments avec plus de focus. Exclure permet également de créer des segments excluant des groupes spécifiques de visiteurs. Par exemple, pour définir un segment qui spécifie les visiteurs qui ont passé des commandes, puis excluant ce groupe de visiteurs afin d’identifier *non-acheteurs*. Une bonne pratique consiste à créer des règles qui utilisent une définition large plutôt que d’essayer d’utiliser [!UICONTROL Exclure] pour cibler des visiteurs spécifiques qui correspondent à des valeurs d’inclusion spécifiques.

Voici quelques exemples de définitions d’exclusion :

* **Exclure des pages**. Utilisez une définition de segment pour exclure une page spécifique (telle que *Page d’accueil*) d’un rapport, créez une règle Accès dans laquelle la page est égale à `Home Page`, puis excluez la règle. Cette définition inclut automatiquement toutes les pages, à l’exception de la *Page d’accueil*.
* **Exclure des domaines référents**. Utilisez une définition qui inclut uniquement les domaines référents de Google.com et exclut tous les autres.
* **Identifier les non-acheteurs**. Identifier les commandes supérieures à zéro, puis exclure la [!UICONTROL Personne].

[!UICONTROL Exclure] peut être utilisé pour identifier une séquence dans laquelle les visiteurs ne font pas partie de visites spécifiques ou n’effectuent pas d’accès spécifiques. [!UICONTROL Exclure] peut également être inclus dans un [!UICONTROL Groupe logique] (voir ci-dessous).

Vous pouvez exclure les conteneurs, et non les composants.

### Exemples

Consultez ci-dessous des exemples d’utilisation de [!UICONTROL Exclure].

#### [!UICONTROL Exclure] dans

Identifiez les visiteurs et visiteuses qui ont consulté une page, qui n’ont pas consulté une autre page, puis qui ont consulté une autre page. Vous excluez le conteneur à l’aide de ![Paramètre](/help/assets/icons/Setting.svg) [!UICONTROL Exclure]. Une fine barre rouge sur la gauche identifie un conteneur exclu.

![Exclure la séquence](assets/sequence-exclude.png)


#### [!UICONTROL Exclure] au début

Identifier les visiteurs et visiteuses qui ont visité une page sans jamais accéder à une autre page. Par exemple, les personnes qui ont extrait un achat sans jamais avoir visité la page d’accueil.

![Début d’exclusion de la séquence](assets/sequence-exclude-start.png)


#### [!UICONTROL Exclure] à la fin

Identifiez les visiteurs et visiteuses qui ont visité une page mais n’ont jamais visité d’autres pages. Par exemple, les visiteurs et visiteuses qui ont visité votre page d’accueil, mais jamais aucune de vos pages de passage en caisse.

![Fin de l’exclusion de la séquence](assets/sequence-exclude-end.png)


## [!UICONTROL Groupe logique]

>[!NOTE]
>
>Un [!UICONTROL Groupe logique] ne peut être défini que dans un segment séquentiel, ce qui signifie que l’opérateur [!UICONTROL Then] est utilisé dans le conteneur.

Les conteneurs Groupe logique servent à regrouper des conditions dans un point de contrôle de segment séquentiel unique. Dans le cadre de la séquence, la logique définie dans le conteneur identifié comme Groupe logique est évaluée après tout point de contrôle séquentiel précédent et avant tout point de contrôle séquentiel suivant.

Les conditions du groupe logique lui-même peuvent être remplies dans n&#39;importe quel ordre. En revanche, les conteneurs non séquentiels (accès, visite, visiteur) n’ont pas besoin que leurs conditions soient remplies dans la séquence globale, ce qui produit des résultats inintuitifs possibles s’ils sont utilisés avec un opérateur **[!UICONTROL Then]**.

[!UICONTROL Groupe logique] a été conçu pour traiter *plusieurs conditions en tant que groupe, sans ordre* parmi les conditions regroupées. Autrement dit, l’ordre des conditions au sein d’un groupe logique n’est pas pertinent.

Voici quelques bonnes pratiques d’utilisation du groupe logique :

* Pour regrouper des points de contrôle séquentiels.
* Pour simplifier la construction de segments séquentiels.

### Exemples

Voici des exemples d’utilisation du conteneur Groupe logique .

#### N’importe quelle commande

Identifiez les visiteurs qui ont visité une page, puis consulté chaque page d’un autre ensemble de pages dans n’importe quel ordre. Par exemple, les visiteurs qui ont visité la page d’accueil de , puis ont visité chacune des pages Hommes, Femmes et Enfants , quel que soit l’ordre.

Vous pouvez créer ce segment sans [!UICONTROL &#x200B; Groupe logique &#x200B;], mais la construction sera complexe et laborieuse. Spécifiez chaque séquence de pages que le visiteur peut afficher. Pour plus de clarté, seul le premier conteneur est ouvert ![ChevronDown](/help/assets/icons/ChevronDown.svg) et les autres conteneurs sont fermés ![ChevronRight](/help/assets/icons/ChevronRight.svg). Vous pouvez dériver le contenu des autres conteneurs par les titres.

![Exemple n’utilisant pas de groupe logique](assets/logicgroup-example-notusing.png)

Vous pouvez utiliser [!UICONTROL Groupe logique] pour simplifier la création de ce segment, comme illustré ci-dessous. Veillez à sélectionner ![Groupe](/help/assets/icons/Group.svg) **[!UICONTROL Groupe logique]** pour le conteneur.

![Exemple n’utilisant pas de groupe logique](assets/logicgroup-example-using.png)

#### Première correspondance

Identifiez les visiteurs qui ont visité une page ou une autre page, puis qui ont visité une autre page. Par exemple, les visiteurs et visiteuses qui ont visité la page Femmes ou la page Hommes, puis qui ont visité le passage en caisse | Page de remerciement.

![Exemple d’utilisation de la première correspondance avec un groupe logique](assets/logicgroup-example-firstmatch.png)

#### [!UICONTROL Exclure] [!UICONTROL Et]

Identifier les visiteurs qui ont visité une page, puis qui n’ont pas visité explicitement un ensemble de pages, mais qui ont visité une autre page. Par exemple, les visiteurs qui ont visité la page d’accueil et qui n’ont pas visité la page Hommes ou Femmes, mais qui ont visité la page Enfants .

![Groupe logique à exclure et](assets/logicgroup-exclude-and.png)

#### [!UICONTROL Exclure] [!UICONTROL Ou]

Identifiez les visiteurs qui ont visité une page, puis qui n’ont visité explicitement aucune page d’un ensemble de pages, mais qui ont visité une autre page. Par exemple, les visiteurs qui ont visité la page d’accueil et qui n’ont pas visité la page Hommes et femmes, mais qui ont visité la page Enfants .

![Groupe logique à exclure et](assets/logicgroup-exclude-or.png)


<!--
An example of a complex sequential segment if you want to find the visitors that 

| visit One | visit Two | visit Three |
| --- | --- | --- |
| The visitor went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The visitor again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The visitor entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->


## Dernier exemple

Dernier exemple : vous souhaitez identifier les visiteurs qui ont appris quelque chose sur une page produit spécifique, sans qu’ils aient jamais été touchés par votre campagne Donnez le pouvoir pour bouger. Et lors de leur première visite dans votre boutique en ligne, ils ont consulté la page d&#39;accueil, mais n&#39;ont pas examiné plus loin les produits de fitness (équipement) de la catégorie Hommes. Cependant, lors de leur prochaine visite directement après cela, ils se sont rendus sur une page produit et ont passé une commande en ligne sans passer par la page d&#39;accueil au préalable.


![ Exemple de segment séquentiel complexe ](assets/sequential-complex.png)

>[!MORELIKETHIS]
>
> * [Maîtriser la logique séquentielle dans AA et CJA : introduction à THEN](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/mastering-sequential-logic-in-aa-amp-cja-introduction-to-then/ba-p/738131)
