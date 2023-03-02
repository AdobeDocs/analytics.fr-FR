---
description: Partage de projets et rôles de projets dans Workspace
keywords: Partage de projets Analysis Workspace
title: Partage de projets
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
source-git-commit: 58abc4a8410441a3c76c6737ace8e2c5ab5c1374
workflow-type: ht
source-wordcount: '1132'
ht-degree: 100%

---

# Partage de projets

Vous pouvez partager un projet avec des utilisateurs et utilisatrices ou des groupes Adobe Analytics existants de votre organisation. Les utilisateurs et utilisatrices avec lesquels vous partagez le projet doivent disposer au préalable d’un compte Adobe Analytics.

Vous pouvez partager un rôle spécifique avec des utilisateurs et utilisatrices ou des groupes, ainsi que partager un lien.

* [Partager un rôle de projet spécifique](#share-a-specific-project-role)

* [Partager un lien vers un projet](#share-a-link-to-a-project)

## Partager un rôle de projet spécifique

Lorsque vous partagez un rôle de projet spécifique avec des utilisateurs et utilisatrices et des groupes de votre organisation, tenez compte des points suivants :

* Les rôles de projet (**[!UICONTROL Peut modifier]**, **[!UICONTROL Peut dupliquer]** et **[!UICONTROL Peut afficher]**) s’appliquent à l’utilisateur ou à l’utilisatrice et à un ID de projet spécifique. Les rôles de projet ne dépendent pas des autorisations d’utilisation gérées dans l’[Admin Console d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr).

* Dans Adobe Analytics, les groupes sont définis par profils de produits dans l’[Admin Console d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr). Les administrateurs et administratrices peuvent partager des projets avec n’importe quel groupe, y compris « Tous ». Les personnes ne disposant pas de droit d’administration peuvent partager des projets avec des groupes dont elles sont membres, à l’exception de « Tous ».

* Si un utilisateur ou une utilisatrice reçoit plusieurs rôles, le rôle le plus élevé s’applique. Cela peut se produire si la personne est ajouté à la fois en tant que personne individuelle et en tant que membre d’un groupe. Par exemple, si un utilisateur ou une utilisatrice reçoit le rôle **[!UICONTROL Peut modifier]** en tant que personne individuelle et le rôle **[!UICONTROL Peut afficher]** en tant que membre d’un groupe, le rôle **[!UICONTROL Peut modifier]** s’applique pour le projet.

* Les administrateurs et administratrices se voyant attribuer un rôle **[!UICONTROL Peut dupliquer]** ou **[!UICONTROL Peut afficher]** bénéficient de ces rôles limités lorsqu’ils ouvrent un projet. En cas de besoin, une personne chargée de l’administration peut augmenter son rôle pour obtenir le rôle **[!UICONTROL Peut modifier]** à tout moment via **[!UICONTROL Composants] > [!UICONTROL Projets]**.

Pour partager un rôle de projet spécifique avec des utilisateurs et utilisatrices ou des groupes de votre organisation, procédez comme suit :

1. Accédez au projet à partager, puis cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Partager le projet]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
Si des modifications ne sont pas enregistrées, on vous invitera d’abord à enregistrer votre projet.

   ![](assets/share-proj-modal.png)

   Pour plus d’informations sur le partage simultané de plusieurs projets, consultez la section [Partager des projets dans le Gestionnaire de projets](#share-projects-in-the-project-manager).

1. Ajoutez des destinataires ou des groupes de destinataires dans l’un des champs de rôle disponibles :

   **Peut modifier :** les destinataires peuvent **[!UICONTROL Enregistrer]** les modifications dans un projet et agir en tant que copropriétaires. Ce rôle est utile si vous souhaitez cogérer un projet avec d’autres collègues. Cela comprend la modification, la suppression et la modification des listes de destinataires pour un projet partagé. <br>Remarque : Analysis Workspace ne prend actuellement pas en charge la collaboration en direct. Il est donc recommandé qu’un seul utilisateur modifie un projet à la fois. Si les projets sont enregistrés en même temps, la dernière version est conservée.

   **Peut dupliquer :** les destinataires peuvent **[!UICONTROL Enregistrer sous]** et ont accès au rail de gauche. Les interactions avec le projet ne sont pas limitées dans ce rôle. Ce rôle est utile si vous souhaitez partager un projet avec des utilisateurs et utilisatrices qui comprennent les données de votre organisation et comment utiliser Analysis Workspace, mais que vous ne souhaitez pas que votre projet soit modifié.

   **Peut afficher :** les destinataires ne peuvent pas **[!UICONTROL Enregistrer]** ou **[!UICONTROL Enregistrer sous]** et n’ont pas accès au rail de gauche. Les interactions avec le projet sont également limitées. Ce rôle est utile si vous souhaitez partager un projet avec des utilisateurs et utilisatrices qui connaissent moins bien la structure de données de votre organisation, Analysis Workspace ou Adobe Analytics en général. Cependant, vous souhaitez tout de même que les utilisateurs et utilisatrices consomment des données et des insights dans un environnement sûr. En savoir plus sur l’[expérience du projet Peut afficher](/help/analyze/analysis-workspace/curate-share/view-only-projects.md).

1. Configurez les options suivantes lors du partage du projet :

   * **Partager les composants intégrés au projet :** partagez avec l’ensemble des destinataires les segments, mesures calculées et périodes. Une fois partagés, ces composants apparaîtront dans le menu déroulant des composants de l’espace de travail de destination. Ce paramètre n’est pas persistant, il s’applique une seule fois, au moment du partage du projet.

   * **Définir comme page de destination pour les destinataires :** définit cette page comme page de destination pour les destinataires. Ce paramètre n’est pas persistant, il s’applique une seule fois, au moment du partage du projet.

1. Cliquez sur **[!UICONTROL Partager]**.
Vous pouvez également cliquer sur **[!UICONTROL Traiter et partager]** pour appliquer automatiquement le traitement du projet. Si un projet a déjà été partagé, ces boutons indiqueront **[!UICONTROL Mettre à jour]** et **[!UICONTROL Traiter et mettre à jour]**. En savoir plus sur le [traitement des projets](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=fr).

## Partager un lien vers un projet

Lorsque vous partagez un lien comme décrit dans cette section, tenez compte des points suivants :

* Les destinataires qui utilisent le lien doivent se connecter à Adobe Analytics avant d’accéder au projet.

* Si la personne destinataire ne se voit pas attribuer un rôle et reçoit un [lien](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=fr) vers le projet (**[!UICONTROL Partager] > [!UICONTROL Obtenir le lien du projet]**), elle se verra attribuer un rôle par défaut. Les personnes chargées de l’administration reçoivent **[!UICONTROL Peut modifier]** et les autres reçoivent **[!UICONTROL Peut dupliquer]**.

Pour partager le lien du projet avec les utilisateurs et utilisatrices de votre organisation, procédez comme suit :

1. Cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Partager le projet]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
Si des modifications ne sont pas enregistrées, on vous invitera d’abord à enregistrer votre projet.

   ![](assets/share-proj-modal.png)

1. Cliquez sur **[!UICONTROL Copier le lien]** en regard du champ **[!UICONTROL de partage d’URL]**.

1. Partagez le lien avec les utilisateurs et utilisatrices de votre organisation. Vous pouvez par exemple le coller dans un e-mail, sur un site web interne, etc.

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
