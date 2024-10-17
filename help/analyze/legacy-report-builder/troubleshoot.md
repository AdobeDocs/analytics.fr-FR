---
description: Découvrez comment optimiser la diffusion par Report Builder et une liste des messages d’erreur qui peuvent se produire.
title: Résolution des problèmes et bonnes pratiques pour le Report Builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
feature: Report Builder
role: User, Admin
exl-id: 41a640ce-2316-439b-b3ba-f0bace9af268
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 84%

---

# Résolution des problèmes et bonnes pratiques pour le Report Builder

{{legacy-arb}}

Cet article décrit le dépannage et les bonnes pratiques que vous pouvez utiliser pour optimiser le Report Builder. Elle comprend également une liste des messages d’erreur qui peuvent s’afficher.

## Utilisateurs du Report Builder 5.0 et ouverture de classeurs 5.1 {#section_C29898775999453FABB5FB0E098415C8}

Adobe a remplacé le séparateur entre les dimensions et les classifications représenté par un trait de soulignement (_) par ||. Ce changement a des répercussions de compatibilité pour un utilisateur du Report Builder 5.0 qui ouvre un classeur de la version 5.1 avec des demandes de classification. Chaque fois qu’un classeur d’une version antérieure à la version 5.1 est ouvert, toutes ses demandes de classification sérialisées sont converties dans ce format.

Ceci crée toutefois un problème de compatibilité : une fois qu’un classeur converti au format 5.1 est partagé avec un utilisateur de la version 5.0, cet utilisateur ne peut plus reconnaître la demande de classification (« _ » est recherché à la place de « || » dans la version 5.1).

L’effet secondaire suivant se produit lors de l’ouverture d’un classeur ARB 5.1 avec la demande de classification :

* Lors de l’ouverture du classeur, l’avertissement suivant s’affiche : « Ce classeur a été enregistré pour la dernière fois avec le Report Builder version 5.1. Cette version comprend des fonctions incompatibles avec la version du Report Builder installée sur cet ordinateur. Nous vous recommandons de mettre à niveau votre version du Report Builder avant de mettre à jour ce classeur. »
* Si vous cliquez avec le bouton droit de la souris sur une demande ARB avec classification, les menus contextuels du Report Builder (Modifier les requêtes, Ajouter une requête dépendante, etc.) ne seront pas visibles.
* Si vous actualisez tout, en cliquant sur le troisième bouton ou en actualisant un ensemble de requêtes issues du formulaire du Gestionnaire de requêtes, la demande de classification s’exécutera sans erreur. Toutefois, les valeurs de classification ne seront pas inscrites.
* Vous pouvez modifier la requête en ouvrant le Gestionnaire de requêtes, puis passer d’une ligne à l’autre jusqu’à la requête recherchée.
* Si vous modifiez la requête sans changer aucun des paramètres, puis cliquez sur Terminer, la réponse sera correctement inscrite. En fait, la modification de la requête résout le problème puisque les paramètres de mise en page des réponses sont resérialisés. Il s’agit donc d’une solution, même si elle prend du temps.

## Problèmes d’authentification dans le Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Le Report Builder requiert une authentification pour créer des requêtes de données à partir de vos suites de rapports. Il arrive que des problèmes de connexion à Report Builder se produisent selon vos paramètres dans [!DNL Analytics] ou votre réseau.

* **Invalid Login Company** : cette erreur survient le plus souvent lorsque la connexion de la société est incorrectement entrée ou en cas de problèmes d’activité réseau. Procédez comme suit :
   * Vérifiez l’orthographe des informations de connexion de la société pour vous assurer qu’il n’y a pas de faute de frappe ou d’espace en trop.
   * Connectez-vous à Analytics à l’aide des mêmes informations de connexion pour vous assurer qu’elles sont correctes. Si vous ne parvenez pas à vous connecter à l’aide de ces informations d’identification, contactez un administrateur de votre société pour obtenir les informations de connexion correctes de la société.
* **Firewall** : le Report Builder utilise les ports 80 et 443. Vérifiez que ces ports sont autorisés à travers le pare-feu de votre société. Pour obtenir des informations sur les autres exclusions de pare-feu, reportez-vous aux adresses IP internes d’Adobe.

## Recommandations pour optimiser les requêtes {#section_33EF919255BF46CD97105D8ACB43573F}

Les facteurs suivants peuvent rendre les requêtes plus complexes, ce qui peut ralentir le processus de traitement.

* **Facteurs pouvant ralentir les diffusions** : un trop grand nombre de signets, de tableaux de bord et de classeurs Report Builder planifiés en quelques heures. Prenez également en compte le fait que trop de classeurs Report Builder ont été planifiés à peu près à la même heure. Lorsque cela se produit, la file d’attente de l’API de rapports comporte des travaux en souffrance.
* **Facteurs pouvant ralentir l’exécution des classeurs** : augmentation significative des classifications ou augmentation de la période de demande au fil du temps.
* **Causes des échecs de remise de classeurs** : des formules Excel complexes dans un classeur, en particulier celles qui impliquent la date et l’heure.
* **Cellules renvoyant des zéros (aucune valeur)** : une apostrophe ou un guillemet simple dans le nom de la feuille Excel ne renverra aucune valeur. (Il s’agit d’une limitation de Microsoft Excel.)
* **Performances des requêtes individuelles** : la vitesse de traitement peut être affectée par les paramètres suivants :

  | Paramètre | Plus rapide | Plus lent |
  |--- |--- |--- |
  | Répartitions et ordre de répartition | Peu | Beaucoup |
  |  | Exemple : si vous ventilez A par Z, le nombre d’éléments d’A doit être toujours inférieur à celui de Z. Dans le cas contraire, la durée de la requête peut augmenter de façon significative. |
  | Période | Courte période | Longue période |
  | Filtrage | Filtrage spécifique | Filtrage de type « Le plus populaire » |
  | Granularité | Agrégé | Toutes les heures<ul><li>Quotidien</li><li>Hebdomadaire</li><li>Mensuel</li><li>Trimestriel</li><li>Annuel</li></ul> |
  | Nombre d’entrées | Petit jeu de données | Jeu de données volumineux |

* **Heure de planification** : planifiez une planification plus échelonnée sur une période de 24 heures (voir le tableau ci-dessous). Les signets, les tableaux de bord et les classeurs du Report Builder planifiés de façon rapprochée peuvent entraîner des retards. Planifiez les requêtes volumineuses et plus complexes tôt le matin pour permettre les extractions et les actualisations manuelles pendant la journée de travail.

  | Heures de planification | 01:00 - 02:00 | 02:00 - 07:00 | 07:00 - 18:00 | 18:00 - minuit |
  |--- |--- |--- |--- |--- |
  | Utilisation du Report Builder | Peu occupé | Très occupé | Utilisation du côté client<br>Nombre plus élevé d’utilisateurs effectuant une actualisation locale et demandant un envoi immédiat.<br>De plus, vérifiez si la file d’attente de l’API est effacée lorsque les classeurs planifiés expirent. | Pas occupé |

* **Délais d’expiration** : tout rapport planifié expire au bout de quatre heures. Le système tente d’effectuer la planification trois autres fois, ce qui peut entraîner un échec. (En règle générale, plus le jeu de données est volumineux, plus l’exécution prend du temps.) Ces informations sont affichées dans les rapports [!DNL Analytics] et le Report Builder :

## Exemples de descriptions de message d’erreur {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

Cette section comprend un exemple de liste des messages d’erreur qui peuvent se produire lorsque vous utilisez Report Builder.

>[!NOTE]
>
>Il s’agit d’un exemple de messages d’erreur, qui n’est pas exhaustif. Pour plus d’informations sur la résolution des erreurs, contactez votre administrateur.

* **Cette fonctionnalité peut uniquement être appliquée à un classeur ouvert.** : si aucun classeur (feuilles de calcul) n’est ouvert dans Excel et que vous cliquez sur l’une des icônes de la barre d’outils Report Builder, ce message s’affiche. En outre, la barre d’outils devient inactive jusqu’à ce que vous ouvriez une feuille de calcul. Vous pouvez toutefois cliquer sur l’icône de l’aide en ligne lorsque la barre d’outils est encore active sans engendrer cette erreur.
* **Vous devez quitter l’[!UICONTROL Assistant Requête] avant d’activer le [!UICONTROL Gestionnaire de requêtes].**: Le [!UICONTROL Gestionnaire de requêtes] et l’[!UICONTROL Assistant Requête] constituent une fonctionnalité liée. Il n’est toutefois pas possible de commencer à utiliser le [!UICONTROL Gestionnaire de requêtes] avant d’avoir terminé ou annulé les tâches entreprises dans l’[!UICONTROL Assistant Requête].
* **Aucune requête n’est associée à cette plage.**: Ce message d’erreur s’affiche si vous cliquez sur le bouton [!UICONTROL De la feuille] du [!UICONTROL Gestionnaire de requêtes] alors qu’une cellule de la feuille de calcul ne contient aucune requête. Afin d’identifier les cellules de la feuille de calcul qui contiennent des requêtes, cliquez sur les requêtes individuelles répertoriées dans le tableau du [!UICONTROL Gestionnaire de requêtes]. Si la requête sélectionnée dans le tableau est associée aux cellules, celles-ci sont surlignées.
* **La plage sélectionnée n’est pas valide. Sélectionnez une autre plage.**: Cette erreur s’affiche si vous sélectionnez, dans une feuille de calcul, une cellule à laquelle est déjà associée une requête. Supprimez la requête associée aux cellules ou sélectionnez une autre plage de cellules à mettre en correspondance. Si vous souhaitez supprimer les cellules, il est important de localiser celles qui contiennent des requêtes et de supprimer les requêtes avant de supprimer les cellules (suppression des lignes ou colonnes).
* **Veuillez quitter la cellule Excel active avant d’utiliser cette fonctionnalité.**: Cette erreur s’affiche si vous êtes en *mode d’édition* dans une cellule Excel et que vous cliquez sur l’une des icônes du Report Builder. Le mode d’édition dans une cellule Excel signifie que la cellule est sélectionnée et que le curseur s’affiche à l’intérieur de celle-ci. Vous êtes également en mode d’édition dans une cellule Excel lorsque vous entrez directement des données dans la barre [!UICONTROL Formule] ou dans la zone [!UICONTROL Nom] en haut de la fenêtre Excel.
* **La plage sélectionnée chevauche une autre plage de la requête. Veuillez modifier votre sélection.**: Cette erreur s’affiche si vous avez déjà mis en correspondance un ensemble de cellules à la feuille de calcul.
* **Réparations du classeur (enregistrements supprimés : formule à partir de /xl/calcChain.xml)** : il arrive que les formules d’un classeur soient endommagées lors de l’enregistrement ou du transfert. Lors de l’ouverture du fichier, Excel tente d’exécuter ces formules et échoue. Vous pouvez résoudre ce problème en supprimant `calcChain.xml` de la feuille de calcul, ce qui force Excel à actualiser ses calculs de formule.
   1. Renommez l’extension de fichier du classeur `.xlsx` en `.zip`.
   2. Décompressez le contenu et ouvrez le dossier `/xl/`.
   3. Supprimer `calcChain.xml`.
   4. Compressez à nouveau le contenu et redéfinissez l’extension de fichier sur `.xlsx`.
   5. Ouvrez le classeur dans Excel et actualisez toutes les requêtes de Report Builder.
* **Les cellules Excel associées aux filtres d’entrée ou une plage de sortie peuvent avoir été supprimées** : Report Builder utilise des noms Excel pour joindre des requêtes de données aux cellules. Si vous supprimez des noms Excel dans le Gestionnaire de noms, cette erreur apparaît. Les requêtes ne peuvent pas être récupérées si des noms Excel sont supprimés. Si le classeur a été planifié, vous pouvez télécharger une copie à partir du Gestionnaire de planification ou ouvrir des copies du classeur précédemment diffusées.
