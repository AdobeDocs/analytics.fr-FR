---
description: Vous pouvez protéger toutes les requêtes d’un classeur contre l’ajout et la modification de requêtes en verrouillant le classeur. Cette option permet la modification hors ligne des classeurs en mettant en pause toutes les requêtes de rapport pour une modification plus efficace.
title: Verrouillez/déverrouillez des classeurs
topic: Report builder
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Verrouillez/déverrouillez des classeurs

Vous pouvez protéger toutes les requêtes d’un classeur contre l’ajout et la modification de requêtes en verrouillant le classeur. Cette option permet la modification hors ligne des classeurs en mettant en pause toutes les requêtes de rapport pour une modification plus efficace.

En tant qu’analyste, le verrouillage d’un classeur vous permet de protéger vos requêtes de classeur contre toute manipulation par d’autres utilisateurs de votre entreprise. En même temps, ces utilisateurs peuvent toujours actualiser les requêtes du classeur.

To protect a workbook against editing, click **[!UICONTROL Locked]** on the Report Builder toolbar ( ![](assets/locked_icon.png)

).

To unprotect a workbook, click **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)

).

Vous pouvez déverrouiller un classeur verrouillé si vous êtes doté de l’une des autorisations suivantes :

* Vous êtes administrateur ou
* Vous êtes la personne qui a initialement verrouillé le classeur. Dans ce cas, vous n’avez pas besoin d’être administrateur.

>[!NOTE] Vous ne pouvez pas ajouter de requête à un classeur protégé si vous ne possédez pas l’autorisation de déverrouiller le classeur.

Lorsqu’un classeur est verrouillé contre la modification des requêtes,

* Les utilisateurs ne peuvent pas créer ni ajouter de requêtes.
* Les utilisateurs ne peuvent pas modifier les requêtes par le biais de l’Assistant Requête.
* Les utilisateurs ne peuvent pas modifier les requêtes au moyen de la fonctionnalité Modifier plusieurs requêtes.
* Les utilisateurs ne peuvent pas couper, copier ou coller des requêtes. Toutefois, les utilisateurs peuvent toujours utiliser le menu contextuel natif Couper/Copier/Coller d’Excel pour couper/copier/coller le contenu des requêtes.
* Les utilisateurs peuvent actualiser les requêtes, individuellement ou dans le cadre d’un groupe.
* Si la requête utilise des valeurs d’entrée provenant de cellules (période, segment, ), les utilisateurs peuvent modifier ces valeurs dans les cellules et, par conséquent, modifier indirectement les requêtes en les actualisant.

Si vous tentez de modifier un classeur protégé (par le biais du menu contextuel, **[!UICONTROL Request Manager]** ou **[!UICONTROL Edit Multiple Requests]**), vous pouvez être autorisé à le faire ou non :

* Si vous n’êtes pas autorisé à déverrouiller les requêtes, cette invite s’affiche :

   ![](assets/locked_workbook_error.png)

* Si vous disposez des autorisations requises, aucune invite ne s’affiche et vous pouvez modifier la requête.

## Processus {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Présumons que le classeur A comporte une requête qui se trouve à l’état verrouillé et qui a été créée par l’utilisateur A.

**Exemple 1 : utilisateur administrateur (ou utilisateur A)**

1. L’utilisateur se connecte au Report Builder et ouvre un classeur
1. Le classeur A est actuellement verrouillé. De ce fait, le bouton « Créer une requête » est désactivé dans la barre d’outils ainsi que tous les autres boutons dont le fonctionnement est désactivé par le verrouillage.
1. Si l’utilisateur tente d’utiliser l’un des boutons désactivés, un message s’affiche indiquant que le classeur est actuellement verrouillé.
1. L’utilisateur peut déverrouiller le classeur, ce qui active une fonctionnalité de modification complète.
1. Une fois déverrouillé, le classeur reste déverrouillé jusqu’à ce qu’il soit explicitement reverrouillé.

**Exemple 2 : utilisateur non administrateur (utilisateur B)**

1. L’utilisateur se connecte au Report Builder et ouvre un classeur
1. L’utilisateur ne peut pas ajouter/modifier la requête.
1. L’utilisateur ne peut pas déverrouiller le classeur.

