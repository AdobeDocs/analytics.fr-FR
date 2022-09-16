---
description: Partage de projets et rôles de projets dans Workspace
keywords: Partage de projets Analysis Workspace
title: Partage de projets
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
source-git-commit: 5454995fb9d6e63fb19e2272f66f3c96bf951ccb
workflow-type: tm+mt
source-wordcount: '1121'
ht-degree: 100%

---

# Partage de projets

Le partage rend un projet disponible pour d’autres utilisateurs d’Analysis Workspace de votre entreprise. Les [traitements](curate.md) appliqués sont répercutés lorsque les destinataires ouvrent le projet.

Regardez cet aperçu vidéo sur le partage de projet :

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)

## Rôles de projet {#Roles}

Vous pouvez ajouter des destinataires à l’un des trois rôles de projet. Les rôles de projet sont liés à l’utilisateur et à l’identifiant de projet spécifique. Les rôles de projet ne dépendent pas des autorisations d’utilisateurs gérées dans l’[Admin Console pour Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr).

| Rôle | Contrôle du projet |
| --- | --- |
| Peut modifier | Les destinataires peuvent **[!UICONTROL Enregistrer]** les modifications dans un projet et agir en tant que copropriétaires. Ce rôle est utile si vous souhaitez cogérer un projet avec d’autres collègues. Cela comprend la modification, la suppression et la modification des listes de destinataires pour un projet partagé. <br>Remarque : Analysis Workspace ne prend actuellement pas en charge la collaboration en direct. Il est donc recommandé qu’un seul utilisateur modifie un projet à la fois. Si les projets sont enregistrés en même temps, la dernière version est conservée. |
| Peut dupliquer | Les destinataires peuvent **[!UICONTROL Enregistrer sous]** et ont accès au rail de gauche. Les interactions avec le projet ne sont pas limitées dans ce rôle. Ce rôle est utile si vous souhaitez partager un projet avec des utilisateurs qui comprennent les données de votre entreprise et comment utiliser Analysis Workspace, mais que vous ne souhaitez pas que votre projet soit modifié. |
| Peut afficher | Les destinataires ne peuvent pas Enregistrer sous et n’ont pas accès au rail de gauche. Les interactions avec le projet sont également limitées. Ce rôle est utile si vous souhaitez partager un projet avec des utilisateurs qui connaissent moins bien la structure de données de votre entreprise, Analysis Workspace ou Adobe Analytics en général. Cependant, vous souhaitez tout de même qu’ils consomment des données et des informations dans un environnement sûr.<br>En savoir plus sur l’[expérience du projet Peut afficher](/help/analyze/analysis-workspace/curate-share/view-only-projects.md). |

Regardez cette vidéo sur les projets en lecture seule dans Analysis Workspace :

>[!VIDEO](https://video.tv.adobe.com/v/36206/?quality=12)

>[!IMPORTANT]
> Les destinataires de projet ajoutés avant le 18 juin 2020 ont été migrés dans un rôle de projet. Les utilisateurs administrateurs ont effectué la migration vers le rôle **[!UICONTROL Peut modifier]** et les utilisateurs non-administrateurs ont effectué la migration vers le rôle **[!UICONTROL Peut dupliquer]**. Ces rôles offrent la même expérience de projet que celle qu’ils avaient auparavant. En outre, tous les groupes (y compris « Tous ») ont migré vers le rôle **[!UICONTROL Peut dupliquer]**.

### Aucun rôle attribué (destinataires de lien de projet)

Si un destinataire ne se voit pas attribuer un rôle et reçoit un [lien](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=fr) vers le projet (**[!UICONTROL Partager] > [!UICONTROL Obtenir le lien du projet]**), il se verra attribuer un rôle par défaut. Les administrateurs reçoivent **[!UICONTROL Peut modifier]** et les non-administrateurs reçoivent **[!UICONTROL Peut dupliquer]**.

### Plusieurs rôles attribués

Si un destinataire reçoit plusieurs rôles, il obtient toujours l’expérience la plus élevée. Cela peut se produire si un destinataire est ajouté à la fois en tant qu’individu et en tant que membre d’un groupe. Par exemple, si un destinataire reçoit le rôle **[!UICONTROL Peut modifier]** en tant qu’individu et le rôle **[!UICONTROL Peut afficher]** en tant que membre d’un groupe, il reçoit une expérience de projet **[!UICONTROL Peut modifier]**.

### Administrateurs et rôles

Les administrateurs se voyant attribuer un rôle **[!UICONTROL Peut dupliquer]** ou **[!UICONTROL Peur afficher]** reçoivent ces expériences limitées lorsqu’ils ouvrent un projet. Si vous le souhaitez, un administrateur peut augmenter son rôle pour obtenir le rôle **[!UICONTROL Peut modifier]** à tout moment via **[!UICONTROL Composants] > [!UICONTROL Projets]**.

## Ajout de destinataires au projet partagé {#Add}

Pour ajouter des destinataires au projet partagé :

1. Cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Partager le projet]**.
Si des modifications ne sont pas enregistrées, vous serez d’abord invité à enregistrer votre projet.
1. Ajoutez des destinataires ou des groupes de destinataires.
Pour obtenir la description de chaque rôle, reportez-vous à l’icône d’aide en haut de l’écran.
1. (Facultatif) Partagez avec tous les destinataires les composants de projet incorporés (segments, mesures calculées et périodes).
Une fois partagés, ces composants apparaîtront dans le menu déroulant des composants du Workspace du destinataire. Notez que ce paramètre est ponctuel ; c’est une action unique au moment du partage.
1. (Facultatif) Définissez cette page comme page d’entrée pour les destinataires.
Ce paramètre est ponctuel ; c’est une action unique au moment du partage.
1. Cliquez sur Partager.
Vous pouvez également cliquer sur **[!UICONTROL Traiter et partager]** pour appliquer automatiquement le traitement du projet. Si un projet a déjà été partagé, ces boutons indiqueront **[!UICONTROL Mettre à jour]** et **[!UICONTROL Traiter et mettre à jour]**. En savoir plus sur le [traitement des projets](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=fr).

![](assets/share-proj-modal.png)

## Partage avec des groupes de destinataires {#Groups}

Tous les utilisateurs peuvent partager des projets avec des groupes, qui représentent un ensemble de destinataires. Dans Adobe Analytics, les groupes sont définis par profils de produits dans l’[Admin Console pour Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

* Les administrateurs peuvent partager des projets avec n’importe quel groupe, y compris « Tous ».
* Les non-administrateurs peuvent partager des projets avec des groupes dont ils sont membres, à l’exception de « Tous ».

## Partage d’un lien de projet {#Links}

Vous pouvez obtenir un lien vers un projet sous **[!UICONTROL Partager] > [!UICONTROL Obtenir le lien du projet]**. Lorsque vous cliquez dessus, les destinataires doivent se connecter avant d’accéder au projet. Si les destinataires n’ont pas reçu de rôle, ils recevront un rôle par défaut. Les administrateurs reçoivent **[!UICONTROL Peut modifier]** et les non-administrateurs reçoivent **[!UICONTROL Peut dupliquer]**. [En savoir plus](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html) sur la création de liens partageables vers des projets Workspace.

## Partage de projets dans le gestionnaire de projets {#Manager}

Les projets peuvent également être partagés à partir de **[!UICONTROL Composants] > [!UICONTROL Projets]**. Un seul projet peut être partagé en suivant les mêmes étapes que celles décrites ci-dessus.  Si plusieurs projets sont sélectionnés pour le partage, des destinataires seront ajoutés à la liste existante de destinataires pour chaque projet.

Par exemple :

* Le projet A est partagé avec les destinataires 1, 2 et 3.
* Le projet B est partagé avec les destinataires 4, 5 et 6.

Si les projets A et B sont sélectionnés, les destinataires 4 et 7 sont ajoutés aux listes de partage. Voici les nouvelles listes de partage des projets :

* Projet A : 1, 2, 3, 4 et 7
* Projet B : 4, 5, 6 et 7

![](assets/mult-proj-sharing.png)

## Partage de composants intégrés

Regardez une vidéo sur ce sujet :

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## Questions fréquentes {#FAQs}

| Question | Réponse |
| --- | --- |
| Que se passe-t-il si deux éditeurs enregistrent un projet en même temps ? | Les modifications ne sont pas fusionnées et la dernière version enregistrée du projet sera conservée. Analysis Workspace ne prend actuellement pas en charge la collaboration en direct. |
| En tant qu’administrateur, quelle expérience de projet vais-je voir ? | Les administrateurs se voyant attribuer un rôle **[!UICONTROL Peut dupliquer]** ou **[!UICONTROL Peur afficher]** reçoivent ces expériences limitées lorsqu’ils ouvrent un projet. Si vous le souhaitez, un administrateur peut augmenter son rôle pour obtenir le rôle **[!UICONTROL Peut modifier]** à tout moment via **[!UICONTROL Composants] > [!UICONTROL Projets]**. |
| Que se passe-t-il si un destinataire reçoit un rôle en tant qu’individu et un autre rôle en tant que membre d’un groupe ? | Si un destinataire reçoit plusieurs rôles, il obtient toujours l’expérience la plus élevée. Par exemple, si un destinataire reçoit le rôle **[!UICONTROL Peut modifier]** en tant qu’individu et le rôle **[!UICONTROL Peut afficher]** en tant que membre d’un groupe, il reçoit une expérience de projet **[!UICONTROL Peut modifier]**. |
| Quelle expérience obtient un destinataire s’il ouvre un lien de projet ? | Les destinataires reçoivent le rôle que vous leur avez attribué dans le modal de partage. Si un destinataire ne se voit pas attribuer un rôle et reçoit un lien vers le projet (**[!UICONTROL Partager] > [!UICONTROL Obtenir le lien du projet]**), il se verra attribuer un rôle par défaut. Les administrateurs reçoivent **[!UICONTROL Peut modifier]** et les non-administrateurs reçoivent **[!UICONTROL Peut dupliquer]**. |
