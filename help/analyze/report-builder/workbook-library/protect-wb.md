---
description: Découvrez comment protéger toutes les requêtes d’un classeur contre l’ajout et la modification de requêtes en verrouillant le classeur.
title: Comment verrouiller et déverrouiller des classeurs
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
feature: Report Builder
role: User, Admin
exl-id: b5a83532-9fa7-4f1f-b744-e5d74781fffb
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 69%

---

# Verrouillage et déverrouillage de classeurs

Vous pouvez protéger toutes les requêtes d’un classeur contre l’ajout et la modification des demandes en verrouillant le classeur. Cette option permet la modification hors ligne des classeurs en mettant en pause toutes les requêtes de rapport pour une modification plus efficace.

En tant qu’analyste, le verrouillage d’un classeur permet de protéger vos requêtes contre les modifications apportées par d’autres utilisateurs de votre entreprise. En même temps, les autres utilisateurs peuvent tout de même actualiser les requêtes du classeur.

Pour protéger un classeur contre la modification, cliquez sur **[!UICONTROL Verrouillé]** dans la barre d’outils de Report Builder ( ![](assets/locked_icon.png)).

Pour annuler la protection d’un classeur, cliquez sur **[!UICONTROL Déverrouillé]** ( ![](assets/unlocked_icon.png)).

Vous pouvez déverrouiller un classeur verrouillé si vous êtes doté de l’une des autorisations suivantes :

* Vous êtes administrateur, ou
* Vous êtes la personne qui a initialement verrouillé le classeur. Dans ce cas, il n’est pas requis d’être administrateur.

>[!NOTE]
>
>Vous ne pouvez pas ajouter de requête à un classeur protégé si vous ne disposez pas des autorisations nécessaires pour le déverrouiller.

Lorsqu’un classeur est verrouillé pour empêcher la modification de requête :

* Les utilisateurs ne peuvent pas créer ni ajouter de requêtes.
* Les utilisateurs ne peuvent pas modifier de requêtes par l’intermédiaire de l’Assistant Requête.
* Les utilisateurs ne peuvent pas modifier de requêtes par l’intermédiaire des fonctionnalités Modifier plusieurs requêtes.
* Les utilisateurs ne peuvent pas couper, copier ou coller des requêtes. Néanmoins, les utilisateurs peuvent tout de même utiliser le menu contextuel natif d’Excel Couper/Copier/Coller afin de couper/copier/coller le contenu des requêtes.
* Les utilisateurs peuvent actualiser les requêtes, soit individuellement, soit en tant que partie d’un groupe.
* Si la requête utilise les valeurs d’entrée provenant des cellules (période, segment, filtres), les utilisateurs peuvent modifier ces valeurs dans les cellules et, ainsi, indirectement modifier les requêtes en les actualisant.

Si vous essayez de modifier un classeur protégé par le biais du menu contextuel, ou du **[!UICONTROL Gestionnaire de requêtes]**, ou de la fonction **[!UICONTROL Modifier plusieurs requêtes]**, vous pouvez le faire ou non :

* Si vous ne disposez pas des autorisations nécessaires pour déverrouiller une requête, un message s’affiche indiquant que vous n’avez pas les droits de déverrouiller et de modifier le classeur.

  ![Capture d&#39;écran montrant le message d&#39;erreur lorsque vous ne disposez pas des autorisations nécessaires pour déverrouiller une requête.](assets/locked_workbook_error.png)

## Processus {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Présumons que le classeur A comporte une requête qui se trouve à l’état verrouillé et qui a été créée par l’utilisateur A.

**Exemple 1 : utilisateur administrateur (ou utilisateur A)**

1. L’utilisateur se connecte au Report Builder et ouvre un classeur
1. Le classeur A est actuellement verrouillé. De ce fait, le bouton « Créer une requête » est désactivé dans la barre d’outils ainsi que tous les autres boutons dont le fonctionnement est désactivé par le verrouillage.
1. Si l’utilisateur tente d’utiliser un des boutons désactivés, un message s’affiche indiquant que le classeur est actuellement verrouillé.
1. L’utilisateur peut déverrouiller le classeur, ce qui active la fonctionnalité de modification.
1. Une fois déverrouillé, le classeur reste dans cet état jusqu’à ce qu’il soit explicitement reverrouillé.

**Exemple 2 : utilisateur non administrateur (utilisateur B)**

1. L’utilisateur se connecte au Report Builder et ouvre un classeur
1. L’utilisateur ne peut pas ajouter/modifier la requête.
1. L’utilisateur ne peut pas déverrouiller le classeur.
