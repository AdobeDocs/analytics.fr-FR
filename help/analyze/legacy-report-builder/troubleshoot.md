---
description: Découvrez comment optimiser la diffusion Report Builder et obtenez une liste des messages d’erreur qui peuvent se produire.
title: Résolution des problèmes et bonnes pratiques pour le Report Builder
uuid: 36a08143-dc78-40f5-9ce9-7d16980aa27b
feature: Report Builder
role: User, Admin
exl-id: 41a640ce-2316-439b-b3ba-f0bace9af268
TQID: https://experienceleague.adobe.com/al9ySg7-3MCg-NZgdci4bDs4B9jNzpdBxlgBTrew2Hs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1427
ht-degree: 65%

---

# Résolution des problèmes et bonnes pratiques pour le Report Builder

{{legacy-arb}}

Cet article décrit le dépannage et les bonnes pratiques que vous pouvez utiliser pour optimiser Report Builder. Elle inclut également une liste des messages d’erreur qui peuvent s’afficher.

## Utilisateurs du Report Builder 5.0 et ouverture de classeurs 5.1 {#section_C29898775999453FABB5FB0E098415C8}

Adobe a remplacé le séparateur entre les dimensions et les classifications représenté par un trait de soulignement (_) par ||. Ce changement a des répercussions de compatibilité pour un utilisateur du Report Builder 5.0 qui ouvre un classeur de la version 5.1 avec des demandes de classification. Chaque fois qu’un classeur d’une version antérieure à la version 5.1 est ouvert, toutes ses demandes de classification sérialisées sont converties dans ce format.

Ceci crée toutefois un problème de compatibilité : une fois qu’un classeur converti au format 5.1 est partagé avec un utilisateur de la version 5.0, cet utilisateur ne peut plus reconnaître la demande de classification (« _ » est recherché à la place de « || » dans la version 5.1).

L’effet secondaire suivant se produit lors de l’ouverture d’un classeur ARB 5.1 avec la demande de classification :

* Lors de l’ouverture du classeur, l’avertissement suivant s’affiche : « Ce classeur a été enregistré pour la dernière fois à l’aide de Report Builder v5.1. Cette version a introduit certaines fonctionnalités qui sont incompatibles avec la version Report Builder installée sur cet ordinateur. Nous vous recommandons de mettre à niveau votre version du Report Builder avant de mettre à jour ce classeur. »
* Si vous cliquez avec le bouton droit de la souris sur une requête ARB avec classification, les menus contextuels de Report Builder (modifier la requête, ajouter une requête dépendante, etc.) ne s’affichera pas.
* Si vous actualisez tout, en cliquant sur le troisième bouton ou en actualisant un ensemble de requêtes issues du formulaire du Gestionnaire de requêtes, la demande de classification s’exécutera sans erreur. Toutefois, les valeurs de classification ne seront pas inscrites.
* Vous pouvez modifier la requête en ouvrant le Gestionnaire de requêtes, puis passer d’une ligne à l’autre jusqu’à la requête recherchée.
* Si vous modifiez la requête sans changer aucun des paramètres, puis cliquez sur Terminer, la réponse sera correctement inscrite. En fait, la modification de la requête résout le problème puisque les paramètres de mise en page des réponses sont resérialisés. Il s’agit donc d’une solution, même si elle prend du temps.

## Problèmes d’authentification dans le Report Builder {#section_FD79104DF1414FE2B36591606C963DE6}

Le Report Builder requiert une authentification pour créer des requêtes de données à partir de vos suites de rapports. Parfois, la connexion à Report Builder peut rencontrer des problèmes en fonction de vos paramètres dans [!DNL Analytics] ou votre réseau.

* **Société de connexion non valide** : cette erreur se produit généralement lorsque la société de connexion n’est pas saisie correctement ou en cas de problèmes réseau. Procédez comme suit :
   * Vérifiez l’orthographe des informations de connexion de la société pour vous assurer qu’il n’y a pas de faute de frappe ou d’espace en trop.
   * Connectez-vous à Analytics à l’aide des mêmes informations de connexion pour vous assurer qu’elles sont correctes. Si vous ne parvenez pas à vous connecter à l’aide de ces informations d’identification, contactez un administrateur de votre société pour obtenir les informations de connexion correctes de la société.
* **Pare-feu** : Report Builder utilise les ports 80 et 443. Vérifiez que ces ports sont autorisés à travers le pare-feu de votre société. Pour obtenir des informations sur les autres exclusions de pare-feu, reportez-vous aux adresses IP internes d’Adobe.

## Recommandations pour optimiser les requêtes {#section_33EF919255BF46CD97105D8ACB43573F}

Les facteurs suivants peuvent rendre les requêtes plus complexes, ce qui peut ralentir le processus de traitement.

* **Facteurs pouvant ralentir les diffusions** : un trop grand nombre de signets, de tableaux de bord et de classeurs Report Builder planifiés en quelques heures. Prenez également en compte le fait que trop de classeurs Report Builder ont été planifiés à peu près à la même heure. Lorsque cela se produit, la file d’attente de l’API de rapports comporte des travaux en souffrance.
* **Facteurs pouvant ralentir l’exécution du classeur** : augmentation significative des classifications ou de la période de requête au fil du temps.
* **Causes des échecs de remise de classeurs** : des formules Excel complexes dans un classeur, en particulier celles qui impliquent la date et l’heure.
* **Cellules renvoyant des zéros (aucune valeur)** : si le nom de la feuille Excel comporte une apostrophe ou un guillemet simple, Report Builder ne renvoie aucune valeur. (Il s’agit d’une limitation de Microsoft Excel.)
* **Performances des requêtes individuelles** : les paramètres ci-dessous peuvent avoir une incidence sur la vitesse de traitement :

  | Paramètre | Plus rapide | Plus lent |
  |--- |--- |--- |
  | Répartitions et ordre de répartition | Peu | Beaucoup |
  |  | Exemple : si vous ventilez A par Z, le nombre d’éléments d’A doit être toujours inférieur à celui de Z. Dans le cas contraire, la durée de la requête peut augmenter de façon significative. |  |
  | Période | Courte période | Longue période |
  | Filtrage | Filtrage spécifique | Filtrage de type « Le plus populaire » |
  | Granularité | Agrégé | Toutes les heures<ul><li>Quotidien</li><li>Hebdomadaire</li><li>Mensuel</li><li>Trimestriel</li><li>Annuel</li></ul> |
  | Nombre d’entrées | Petit jeu de données | Jeu de données volumineux |

* **Heure de planification** : échelonnez la planification sur une période de 24 heures (voir le tableau ci-dessous). Les signets, les tableaux de bord et les classeurs du Report Builder planifiés de façon rapprochée peuvent entraîner des retards. Planifiez les requêtes volumineuses et plus complexes tôt le matin pour permettre les extractions et les actualisations manuelles pendant la journée de travail.

  | Heures de planification | 01:00 - 02:00 | 02:00 - 07:00 | 07:00 - 18:00 | 18:00 - minuit |
  |--- |--- |--- |--- |--- |
  | Utilisation du Report Builder | Peu occupé | Très occupé | Utilisation du côté client<br>Augmentation du nombre d’utilisateurs et utilisatrices qui s’actualisent localement et qui demandent « Envoyer immédiatement »<br> Vérifiez également que la file d’attente d’API est effacée lorsque les classeurs planifiés expirent. | Pas occupé |

* **Délais d’expiration** : tous les rapports planifiés expirent au bout de quatre heures. Le système tente d’effectuer la planification trois autres fois, ce qui peut entraîner un échec. (En règle générale, plus le jeu de données est volumineux, plus son exécution est longue.) Ceux-ci sont visibles dans les rapports [!DNL Analytics] et Report Builder :

## Exemples de descriptions de message d’erreur {#section_3DF3A1EEDAD149CB941BEABEF948A4A5}

Cette section comprend un exemple de liste des messages d’erreur qui peuvent se produire lorsque vous utilisez Report Builder.

>[!NOTE]
>
>Voici un exemple de messages d’erreur, et non une liste exhaustive. Pour plus d’informations sur la résolution des erreurs, contactez votre administrateur.

* **Cette fonction ne peut être appliquée que sur un classeur ouvert.** : si aucun classeur (feuilles de calcul) n’est ouvert dans Excel et que vous cliquez sur l’une des icônes de la barre d’outils Report Builder, ce message s’affiche. En outre, la barre d’outils devient inactive jusqu’à ce que vous ouvriez une feuille de calcul. Vous pouvez toutefois cliquer sur l’icône de l’aide en ligne lorsque la barre d’outils est encore active sans engendrer cette erreur.
* **Vous devez d’abord quitter l’[!UICONTROL Assistant Requête]avant d’activer le [!UICONTROL Gestionnaire de requêtes].** : bien que le [!UICONTROL Gestionnaire de requêtes] et l’[!UICONTROL Assistant Requête] soient fonctionnellement liés, il n’est pas possible de commencer à travailler avec le [!UICONTROL Gestionnaire de requêtes] avant d’avoir terminé ou annulé les actions entreprises dans le  Assistant de requêtes.
* **Aucune requête n’est associée à cette plage.** : ce message d’erreur s’affiche si vous cliquez sur le bouton [!UICONTROL À partir de la feuille] du [!UICONTROL Gestionnaire de requêtes] alors qu’une cellule de la feuille de calcul ne contient aucune requête. Afin d’identifier les cellules de la feuille de calcul qui contiennent des requêtes, cliquez sur les requêtes individuelles répertoriées dans le tableau du [!UICONTROL Gestionnaire de requêtes]. Si la requête sélectionnée dans le tableau est associée aux cellules, celles-ci sont surlignées.
* **La plage sélectionnée n’est pas valide. Veuillez sélectionner une autre plage.** : Cette erreur s&#39;affiche si vous sélectionnez une cellule de la feuille de calcul à laquelle est déjà associée une demande. Supprimez la requête associée aux cellules ou sélectionnez une autre plage de cellules à mettre en correspondance. Si vous souhaitez supprimer les cellules, il est important de localiser celles qui contiennent des requêtes et de supprimer les requêtes avant de supprimer les cellules (suppression des lignes ou colonnes).
* **Veuillez quitter la cellule Excel active avant d’utiliser cette fonctionnalité.** : Si vous êtes en *mode d’édition* dans une cellule Excel et que vous cliquez sur l’une des icônes Report Builder, ce message d’erreur s’affiche. Le mode d’édition dans une cellule Excel signifie que la cellule est sélectionnée et que le curseur s’affiche à l’intérieur de celle-ci. Vous êtes également en mode d’édition dans une cellule Excel lorsque vous entrez directement des données dans la barre [!UICONTROL Formule] ou dans la zone [!UICONTROL Nom] en haut de la fenêtre Excel.
* **La plage sélectionnée chevauche une autre plage de la requête. Modifiez votre sélection.** : Cette erreur s&#39;affiche si vous avez déjà mis en correspondance un ensemble de cellules à la feuille de calcul.
* **Réparations du classeur (enregistrements supprimés : formule à partir de /xl/calcChain.xml)** : il arrive que les formules d’un classeur soient endommagées lors de l’enregistrement ou du transfert. Lors de l’ouverture du fichier, Excel tente d’exécuter ces formules et échoue. Vous pouvez résoudre ce problème en supprimant `calcChain.xml` de la feuille de calcul, ce qui force Excel à actualiser ses calculs de formule.
   1. Renommez l’extension de fichier du classeur `.xlsx` en `.zip`.
   2. Décompressez le contenu et ouvrez le dossier `/xl/`.
   3. Supprimer `calcChain.xml`.
   4. Compressez à nouveau le contenu et redéfinissez l’extension de fichier sur `.xlsx`.
   5. Ouvrez le classeur dans Excel et actualisez toutes les requêtes de Report Builder.
* **Les cellules Excel associées aux filtres d’entrée ou une plage de sortie peuvent avoir été supprimées** : Report Builder utilise des noms Excel pour joindre des requêtes de données aux cellules. Si vous supprimez des noms Excel dans le Gestionnaire de noms, cette erreur apparaît. Les requêtes ne peuvent pas être récupérées si des noms Excel sont supprimés. Si le classeur a été planifié, vous pouvez télécharger une copie à partir du Gestionnaire de planification ou ouvrir des copies du classeur précédemment diffusées.
