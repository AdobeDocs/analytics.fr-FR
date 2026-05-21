---
description: Découvrez comment protéger toutes les requêtes d’un classeur contre l’ajout et la modification de requêtes par le verrouillage du classeur.
title: Verrouiller et déverrouiller des classeurs
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
feature: Report Builder
role: User, Admin
exl-id: b5a83532-9fa7-4f1f-b744-e5d74781fffb
TQID: https://experienceleague.adobe.com/0UyYFqVn5qAIimI3obHdsBbTsRirLl6llZf8Y3endLo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 475
ht-degree: 22%

---

# Verrouiller et déverrouiller des classeurs

{{legacy-arb}}

Vous pouvez protéger toutes les requêtes d’un classeur contre l’ajout et la modification de requêtes en verrouillant le classeur. Cette option permet la modification hors ligne des classeurs en mettant en pause toutes les requêtes de rapport pour une modification plus efficace.

En tant qu’analyste, le verrouillage d’un classeur vous permet de protéger vos requêtes de classeur contre la falsification par d’autres utilisateurs de votre entreprise. Dans le même temps, ces utilisateurs peuvent toujours actualiser les requêtes dans le classeur.

Pour protéger un classeur contre la modification, cliquez sur **[!UICONTROL Verrouillé]** dans la barre d’outils Report Builder (![](assets/locked_icon.png)).

Pour annuler la protection d’un classeur, cliquez sur **[!UICONTROL Déverrouillé]** ( ![](assets/unlocked_icon.png)).

Vous pouvez déverrouiller un classeur verrouillé si vous êtes doté de l’une des autorisations suivantes :

* Vous êtes un administrateur, ou
* Vous êtes la personne qui a initialement verrouillé le classeur. Dans ce cas, il n’est pas nécessaire d’être administrateur.

>[!NOTE]
>
>Vous ne pouvez pas ajouter une demande à un classeur protégé à moins d’être autorisé à déverrouiller le classeur.

Lorsqu’un classeur est verrouillé pour la modification de la demande,

* Les utilisateurs ne peuvent pas créer ni ajouter de requêtes.
* Les utilisateurs ne peuvent pas modifier les demandes via l’Assistant Requête.
* Les utilisateurs ne peuvent pas modifier les demandes via les fonctionnalités Modifier plusieurs demandes .
* Les utilisateurs et utilisatrices ne peuvent pas couper, copier ni coller les demandes. Cependant, les utilisateurs peuvent toujours utiliser le menu contextuel Excel Couper/Copier/Coller pour couper/copier/coller le contenu de la ou des requêtes.
* Les utilisateurs et utilisatrices peuvent actualiser les requêtes, individuellement ou dans le cadre d’un groupe.
* Si la requête utilise des valeurs d’entrée provenant de cellules (période, segment, filtres), les utilisateurs et utilisatrices peuvent modifier ces valeurs dans les cellules et donc modifier indirectement les requêtes en les actualisant.

Si vous essayez de modifier un classeur protégé par le biais du menu contextuel, du **[!UICONTROL Gestionnaire de requêtes]** ou du **[!UICONTROL Modifier plusieurs requêtes]**, vous pouvez être autorisé ou non à le faire :

* Si vous ne disposez pas des autorisations nécessaires pour déverrouiller une demande, un message s’affiche vous indiquant que vous ne disposez pas des droits nécessaires pour déverrouiller et modifier le classeur.

  ![Capture d’écran affichant le message d’erreur lorsque vous n’êtes pas autorisé à déverrouiller une requête.](assets/locked_workbook_error.png)

## Processus {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Présumons que le classeur A comporte une requête qui se trouve à l’état verrouillé et qui a été créée par l’utilisateur A.

**Exemple 1 : utilisateur administrateur (ou utilisateur A)**

1. L’utilisateur se connecte au Report Builder et ouvre un classeur
1. Le classeur A est actuellement verrouillé. De ce fait, le bouton « Créer une requête » est désactivé dans la barre d’outils ainsi que tous les autres boutons dont le fonctionnement est désactivé par le verrouillage.
1. Si l’utilisateur tente d’utiliser l’un des boutons désactivés, un message s’affiche indiquant que le classeur est actuellement verrouillé.
1. L’utilisateur peut déverrouiller le classeur, ce qui active une fonctionnalité de modification complète.
1. Après le déverrouillage, le classeur reste déverrouillé jusqu’à ce qu’il soit explicitement reverrouillé.

**Exemple 2 : utilisateur non administrateur (utilisateur B)**

1. L’utilisateur se connecte au Report Builder et ouvre un classeur
1. L’utilisateur ou l’utilisatrice ne peut pas ajouter ni modifier la demande.
1. Impossible de déverrouiller le classeur.
