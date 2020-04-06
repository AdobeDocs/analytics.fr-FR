---
description: Méthodes pour optimiser le Créateur de rapports et liste des messages d’erreur qui peuvent parfois s’afficher.
title: Résolution des problèmes et bonnes pratiques pour le Report Builder
topic: Report builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Résolution des problèmes et bonnes pratiques pour le Report Builder

Méthodes pour optimiser le Créateur de rapports et liste des messages d’erreur qui peuvent parfois s’afficher.

## Utilisateurs du Report Builder 5.0 et ouverture de classeurs 5.1 {#section_C29898775999453FABB5FB0E098415C8}

Adobe a remplacé le séparateur entre les dimensions et les classifications représenté par un trait de soulignement (_) par ||. Ce changement a des répercussions de compatibilité pour un utilisateur du Report Builder 5.0 qui ouvre un classeur de la version 5.1 avec des demandes de classification. Chaque fois qu’un classeur d’une version antérieure à la version 5.1 est ouvert, toutes ses requêtes de classification sérialisées sont converties dans ce format.

Ceci introduit un problème de compatibilité : Une fois converti en version 5.1, si un classeur est partagé avec un utilisateur dans la version 5.0 du créateur de rapports, cet utilisateur ne pourra plus reconnaître la demande de classification (en effet, il recherche &quot;_&quot; mais &quot;||&quot; en série dans la version 5.1).

L’effet secondaire suivant se produit lors de l’ouverture d’un classeur ARB 5.1 avec la demande de classification :

* Lors de l’ouverture du classeur, l’avertissement suivant s’affiche : « Ce classeur a été enregistré pour la dernière fois avec le Report Builder version 5.1. Cette version comprend des fonctions incompatibles avec la version du Report Builder installée sur cet ordinateur. Nous vous recommandons de mettre à niveau votre version du Report Builder avant de mettre à jour ce classeur. »
* Si vous cliquez avec le bouton droit de la souris sur une demande ARB avec classification, les menus contextuels du Report Builder (Modifier les requêtes, Ajouter une requête dépendante, etc.) ne seront pas visibles.
* Si vous actualisez tout, en cliquant sur le troisième bouton ou en actualisant un ensemble de requêtes issues du formulaire du Gestionnaire de requêtes, la demande de classification s’exécutera sans erreur. Toutefois, les valeurs de classification ne seront pas écrites.
* Vous pouvez toujours modifier la requête en ouvrant le Gestionnaire de requêtes, puis en passant d’une ligne à l’autre, jusqu’à ce qu’elle atteigne la requête appropriée.
* Si vous modifiez la requête sans changer aucun des paramètres, puis cliquez sur Terminer, la réponse sera correctement inscrite. En fait, la modification de la requête résout le problème puisque les paramètres de mise en page des réponses sont resérialisés. Il y a donc une solution, bien que cela prenne du temps.

## Problèmes d’authentification dans le Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Le Report Builder requiert une authentification pour créer des requêtes de données à partir de vos suites de rapports. Selon les paramètres d’[!DNL Analytics] ou le réseau, des problèmes de connexion au Créateur de rapports peuvent parfois se produire.

**Informations de connexion de la société incorrectes**

Cette erreur se produit généralement lorsque les informations de connexion de la société ne sont pas saisies correctement ou en cas de problèmes réseau. Procédez comme suit :

* Vérifiez l’orthographe du de connexion pour vous assurer qu’il n’y a pas de faute de frappe ou d’espace incorrect.
* Connectez-vous à Analytics à l’aide des mêmes informations de connexion pour vous assurer qu’elles sont correctes. Si vous ne parvenez pas à vous connecter à l’aide de ces informations d’identification, contactez un administrateur de votre société pour obtenir les informations de connexion correctes de la société.

**Pare-feu**

Le Report Builder utilise les ports 80 et 443. Vérifiez que ces ports sont autorisés à travers le pare-feu de votre société. Voir aussi Adresses IP internes d’Adobe pour connaître les autres exclusions de pare-feu.

## Recommandations pour optimiser les requêtes {#section_33EF919255BF46CD97105D8ACB43573F}

Les facteurs suivants peuvent rendre les requêtes plus complexes, ce qui peut ralentir le processus de traitement :

**Facteurs pouvant ralentir les remises**

* Trop de signets, de tableaux de bord et de classeurs du Report Builder ont été planifiés en l’espace de quelques heures.
* Trop de classeurs du Report Builder ont été planifiés à environ la même heure. Lorsque cela se produit, la file d’attente de l’API de rapports comporte des travaux en souffrance.

**Facteurs pouvant ralentir l’exécution des classeurs**

* Augmentation significative des classifications.
* Augmentation de la plage de dates de la demande au fil du temps.

   **Exemple** : imaginons que vous créez une requête de tendance à l’aide du paramètre Année en cours, ventilée par Jour. À la fin de l’année, la requête renverra davantage de périodes que celle créée au début de l’année.

   `(January 1 - January 30 versus January 1 - December 31.)`

**Causes des échecs de remise de classeurs**

Formules Excel complexes dans un classeur, notamment celles qui impliquent des dates et heures.

**Cellules renvoyant des zéros (aucune valeur)**

Si le nom de la feuille Excel comporte une apostrophe ou un guillemet simple, le Créateur de rapports ne renvoie aucune valeur. (Il s’agit d’une limitation Microsoft Excel.)

**Performances des requêtes**

La vitesse de traitement peut être affectée par les paramètres suivants :

| Paramètre | Performances plus rapides | Performances plus lentes |
|--- |--- |--- |
| Ventilations et ordre de ventilation | Peu | Beaucoup |
|  | Exemple : si vous ventilez A par Z, le nombre d’éléments d’A doit être toujours inférieur à celui de Z. Dans le cas contraire, la durée de la requête peut augmenter de façon significative. |
| Date range (Plage de dates) | Petite plage | Large éventail |
| Filtres | Filtrage spécifique | Filtrage le plus populaire |
| Granularité | Agrégé | Horaire<ul><li>Quotidien</li><li>Hebdomadaire</li><li>Mensuel</li><li>Trimestriel</li><li>Annuel</li></ul> |
| Nombre d’entrées | Petit jeu de données | Jeu de données volumineux |


**Heures de planification**

Échelonnez les planifications sur une période de 24 heures (voir le tableau ci-après). Les signets, les tableaux de bord et les classeurs du Report Builder planifiés de façon rapprochée peuvent entraîner des retards.

Planifiez des requêtes plus volumineuses et plus complexes tôt le matin pour permettre des extractions manuelles et des actualisations pendant la journée de travail.

| Heure de planification | 1 heure du matin - 2 heures du matin | 2 heures du matin - 7 heures | 7 heures - 18 heures | 18 heures - Minuit |
|--- |--- |--- |--- |--- |
| Utilisation du Report Builder | Calme | Très occupé | Utilisation côté client.<br>Nombre plus élevé d’utilisateurs effectuant une actualisation locale et demandant un envoi immédiat.<br>De plus, vérifiez si la file d’attente de l’API est effacée lorsque les classeurs planifiés expirent. | Pas occupé |

**Délais d’expiration**

Les rapports planifiés expirent au bout de quatre heures. Le système tente d’effectuer la planification trois autres fois, ce qui peut entraîner un échec. (En règle générale, plus le jeu de données est volumineux, plus l’exécution prend du temps.) Ces informations sont affichées dans les rapports [!DNL Analytics] et le Report Builder :

* [!DNL Analytics]: **[!UICONTROL Favorites]** > **[!UICONTROL Scheduled Reports]**

* Report Builder: Click **[!UICONTROL Management]** in the [!UICONTROL Add-ins] tab in Excel.

## Description des messages d’erreur {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

Liste des messages d’erreur qui peuvent s’afficher lors de l’utilisation du Report Builder.

>[!NOTE] Cette liste n’est pas exhaustive. Pour plus d’informations sur la résolution des erreurs, contactez votre administrateur.

**Cette fonctionnalité peut uniquement être appliquée à un classeur ouvert.**

Si aucun classeur (de feuilles de calcul) n’est ouvert dans Excel et que vous cliquez sur l’une des icônes de la barre d’outils du créateur de rapports, ce message s’affiche. En outre, la barre d’outils est désactivée jusqu’à ce que vous ouvriez une feuille de calcul. Vous pouvez toutefois cliquer sur l’icône d’aide en ligne pendant que la barre d’outils est toujours activée sans générer cette erreur.

**Vous devez d’abord quitter le fichier[!UICONTROL Request Wizard]avant d’activer le[!UICONTROL Request Manager].**

Bien que les [!UICONTROL Request Manager] et les [!UICONTROL Request Wizard] soient liés sur le plan fonctionnel, il n’est pas possible d’de travailler avec le [!UICONTROL Request Manager] avant d’exécuter ou d’annuler les actions entreprises dans le [!UICONTROL Request Wizard].

**Aucune requête n’est associée à cette plage.**

Ce message d’erreur se produit si vous cliquez sur le [!UICONTROL From Sheet] bouton dans le [!UICONTROL Request Manager] cas où une cellule de la feuille de calcul ne contient aucune requête.

Pour identifier les cellules de la feuille de calcul qui contiennent des requêtes, cliquez sur des requêtes individuelles répertoriées dans le tableau du [!UICONTROL Request Manager]. Si une requête est associée à des cellules, les cellules s’affichent en surbrillance lorsque la requête est sélectionnée dans le tableau.

**La plage sélectionnée n’est pas valide. Sélectionnez une autre plage.**

Si une cellule de la feuille de calcul est sélectionnée et qu’une requête y est déjà associée, cette erreur se produit. Supprimez la requête mappée aux cellules ou choisissez une autre plage de cellules à mapper.

Lorsque vous souhaitez supprimer des cellules, il est important de localiser les cellules contenant des requêtes et de supprimer la requête avant de supprimer les cellules (suppression des lignes ou des colonnes).

**Veuillez quitter la cellule Excel active avant d’utiliser cette fonctionnalité.**

Cette erreur s’affiche si vous êtes en *mode d’édition* dans une cellule Excel et que vous cliquez sur l’une des icônes du Report Builder. Le mode de modification d’une cellule Excel signifie que la cellule est sélectionnée et que le curseur s’affiche à l’intérieur de la cellule. Vous êtes également en mode d’édition dans une cellule Excel lorsque vous entrez directement dans la [!UICONTROL Formula] barre ou [!UICONTROL Name Box] dans la partie supérieure d’Excel.

**La plage sélectionnée chevauche une autre plage de la requête. Veuillez modifier votre sélection.**

Si vous avez déjà mappé un ensemble de cellules à la feuille de calcul, cette erreur s’affiche.

Pour déterminer quelles cellules sont mappées avant d’ajouter de nouvelles requêtes, fermez la [!UICONTROL Request Wizard] fenêtre et ouvrez la [!UICONTROL Request Manager]. Sélectionnez ensuite les éléments répertoriés dans le tableau récapitulatif de la requête un par un. Chaque fois que vous sélectionnez une requête dans le , les cellules correspondantes contenant les mappages de requêtes dans la feuille de calcul sont mises en surbrillance.

C’est l’une des raisons pour laquelle vous devez envisager de marquer les cellules avec une mise en surbrillance, des informations sur les lignes ou les colonnes ou un style de formatage avant de mapper plusieurs cellules sur plusieurs zones.
