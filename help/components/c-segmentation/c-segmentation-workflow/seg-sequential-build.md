---
description: Les segments séquentiels sont créés en utilisant l’opérateur ALORS au lieu de ET ou OU. ALORS implique l’apparition d’un critère de segment, suivi d’un autre. Par défaut, un segment séquentiel identifie toutes les données correspondantes, en affichant le filtre « Inclure tout le monde ». Les segments séquentiels peuvent être filtrés davantage pour obtenir un sous-ensemble d’accès correspondants en utilisant les options « Seulement avant la séquence » et « Seulement après la séquence ».
title: Création des segments séquentiels
topic: Segments
uuid: 7fb9f1c7-a738-416a-aaa2-d77e40fa7e61
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Création des segments séquentiels

Les segments séquentiels sont créés en utilisant l’opérateur ALORS au lieu de ET ou OU. ALORS implique l’apparition d’un critère de segment, suivi d’un autre. Par défaut, un segment séquentiel identifie toutes les données correspondantes, en affichant le filtre « Inclure tout le monde ». Les segments séquentiels peuvent être filtrés davantage pour obtenir un sous-ensemble d’accès correspondants en utilisant les options « Seulement avant la séquence » et « Seulement après la séquence ».

![](assets/before-after-sequence.png)

De plus, vous pouvez contraindre des segments séquentiels à une durée spécifique, une granularité donnée et un nombre d’accès entre des points de contrôle en utilisant les [opérateurs Après et Dans](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md).

## Inclure tout le monde {#section_75ADDD5D41F04800A09E592BB2940B35}

Lors de la création d’un segment pour lequel « Inclure tout le monde » est sélectionné, le segment identifie les chemins correspondant au modèle donné dans son ensemble. Voici un exemple de segment de séquence de base recherchant un accès (Page A) suivi d’un autre (Page B) lors d’une visite effectuée par le même visiteur. Le segment est défini sur Inclure tout le monde.

![](assets/sequence-filter.png)

| Si le résultat… | Séquence |
|--- |--- |
| Correspond à | A puis B<br>A puis B (lors d’une autre visite)<br>A puis D puis B |
| Ne correspond pas à | B puis A |

## Seulement avant la séquence et Seulement après la séquence  {#section_736E255C8CFF43C2A2CAAA6D312ED574}

Les options **[!UICONTROL Seulement avant la séquence]** et **[!UICONTROL Seulement après la séquence]** filtrent le segment en un sous-ensemble de données avant ou après la séquence spécifiée.

* **Seulement avant la séquence :** inclut tous les accès avant une séquence + le premier accès de la séquence elle-même (voir les exemples 1 et 3). Si une séquence apparaît plusieurs fois dans un chemin, « Seulement avant la séquence » inclut le premier accès de la dernière occurrence de la séquence et tous les accès précédents (voir l’exemple 2).
* **Seulement après la séquence :** inclut tous les accès après une séquence + le dernier accès de la séquence elle-même (voir les exemples 1 et 3). Si une séquence apparaît plusieurs fois dans un chemin, « Seulement après la séquence » inclut le dernier accès de la première occurrence de la séquence et tous les accès suivants (voir l’exemple 2).

Par exemple, considérons une séquence de B -> D. Les trois filtres identifieraient les accès comme suit :

**Exemple 1 : B puis D apparaissent une fois**

| Exemple | A | B | C | D | E | F |
|---|---|---|---|---|---|---|
| Inclure tout le monde | A | B | C | D | E | F |
| Seulement avant la séquence | A | B |  |  |  |  |
| Seulement après la séquence |  |  |  | D | E | F |

**Exemple 2 : B puis D apparaissent plusieurs fois**

| Exemple | A | B | C | D | B | C | D | E |
|---|---|---|---|---|---|---|---|---|
| Inclure tout le monde | A | B | C | D | B | C | D | E |
| Seulement avant la séquence | A | B | C | D | B |  |  |  |
| Seulement après la séquence |  |  |  | D | B | C | D | E |

Formulons également ce concept avec la dimension de Détail des accès.

**Exemple 3 : Détail des accès sur 3 puis sur 5**

![](assets/hit-depth.png)

## Contraintes de dimension {#section_EAFD755F8E674F32BCE9B642F7F909DB}

Dans une clause « dans » entre des instructions ALORS, vous pouvez ajouter par exemple « dans une instance de mot-clé de recherche », « dans une instance eVar 47 ». Le segment est ainsi limité à une instance d’une dimension.

Définir une clause « Dans la dimension » entre des règles permet à un segment de limiter les données aux séquences où cette clause est satisfaite. Voir l’exemple ci-dessous où la contrainte est définie sur « Dans 1 Page » :

![](assets/sequence-filter4.png)

| Si le résultat… | Séquence |
|--- |--- |
| Correspond à | A puis B |
| Ne correspond pas à | A puis C puis B (car B ne se trouvait pas à moins d’une page de A)<br>**Remarque ** : si la restriction de dimension est levée, « A puis B » et « A puis C puis B » correspondent tous les deux. |

## Séquence simple de pages vues

Identifiez les visiteurs qui ont consulté une page, puis consulté une autre page. Les données au niveau de l’accès filtrent cette séquence sans tenir compte des sessions précédentes ou intermédiaires, ni de l’intervalle ou du nombre de pages vues entre celles-ci.

**Exemple** : le visiteur a consulté la page A, puis la page B au cours de la même visite ou d’une autre.

**Cas d’utilisation**

Vous trouverez ci-dessous des exemples d’utilisation du segment :

1. Les visiteurs d’un site dédié au sport consultent la page d’entrée « football », puis la page d’entrée « basketball » en ordre séquentiel mais pas nécessairement lors de la même visite. Cela invite à créer une campagne visant à « pousser » le contenu de la page « basketball » vers les visiteurs de la page « football » au cours de la saison de football.
1. Un concessionnaire automobile identifie une relation entre ceux qui accèdent à la page de fidélité des clients, puis à la page vidéo à n’importe quel moment au cours de la visite ou d’une autre visite.

**Créer ce segment**

Vous imbriquez deux règles de pages dans un conteneur [!UICONTROL Visiteur] de niveau supérieur et séquencez les accès aux pages à l’aide de l’opérateur [!UICONTROL ALORS].

![](assets/segment_sequential_1.png)

## Séquence de visiteur entre plusieurs visites

Identifiez les visiteurs qui ont abandonné une campagne, mais sont revenus à la séquence de pages vues au cours d’une autre session.

**Exemple** : le visiteur a consulté la page A lors d’une session, puis la page B au cours d’une autre.

**Cas d’utilisation**

Vous trouverez ci-dessous des exemples d’utilisation de ce type de segment :

* Le visiteur d’un site de nouvelles consulte la page Sports, puis la consulte à nouveau lors d’une autre visite.
* Un détaillant en vêtements constate une relation entre les visiteurs qui accèdent à une page d’entrée lors d’une visite et qui se rendent directement à la page de passage en caisse lors d’une autre visite.

**Créer ce segment**

Cet exemple imbrique deux conteneurs **[!UICONTROL Visite]** dans le conteneur **[!UICONTROL Visiteur]** de niveau supérieur et séquence le segment à l’aide de l’opérateur [!UICONTROL ALORS].

![](assets/visitor_seq_across_visits.png)

## Séquence de niveau mixte

Identifiez les visiteurs qui consultent deux pages lors d’un nombre indéterminé de visites, puis consultent une troisième page lors d’une autre visite.

**Exemple** : les visiteurs visitent la page A, puis la page B lors d’une ou de plusieurs visites, puis la page C lors d’une autre visite.

**Cas d’utilisation**

Vous trouverez ci-dessous des exemples d’utilisation de ce type de segment :

* Les visiteurs consultent tout d’abord un site de nouvelles, puis la page des sports, lors de la même visite. Lors d’une autre visite, le visiteur consulte la page météo.
* Le détaillant définit les visiteurs qui consultent la page d’accueil, puis passe à la page Mon compte. Lors d’une autre visite, ils consultent la page Afficher le panier.

**Créer ce segment**

1. Déposez deux dimensions Page depuis les panneaux de gauche dans un conteneur [!UICONTROL Visiteur] de niveau supérieur.
1. Ajoutez l’opérateur ALORS entre les deux dimensions.
1. Cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Ajouter un conteneur]**, puis ajoutez un conteneur [!UICONTROL Visite] sous le niveau [!UICONTROL Visiteur] et séquencez à l’aide de l’opérateur [!UICONTROL ALORS].

![](assets/mixed_level_checkpoints.png)

## Agrégat de conteneurs

L’ajout de plusieurs conteneurs [!UICONTROL Accès] à l’intérieur d’un conteneur [!UICONTROL Visiteurs] vous permet d’utiliser les opérateurs appropriés entre des conteneurs de même type, ainsi que d’utiliser des règles et des dimensions, telles que Page et Nombre de visites, pour définir la page vue et fournir une dimension de séquence dans le conteneur [!UICONTROL Accès]. L’application de la logique au niveau Accès vous permet de limiter et de combiner des correspondances au même niveau d’accès dans le conteneur [!UICONTROL Visiteur] afin de créer plusieurs types de segments.

**Exemple** : les visiteurs ont consulté la page A après le premier accès dans la séquence de pages vues (page D dans l’exemple), puis ont consulté la page B ou C sans tenir compte du nombre de visites.

**Cas d’utilisation**

Vous trouverez ci-dessous des exemples d’utilisation de ce type de segment :

* Identifiez les visiteurs qui accèdent à la page d’entrée principale lors d’une visite, puis consultent la page des vêtements pour hommes lors d’une autre visite, puis la page d’entrée Femmes ou Enfants lors d’une autre visite.
* Un magasin en ligne capture les visiteurs qui accèdent à la page d’accueil lors d’une visite, à la page Sports lors d’une autre visite et la page Opinion lors d’une autre visite.

**Créer ce segment**

1. Sélectionnez le conteneur [!UICONTROL Visiteurs] en tant que conteneur de niveau supérieur.
1. Ajoutez deux autres conteneurs de niveau [!UICONTROL Accès] : une dimension avec une dimension numérique appropriée associée au même niveau [!UICONTROL Accès] par l’opérateur [!UICONTROL ET] ou [!UICONTROL OU].
1. Ajoutez un autre conteneur [!UICONTROL Accès] dans le conteneur [!UICONTROL Visites] et imbriquez deux conteneurs [!UICONTROL Accès] supplémentaires, associés par un opérateur [!UICONTROL OU] ou [!UICONTROL ET].

   Séquencez ces conteneurs [!UICONTROL Accès] imbriqués à l’aide de l’opérateur [!UICONTROL ALORS].

![](assets/aggregate_checkpoints2.png)

## « Imbrication » dans des segments séquentiels

En plaçant des points de contrôle aux niveaux [!UICONTROL Visite] et [!UICONTROL Accès], vous pouvez contraindre le segment à satisfaire certaines exigences au cours d’une visite spécifique, ainsi que lors d’un accès donné.

**Exemple** : le visiteur a consulté la page A, puis la page B au cours de la même visite. Au cours d’une nouvelle visite, le visiteur a accédé à la page C.

**Créer ce segment**

1. Sous un conteneur [!UICONTROL Visite] de niveau supérieur, faites glisser deux dimensions Page.
1. Sélectionnez plusieurs fois les deux règles, cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Ajouter un conteneur d’après la sélection]** et modifiez-le en un conteneur [!UICONTROL Visite].
1. Associez-les avec un opérateur [!UICONTROL ALORS].
1. Créez un conteneur Accès en tant que pair du conteneur [!UICONTROL Visite] et faites glisser dans une dimension Page.
1. Associez la séquence imbriquée dans le conteneur [!UICONTROL Visite] au conteneur [!UICONTROL Accès] en utilisant un autre opérateur [!UICONTROL ALORS].

![](assets/nesting_sequential_seg.png)

## Exclure les accès

Les règles de segmentation incluent toutes les données, à moins que vous n’excluiez spécifiquement les données [!UICONTROL Visiteur], [!UICONTROL Visite] ou [!UICONTROL Accès] à l’aide de la règle [!UICONTROL Exclure]. Cela vous permet d’ignorer les données courantes et de créer des segments plus focalisés. Cela vous permet également de créer des segments qui excluent les groupes trouvés afin d’identifier le jeu de données restant ; il peut s’agir, par exemple, de la création d’une règle qui inclut les visiteurs qui ont passé des commandes, puis les exclut afin d’identifier les simples visiteurs (en d’autres termes, les « non-acheteurs »). Cependant, dans la plupart des cas, il est préférable de créer des règles qui excluent des valeurs trop génériques, plutôt que d’essayer d’utiliser la règle d’exclusion ([!UICONTROL Exclure]) pour cibler des valeurs d’inclusion spécifiques.

Par exemple :

* **Exclure des pages**. Utilisez une règle de segmentation afin d’exclure une page spécifique  *`Home Page`*) d’un rapport. Créez une règle Accès dans laquelle la page est égale à « Page d’accueil », puis excluez-la. Cette règle inclut automatiquement toutes les valeurs, à l’exception de la page d’accueil.
* **Exclure des domaines référents**. Utilisez une règle qui inclut uniquement des domaines référents de Google.com et exclut tous les autres.
* **Identifier les non-acheteurs**. Identifiez les commandes dont la valeur est supérieure à zéro et excluez ensuite le [!UICONTROL Visiteur].

L’opérateur [!UICONTROL Exclure] peut être utilisé pour identifier une séquence dans laquelle des visites ou des accès spécifiques ne sont pas effectués par le visiteur. Les [!UICONTROL points de contrôle d’exclusion] peuvent également être inclus dans un conteneur  [Groupe logique](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md).

### Exclure entre les points de contrôle

Impose la logique de segmentation des visiteurs lorsqu’un point de contrôle ne s’est pas produit explicitement entre deux autres.

**Exemple** : les visiteurs qui ont visité la page A, puis la page C mais pas la page B.

**Cas d’utilisation**

Vous trouverez ci-dessous des exemples d’utilisation de ce type de segment :

* Visiteurs de la page Style de vie, puis de la section Théâtre sans passer par la page Arts.
* Un concessionnaire automobile constate une relation entre ceux qui visitent la page d’entrée principale, puis passent directement à la campagne « Sans intérêt » sans accéder à la page « Véhicule ».

**Créer ce segment**

Créez un segment comme vous le feriez pour un segment  segment séquentiel simple, de niveau mixte ou imbriqué, puis définissez l’opérateur [!UICONTROL EXCLURE] pour l’élément de conteneur. L’exemple ci-dessous illustre un segment agrégé dans lequel les trois conteneurs [!UICONTROL Accès] sont déplacés vers le canevas, l’opérateur [!UICONTROL ALORS] est affecté pour joindre la logique du conteneur, puis le conteneur de pages vues intermédiaire est exclu afin de n’inclure que les visiteurs qui sont passés de la page A à la page C dans la séquence.

![](assets/exclude_between_checkpoints.png)

### Exclure au début d’une séquence

Si le point de contrôle d’exclusion se situe au début d’un segment séquentiel, cette option s’assure qu’une page exclue n’a pas été vue avant le premier accès non exclu.

**Exemple** : le visiteur a visité la page A et non la page B.

**Cas d’utilisation**

Vous trouverez ci-dessous des exemples de cas d’utilisation de ce type de segment :

* Les visiteurs qui ont visité la page A et n’ont pas visité la page B.
* Un restaurant veut voir les utilisateurs incurables qui évitent la page d’entrée principale et vont directement à la page Commande à emporter.

**Créer ce segment**

Créez deux conteneurs d’accès distincts au sein d’un conteneur de visiteurs de niveau supérieur. Définissez l’opérateur [!UICONTROL EXCLURE] pour le premier conteneur.

![](assets/exclude_beginning_sequence.png)

### Exclure en fin de séquence

Si le point de contrôle d’exclusion se situe à la fin d’une séquence, cette option s’assure que le point de contrôle ne s’est pas produit entre le dernier point non exclu et la fin de la séquence du visiteur.

**Exemple** : les visiteurs ont consulté la page A, mais n’ont pas, par la suite, consulté la page B, que ce soit lors de la visite en cours ou de visites ultérieures.

**Cas d’utilisation**

Vous trouverez ci-dessous des exemples d’utilisation de ce type de segment :

* Les visiteurs qui ont visité la page A et n’ont pas visité la page B.
* Un restaurant veut voir les utilisateurs incurables qui évitent la page d’entrée principale et vont directement à la page Commande à emporter.

**Créer ce segment**

Créer une séquence simple en faisant glisser deux conteneurs [!UICONTROL Accès] vers la zone de travail et en les reliant à l’aide de l’opérateur [!UICONTROL ALORS]. Attribuez ensuite l’opérateur [!UICONTROL EXCLURE] au deuxième conteneur [!UICONTROL Accès] dans la séquence.

![](assets/exclude_end_sequence.png)

## Conteneurs Groupe logique

Les conteneurs Groupe logique sont nécessaires pour regrouper des conditions dans un point de contrôle de segment séquentiel unique. Le conteneur Groupe logique spécial n’est disponible que dans la segmentation séquentielle, afin de garantir que ses conditions sont remplies après tout point de contrôle séquentiel précédent et avant tout point de contrôle séquentiel suivant. Les conditions dans le point de contrôle du groupe logique lui-même peuvent être remplies dans n’importe quel ordre. En revanche, les conteneurs non séquentiels (accès, visite, visiteur) ne nécessitent pas que leurs conditions soient remplies dans la séquence globale, ce qui produit des résultats non intuitifs s’ils sont utilisés avec un opérateur ALORS.
Le conteneur [!UICONTROL Groupe logique] a été conçu pour traiter *plusieurs points de contrôle comme un groupe*, *sans aucun ordre* parmi les points de contrôle regroupés. En d’autres termes, nous ne nous soucions pas de l’ordre des points de contrôle dans ce groupe. Par exemple, vous ne pouvez pas imbriquer un conteneur [!UICONTROL Visiteur] dans un conteneur du même type. En revanche, vous pouvez imbriquer un conteneur [!UICONTROL Groupe logique] dans un conteneur [!UICONTROL Visiteur] avec des points de contrôle de niveaux [!UICONTROL Visite] et [!UICONTROL Accès] spécifiques.

> [!NOTE] Un [!UICONTROL groupe logique] ne peut être défini que dans un segment séquentiel, ce qui signifie que l’opérateur [!UICONTROL ALORS] est utilisé dans l’expression.

| Hiérarchie des conteneurs | Illustration | Définition |
|---|---|---|
| Hiérarchie des conteneurs standard | ![](assets/nesting_container.png) | Les conteneurs [!UICONTROL Visite] et [!UICONTROL Accès] sont imbriqués de manière séquentielle dans le conteneur [!UICONTROL Visiteur] afin d’extraire les segments en fonction des accès, du nombre de visites et du visiteur. |
| Hiérarchie de conteneurs logiques | ![](assets/logic_group_hierarchy.png) | La hiérarchie de conteneurs standard est également requise en dehors du conteneur [!UICONTROL Groupe logique]. Cependant, à l’intérieur du conteneur [!UICONTROL Groupe logique], les points de contrôle ne doivent pas respecter un ordre ou une hiérarchie spécifique ; ils doivent simplement être atteints par le visiteur dans n’importe quel ordre. |

Les groupes logiques peuvent sembler décourageants. Voici quelques bonnes pratiques pour les utiliser :

**Groupe logique ou conteneur Accès/Visite ?**
Si vous souhaitez regrouper des points de contrôle séquentiels, alors votre « conteneur » est Groupe logique. Toutefois, si ces points de contrôle séquentiels doivent se produire dans le cadre d’un accès ou d’une visite unique, des conteneurs « d’accès » ou « de visites » sont requis. (Bien sûr, un « accès » n’a aucun sens pour un groupe de points de contrôle séquentiels, lorsqu’un accès ne peut pas créditer plus d’un point de contrôle).

**Les groupes logiques simplifient-ils la création de segments séquentiels ?**
Oui, ils le peuvent. Supposons que vous essayiez de répondre à la question suivante : **Un visiteur a-t-il consulté la page B, la page C ou la page D après la page A ?**

Vous pouvez créer ce segment sans conteneur Groupe logique, mais cette opération est complexe et fastidieuse :
* `Visitor Container [Page A THEN Page B THEN Page C THEN Page D] or`
* `Visitor Container [Page A THEN Page B THEN Page D THEN Page C] or`
* `Visitor Container [Page A THEN Page C THEN Page B THEN Page D] or`
* `Visitor Container [Page A THEN Page C THEN Page D THEN Page B] or`
* `Visitor Container [Page A THEN Page D THEN Page B THEN Page C] or`
* `Visitor Container [Page A THEN Page D THEN Page C THEN Page B]`

Un conteneur Groupe logique simplifie considérablement la création de ce segment, comme illustré ici :

![](assets/logic-grp-example.png)


### Créer un segment Groupe logique {#section_A5DDC96E72194668AA91BBD89E575D2E}

Comme les autres conteneurs, les conteneurs [!UICONTROL Groupe logique] peuvent être créés de plusieurs manières dans le [!UICONTROL Créateur de segments]. Voici la méthode recommandée pour imbriquer des conteneurs [!UICONTROL Groupe logique] :

1. Faites glisser les dimensions, les événements ou les segments depuis les panneaux de gauche.
1. Définissez le conteneur supérieur sur un conteneur [!UICONTROL Visiteur].
1. Indiquez l’opérateur [!UICONTROL ALORS] à la place de l’opérateur [!UICONTROL ET] ou OU inséré par défaut.
1. Sélectionnez les conteneurs [!UICONTROL Accès] (la Dimension, l’Événement ou l’Élément) et cliquez sur **[!UICONTROL Options]** > **[!UICONTROL Ajouter un conteneur d’après la sélection]**.
1. Cliquez sur l’icône du conteneur et sélectionnez **[!UICONTROL Groupe logique]**.  ![](assets/logic_group_checkpoints.png)
1. Vous pouvez à présent définir le conteneur [!UICONTROL Accès] dans [!UICONTROL Groupe logique] sans tenir compte de la hiérarchie.

### Points de contrôle du groupe logique dans n’importe quel ordre

L’utilisation du [!UICONTROL Groupe logique] vous permet de respecter, au sein de ce groupe, des conditions qui résident en dehors de la séquence. Cela vous permet de créer des segments dans lesquels on trouve un conteneur [!UICONTROL Visite] ou [!UICONTROL Accès], quelle que soit la hiérarchie normale.

**Exemple** : visiteurs ayant consulté la page A, puis les pages B et C, dans n’importe quel ordre.

**Créer ce segment**

Les pages B et C sont imbriquées dans un conteneur [!UICONTROL Groupe logique] dans un conteneur [!UICONTROL Visiteur] extérieur. Le conteneur [!UICONTROL Page vue] pour A est ensuite suivi du conteneur [!UICONTROL Groupe logique], les pages B et C étant identifiées à l’aide de l’opérateur [!UICONTROL ET]. Étant donné que la séquence se trouve dans le conteneur [!UICONTROL Groupe logique], elle n’est pas définie. Aussi, l’accès à la page B ou C dans n’importe quel ordre définit l’argument sur « vrai ».

![](assets/logic_group_any_order2.png)

**Autre exemple** : visiteurs qui ont consulté la page B ou C, puis la page A :

![](assets/logic_group_any_order3.png)

Le segment doit correspondre au moins à l’un des points de contrôle du groupe logique (B ou C). En outre, les conditions du groupe logique peuvent être remplies dans le même accès ou sur plusieurs accès.

### Première correspondance dans le groupe logique

L’utilisation du [!UICONTROL Groupe logique] vous permet de respecter, au sein de ce groupe, des conditions qui résident en dehors de la séquence. Dans ce segment de première correspondance non ordonné, les règles du [!UICONTROL Groupe logique] sont d’abord identifiées comme étant une page vue de la page B ou C, puis comme la vue requise de la page A.

**Exemple** : visiteurs qui ont consulté la page B ou C, puis la page A.

**Créer ce segment**

Les dimensions des pages B et C sont regroupées dans un conteneur [!UICONTROL Groupe logique], l’opérateur [!UICONTROL OU] étant sélectionné, puis dans le conteneur [!UICONTROL Accès] identifiant une page vue de page A comme valeur.

![](assets/logic_group_1st_match.png)

### Opérateur ET d’exclusion du groupe logique

Créez des segments à l’aide du [!UICONTROL Groupe logique], dans lesquels plusieurs pages vues sont agrégées afin de définir les pages auxquelles l’accès était nécessaire, alors que d’autres pages ont été spécifiquement ignorées. ****

**Exemple** : le visiteur a consulté la page A, puis n’a pas explicitement consulté la page B ou C, mais a accédé à la page D.

**Créer ce segment**

Créez ce segment en faisant glisser des dimensions, des événements et des segments pré-créés à partir des volets de gauche. Reportez-vous à la section [Création d’un segment Groupe logique](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md).

Après avoir imbriqué les valeurs dans le [!UICONTROL Groupe logique], cliquez sur le bouton **[!UICONTROL Exclure]** dans le conteneur [!UICONTROL Groupe logique].

![](assets/logic_exclude_and.png)

### Opérateur OU d’exclusion du groupe logique

Créez des segments à l’aide du [!UICONTROL Groupe logique], dans lesquels plusieurs pages vues sont agrégées afin de définir les pages auxquelles l’accès était nécessaire, alors que d’autres pages ont été spécifiquement ignorées.

**Exemple** : visiteurs ayant consulté la page A mais sans avoir, au préalable, consulté la page B ou C.

**Créer ce segment**

Les pages B et C initiales sont identifiées dans un conteneur [!UICONTROL Groupe logique] qui est exclu, puis suivies d’un accès à la page A réalisé par le visiteur.

Créez ce segment en faisant glisser des dimensions, des événements et des segments pré-créés à partir des volets de gauche.

Après avoir imbriqué les valeurs dans le [!UICONTROL Groupe logique], cliquez sur le bouton **[!UICONTROL Exclure]** dans le conteneur [!UICONTROL Groupe logique].

![](assets/logic_exclude_or.png)

## Création de segments Durée-Dans et Durée-Après

Utilisez les opérateurs [!UICONTROL Dans] et [!UICONTROL Après] intégrés dans l’en-tête de chaque conteneur pour définir la durée, des événements et un nombre.

![](assets/then_within_operators.png)

Vous pouvez limiter la correspondance à une durée spécifique en utilisant les conteneurs [!UICONTROL Dans] et [!UICONTROL Après], et en indiquant une granularité et un nombre. L’opérateur [!UICONTROL Dans] est utilisé pour spécifier une limite de temps maximale entre deux points de contrôle. L’opérateur [!UICONTROL Après] est, pour sa part, utilisé pour spécifier une limite de temps minimale entre deux points de contrôle.

### Opérateurs Après et Dans  {#section_CCAF5E44719447CFA7DF8DA4192DA6F8}

La durée est spécifiée par une seule lettre majuscule représentant la granularité, suivie d’un nombre indiquant le nombre de répétitions de la granularité.

**[!UICONTROL Dans]** inclut le point de terminaison (inférieur à ou égal à).

**[!UICONTROL Après]** n’inclut pas le point de terminaison (supérieur à).

| Opérateurs | Description |
|--- |--- |
| APRES | L’opérateur Après est utilisé pour spécifier une limite de temps minimale entre deux points de contrôle. Lorsque vous définissez des valeurs Après, la durée commence au moment où le segment est appliqué. Par exemple, si l’opérateur Après est défini sur un conteneur afin d’identifier des visiteurs qui consultent la page A, mais ne visualisent pas la page B avant au moins un jour, ce jour commence au moment où le visiteur quitte la page A. Pour que le visiteur soit inclus dans le segment, au moins 1 440 minutes (soit un jour) doivent s’écouler entre le moment où le visiteur quitte la page A et celui où il consulte la page B. |
| DANS | L’opérateur Dans est utilisé pour spécifier une limite de temps maximale entre deux points de contrôle. Par exemple, si l’opérateur Dans est défini sur un conteneur afin d’identifier les visiteurs qui consultent la page A, puis reviennent sur le site dans les 24 heures, cette période commence au moment où le visiteur quitte la page A. Pour que le visiteur soit inclus dans le segment, il dispose au maximum de 24 heures pour ouvrir la page B. Pour que le visiteur soit inclus dans le segment, la consultation de la page B doit avoir lieu, au maximum, 1 440 minutes (soit un jour) après avoir quitté la page A. |
| APRÈS/DANS | Lorsque vous utilisez les opérateurs Après et Dans, il importe de comprendre que tous les deux commencent et se terminent en parallèle, et non de manière séquentielle.   Par exemple, si vous créez un segment en définissant le conteneur sur: <br>`After = 1 Week(s) and Within = 2 Week(s)`<br>, les conditions d’identification des visiteurs dans le segment sont réunies uniquement entre 1 et 2 semaines. Les deux conditions sont appliquées à compter du premier accès à la page. |

### Utilisation de l’opérateur Après

* « Temps après » vous permet d’effectuer un suivi par année, mois, jour, heure et minute pour établir des correspondances avec des visites.
* Cet opérateur ne peut être appliqué qu’à un conteneur [!UICONTROL Accès], car il s’agit du seul niveau pour lequel une granularité aussi fine est définie.

**Exemple** : visiteurs qui ont consulté la page A, puis seulement la page B après 2 semaines.****

![](assets/time_between_after_operator.png)

**Créer le segment** : la création de ce segment s’effectue en ajoutant un conteneur [!UICONTROL Visiteur] avec deux conteneurs [!UICONTROL Accès]. Vous pouvez ensuite définir l’opérateur [!UICONTROL ALORS], puis ouvrir la liste déroulante de l’opérateur [!UICONTROL APRÈS] et définir le nombre de semaines.

![](assets/after_operator.png)

**Correspond à**

Lorsque « Après 2 semaines » est spécifié, si un accès à la page A a lieu le 1er juin 2019 à 00:01, un accès à la page B suivant sera considéré comme une correspondance s’il se produit avant le 15 juin 2019 à 00:01 (14 jours plus tard).

| Accès A | Accès B | Correspondance |
|--- |--- |--- |
| Accès **A** : 1er juin 2019 00:01 | Accès **B** : 15 juin 2019 00:01 | **Correspond à** : cette contrainte temporelle est considérée comme une correspondance, car elle intervient après le 1er juin 2019 (deux semaines). |
| Accès **A** : 1er juin 2019 00:01 | Accès **B** : 8 juin 2019 00:01 Accès B : 15 juin 2019 00:01 | **Ne correspond pas à** : le premier accès à la page B n’est pas considéré comme une correspondance, car il entre en conflit avec la contrainte. |

### Utilisation de l’opérateur Dans

* [!UICONTROL Dans] vous permet d’effectuer un suivi par année, mois, jour, heure et minute pour établir des correspondances avec des visites.
* [!UICONTROL Dans] ne peut être appliqué qu’à un conteneur [!UICONTROL Accès], car il s’agit du seul niveau pour lequel une granularité aussi fine est définie.

>[!IMPORTANT]
>
>Dans une clause « dans » entre des instructions ALORS, vous pouvez ajouter par exemple « dans une instance de mot-clé de recherche », « dans une instance eVar 47 ». Le segment est ainsi limité à une instance d’une dimension.

**Exemple** : visiteurs ayant consulté la page A, puis la page B dans les cinq minutes.

![](assets/time_between_within_operator.png)

**Créer le segment** : la création de ce segment s’effectue en ajoutant un conteneur [!UICONTROL Visiteur], puis en faisant glisser deux conteneurs [!UICONTROL Accès]. Vous pouvez alors définir l’opérateur [!UICONTROL ALORS] et ouvrir le menu déroulant de l’opérateur [!UICONTROL APRÈS] et définir l’intervalle : Accès, Page(s) vue(s), Visite(s), Minute(s), Heure(s), Jour(s), Semaine(s), Mois, Trimestre(s) ou Année(s).

![](assets/within_operator.png)

**Correspond à**

Les correspondances doivent se produire dans la limite temporelle définie. Dans le cas de l’expression , si un visiteur accède à la page A à 00:01, un accès ultérieur à la page B sera considéré comme une correspondance pour autant qu’il se produise au plus tard à 00:06 (soit cinq minutes plus tard). Les accès effectués dans la même minute sont également considérés comme des correspondances.

### Opérateurs Dans et Après

Utilisez les opérateurs [!UICONTROL Dans] et [!UICONTROL Après] pour fournir un point de terminaison maximum et minimum aux deux extrémités d’un segment.

**Exemple** : visiteurs qui ont consulté la page A, puis ont accédé à la page B dans un délai de deux semaines à un mois.

![](assets/time_between_using_both_operators.png)

**Créer le segment** : créez le segment en séquençant deux conteneurs [!UICONTROL Accès] dans un conteneur [!UICONTROL Visiteur]. Définissez ensuite les opérateurs [!UICONTROL Après] et [!UICONTROL Dans].

![](assets/within_after_together.png)

**Correspond à**

Sont inclus dans ce segment tous les visiteurs qui accèdent à la page A le 1er juin 2019 et qui reviennent sur cette page après le 15 juin 2019 à 00:01, mais *avant* le 1er juillet 2019. Comparaison avec [Intervalle entre les exclusions](/help/components/c-segmentation/c-segmentation-workflow/seg-sequential-build.md).

Les opérateurs [!UICONTROL Après] et [!UICONTROL Dans] peuvent être utilisés conjointement pour définir un segment séquentiel.

![](assets/time_between_within_after.png)

Cet exemple illustre une deuxième visite effectuée sur la page B entre deux semaines et un mois.
