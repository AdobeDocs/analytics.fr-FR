---
description: Méthodes pour optimiser le Créateur de rapports et liste des messages d’erreur qui peuvent parfois s’afficher.
title: Résolution des problèmes et bonnes pratiques pour Report Builder
topic: Report builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Résolution des problèmes et bonnes pratiques pour Report Builder

Méthodes pour optimiser le Créateur de rapports et liste des messages d’erreur qui peuvent parfois s’afficher.

## Report Builder 5.0 users and opening 5.1 workbooks {#section_C29898775999453FABB5FB0E098415C8}

Adobe a remplacé le séparateur entre les dimensions et les classifications représenté par un trait de soulignement (_) par ||. Ce changement a des répercussions de compatibilité pour un utilisateur du Créateur de rapports 5.0 qui ouvre un classeur de la version 5.1 avec des demandes de classification. Chaque fois qu’un classeur d’une version antérieure à la version 5.1 est ouvert, toutes ses demandes de classification sérialisées sont converties dans ce format.

Ceci crée toutefois un problème de compatibilité : une fois qu’un classeur converti au format 5.1 est partagé avec un utilisateur de la version 5.0, cet utilisateur ne peut plus reconnaître la demande de classification (« _ » est recherché à la place de « || » dans la version 5.1).

L’effet secondaire suivant se produit lors de l’ouverture d’un classeur ARB 5.1 avec la demande de classification :

* Lors de l’ouverture du classeur, vous recevez l’avertissement suivant : "Ce classeur a été enregistré pour la dernière fois à l’aide de la version 5.1 du créateur de rapports. Cette version a introduit certaines fonctionnalités incompatibles avec la version du créateur de rapports installée sur cet ordinateur. Il est vivement recommandé d’effectuer la mise à niveau vers la dernière version du créateur de rapports avant de mettre à jour ce classeur."
* Si vous cliquez avec le bouton droit de la souris sur une demande ARB avec classification, les menus contextuels du Créateur de rapports (Modifier les requêtes, Ajouter une requête dépendante, etc.) ne seront pas visibles.
* Si vous actualisez tout, en cliquant sur le troisième bouton ou en actualisant un ensemble de requêtes issues du formulaire du Gestionnaire de requêtes, la demande de classification s’exécutera sans erreur. Toutefois, les valeurs de classification ne seront pas inscrites.
* Vous pouvez modifier la requête en ouvrant le Gestionnaire de requêtes, puis passer d’une ligne à l’autre jusqu’à la requête recherchée.
* Si vous modifiez la requête sans changer aucun des paramètres, puis cliquez sur Terminer, la réponse sera correctement inscrite. En fait, la modification de la requête résout le problème puisque les paramètres de mise en page des réponses sont resérialisés. Il s’agit donc d’une solution, même si elle prend du temps.

## Authentication issues in Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Le Créateur de rapports requiert une authentification pour créer des requêtes de données à partir de vos suites de rapports. Selon les paramètres d’[!DNL Analytics] ou le réseau, des problèmes de connexion au Créateur de rapports peuvent parfois se produire.

**Informations de connexion de la société incorrectes**

Cette erreur se produit généralement lorsque les informations de connexion de la société ne sont pas saisies correctement ou en cas de problèmes réseau. Procédez comme suit :

* Vérifiez l’orthographe des informations de connexion de la société pour vous assurer qu’il n’y a pas de faute de frappe ou d’espace en trop.
* Connectez-vous à Analytics à l’aide des mêmes informations de connexion pour vous assurer qu’elles sont correctes. Si vous ne parvenez pas à vous connecter à l’aide de ces informations d’identification, contactez un administrateur de votre société pour obtenir les informations de connexion correctes de la société. 

**Pare-feu**

Le Créateur de rapports utilise les ports 80 et 443. Vérifiez que ces ports sont autorisés à travers le pare-feu de votre société. Pour obtenir des informations sur les autres exclusions de pare-feu, reportez-vous aux adresses IP internes d’Adobe.

## Recommendations for optimizing requests {#section_33EF919255BF46CD97105D8ACB43573F}

Les facteurs suivants peuvent rendre les requêtes plus complexes, ce qui peut ralentir le processus de traitement :

**Facteurs pouvant ralentir les remises**

* Trop de signets, de tableaux de bord et de classeurs du Créateur de rapports ont été planifiés en l’espace de quelques heures.
* Trop de classeurs du Créateur de rapports ont été planifiés à environ la même heure. Lorsque cela se produit, la file d’attente de l’API de rapports comporte des travaux en souffrance.

**Facteurs pouvant ralentir l’exécution des classeurs**

* Augmentation significative des classifications.
* Allongement de la période des requêtes au fil du temps

   **Exemple** : imaginons que vous créez une requête de tendance à l’aide du paramètre Année en cours, ventilée par Jour. À la fin de l’année, la requête renverra davantage de périodes que celle créée au début de l’année. 

   `(January 1 - January 30 versus January 1 - December 31.)`

**Causes des échecs de remise de classeurs**

Formules Excel complexes dans un classeur, notamment celles qui impliquent des dates et heures.

**Cellules renvoyant des zéros (aucune valeur)**

Si le nom de la feuille Excel comporte une apostrophe ou un guillemet simple, le Créateur de rapports ne renvoie aucune valeur. (Il s’agit d’une limitation de Microsoft Excel.)

**Performances des requêtes individuelles**

Les paramètres suivants peuvent avoir un impact sur la vitesse de traitement :

| Paramètre | Plus rapide | Plus lent |
|--- |--- |--- |
| Ventilations et ordre de ventilation | Peu | Beaucoup |
|  | Exemple : si vous ventilez A par Z, le nombre d’éléments d’A doit être toujours inférieur à celui de Z. Dans le cas contraire, la durée de la requête peut augmenter de façon significative. |
| Période | Courte période | Longue période |
| Filtrage | Filtrage spécifique | Filtrage de type « Le plus populaire » |
| Granularité | Agrégé | Toutes les heures<ul><li>Quotidien</li><li>Hebdomadaire</li><li>Mensuel</li><li>Trimestriel</li><li>Annuel</li></ul> |
| Nombre d’entrées | Petit jeu de données | Jeu de données volumineux |


**Heure de planification**

Échelonnez les planifications sur une période de 24 heures (voir le tableau ci-après). Les signets, les tableaux de bord et les classeurs du Créateur de rapports planifiés de façon rapprochée peuvent entraîner des retards.

Planifiez les requêtes volumineuses et plus complexes tôt le matin pour permettre les extractions et les actualisations manuelles pendant la journée de travail.

| Heures de planification | 01:00 - 02:00 | 02:00 - 07:00 | 07:00 - 18:00 | 18:00 - minuit |
|--- |--- |--- |--- |--- |
| Utilisation du Créateur de rapports | Peu occupé | Très occupé | Utilisation du côté client<br>Nombre plus élevé d’utilisateurs effectuant une actualisation locale et demandant un envoi immédiat.<br>De plus, vérifiez si la file d’attente de l’API est effacée lorsque les classeurs planifiés expirent.  | Pas occupé |

**Délais d’expiration**

Les rapports planifiés expirent au bout de quatre heures. Le système tente d’effectuer la planification trois autres fois, ce qui peut entraîner un échec. (En règle générale, plus le jeu de données est volumineux, plus l’exécution prend du temps.) Ces informations sont affichées dans les rapports [!DNL Analytics] et le Créateur de rapports :

* [!DNL Analytics]: **[!UICONTROL Favoris]** &gt; Rapports **[!UICONTROL planifiés]**

* Créateur de rapports : cliquez sur **[!UICONTROL Gestion]** sous l’onglet [!UICONTROL Compléments] dans Excel.

## Error message descriptions {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

Liste des messages d’erreur qui peuvent s’afficher lors de l’utilisation du Créateur de rapports.

> [!NOTE] Il ne s'agit que d'une sélection de messages d'erreur et non d'une liste exhaustive. Pour plus d’informations sur la résolution des erreurs, contactez votre administrateur.

**Cette fonctionnalité peut uniquement être appliquée à un classeur ouvert.**

Ce message s’affiche si aucun classeur (feuilles de calcul) n’est ouvert dans Excel et que vous cliquez sur l’une des icônes de la barre d’outils du Créateur de rapports. En outre, la barre d’outils devient inactive jusqu’à ce que vous ouvriez une feuille de calcul. Vous pouvez toutefois cliquer sur l’icône de l’aide en ligne lorsque la barre d’outils est encore active sans engendrer cette erreur.

**Vous devez quitter l’[!UICONTROL Assistant Requête]avant d’activer le[!UICONTROL Gestionnaire de requêtes].**

Le [!UICONTROL Gestionnaire de requêtes] et l’[!UICONTROL Assistant Requête] constituent une fonctionnalité liée. Il n’est toutefois pas possible de commencer à utiliser le [!UICONTROL Gestionnaire de requêtes] avant d’avoir terminé ou annulé les tâches entreprises dans l’[!UICONTROL Assistant Requête].

**Aucune requête n’est associée à cette plage.**

Ce message d’erreur s’affiche si vous cliquez sur le bouton [!UICONTROL De la feuille] du [!UICONTROL Gestionnaire de requêtes] alors qu’une cellule de la feuille de calcul ne contient aucune requête.

Afin d’identifier les cellules de la feuille de calcul qui contiennent des requêtes, cliquez sur les requêtes individuelles répertoriées dans le tableau du [!UICONTROL Gestionnaire de requêtes]. Si la requête sélectionnée dans le tableau est associée aux cellules, celles-ci sont surlignées.

**La plage sélectionnée n’est pas valide. Sélectionnez une autre plage.**

Cette erreur s’affiche si vous sélectionnez, dans une feuille de calcul, une cellule à laquelle est déjà associée une requête. Supprimez la requête associée aux cellules ou sélectionnez une autre plage de cellules à mettre en correspondance.

Si vous souhaitez supprimer les cellules, il est important de localiser celles qui contiennent des requêtes et de supprimer les requêtes avant de supprimer les cellules (suppression des lignes ou colonnes).

**Veuillez quitter la cellule Excel active avant d’utiliser cette fonctionnalité.**

Cette erreur s’affiche si vous êtes en *mode d’édition* dans une cellule Excel et que vous cliquez sur l’une des icônes du Créateur de rapports. Le mode d’édition dans une cellule Excel signifie que la cellule est sélectionnée et que le curseur s’affiche à l’intérieur de celle-ci. Vous êtes également en mode d’édition dans une cellule Excel lorsque vous entrez directement des données dans la barre [!UICONTROL Formule] ou dans la zone [!UICONTROL Nom] en haut de la fenêtre Excel.

**La plage sélectionnée chevauche une autre plage de la requête. Veuillez modifier votre sélection.**

Cette erreur s’affiche si vous avez déjà mappé un ensemble de cellules à la feuille de calcul.

Pour déterminer les cellules qui sont mappées avant d’ajouter de nouvelles requêtes, fermez l’[!UICONTROL Assistant Requête] et ouvrez le [!UICONTROL Gestionnaire de requêtes]. Sélectionnez ensuite un par un les éléments répertoriés dans le tableau récapitulatif des requêtes. Chaque fois que vous sélectionnez une requête de la liste, les cellules associées contenant les correspondances de requêtes dans la feuille de calcul sont surlignées.

C’est pourquoi il est conseillé de marquer les cellules avec un surlignage, des informations de ligne ou de colonne ou un style de mise en forme avant de mapper plusieurs cellules sur plusieurs zones.
