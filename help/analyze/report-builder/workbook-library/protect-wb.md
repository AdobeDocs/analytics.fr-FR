---
description: 'Vous pouvez protéger toutes les requêtes d’un classeur contre l’ajout et la modification des demandes en verrouillant le classeur. Cette option permet la modification hors ligne des classeurs en mettant en pause toutes les requêtes de rapport pour une modification plus efficace. '
title: Verrouillez/déverrouillez des classeurs
topic: Report builder
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Verrouillez/déverrouillez des classeurs

Vous pouvez protéger toutes les requêtes d’un classeur contre l’ajout et la modification des demandes en verrouillant le classeur. Cette option permet la modification hors ligne des classeurs en mettant en pause toutes les requêtes de rapport pour une modification plus efficace. 

En tant qu’analyste, le verrouillage d’un classeur permet de protéger vos requêtes contre les modifications apportées par d’autres utilisateurs de votre entreprise. En même temps, les autres utilisateurs peuvent tout de même actualiser les requêtes du classeur.

Pour protéger un classeur contre la modification, cliquez sur **[!UICONTROL Verrouillé]** dans la barre d’outils du Créateur de rapports ( ![](assets/locked_icon.png)

).

Pour annuler la protection d’un classeur, cliquez sur **[!UICONTROL Déverrouillé]** ( ![](assets/unlocked_icon.png)

).

Vous pouvez déverrouiller un classeur verrouillé si vous êtes doté de l’une des autorisations suivantes :

* Vous êtes administrateur, ou
* Vous êtes la personne qui a initialement verrouillé le classeur. Dans ce cas, il n’est pas requis d’être administrateur.

> [!NOTE] Vous ne pouvez pas ajouter une requête à un classeur protégé, sauf si vous êtes autorisé à déverrouiller le classeur.

Lorsqu’un classeur est verrouillé pour empêcher la modification de requête :

* Les utilisateurs ne peuvent pas créer/ajouter de requêtes.
* Les utilisateurs ne peuvent pas modifier de requêtes par l’intermédiaire de l’Assistant Requête.
* Les utilisateurs ne peuvent pas modifier de requêtes par l’intermédiaire des fonctionnalités Modifier plusieurs requêtes.
* Les utilisateurs ne peuvent pas couper, copier ou coller des requêtes. Néanmoins, les utilisateurs peuvent tout de même utiliser le menu contextuel natif d’Excel Couper/Copier/Coller afin de couper/copier/coller le contenu des requêtes.
* Les utilisateurs peuvent actualiser les requêtes, soit individuellement, soit en tant que partie d’un groupe.
* Si la requête utilise les valeurs d’entrée provenant des cellules (période, segment, filtres), les utilisateurs peuvent modifier ces valeurs dans les cellules et, ainsi, indirectement modifier les requêtes en les actualisant.

If you try to edit a protected workbook (through the context menu, or **[!UICONTROL Request Manager]**, or **[!UICONTROL Edit Multiple Requests]**), you may or may not be allowed to do so:

* Si vous ne possédez pas les autorisations de déverrouiller la ou les requête(s), cette invite s’affiche :

   ![](assets/locked_workbook_error.png)

* Si vous possédez les autorisations requises, aucune invite ne s’affiche et vous pouvez modifier la requête.

## Processus {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Présumons que le classeur A comporte une requête qui se trouve à l’état verrouillé et qui a été créée par l’utilisateur A.

**Exemple 1 : Utilisateur administrateur (ou Utilisateur A)**

1. L’utilisateur se connecte au Créateur de rapports et ouvre un classeur 
1. Le classeur A est actuellement verrouillé, de sorte que le bouton "Créer une requête" est désactivé dans la barre d’outils, ainsi que tous les autres boutons dont la fonctionnalité est désactivée par verrouillage.
1. Si l’utilisateur tente d’utiliser un des boutons désactivés, un message s’affiche indiquant que le classeur est actuellement verrouillé.
1. L’utilisateur peut déverrouiller le classeur, ce qui active la fonctionnalité de modification.
1. Une fois déverrouillé, le classeur reste dans cet état jusqu’à ce qu’il soit explicitement reverrouillé.

**Exemple 2 : Utilisateur non administrateur (utilisateur B)**

1. L’utilisateur se connecte au Créateur de rapports et ouvre un classeur 
1. L’utilisateur ne peut pas ajouter/modifier la requête.
1. L’utilisateur ne peut pas déverrouiller le classeur.

