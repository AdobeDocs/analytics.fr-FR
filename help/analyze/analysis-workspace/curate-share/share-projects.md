---
description: Partage de projets et rôles de projets dans Workspace
keywords: Partage de projets Analysis Workspace
title: Partage de projets
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
source-git-commit: 441484c0547439de2ab1cdc2596fb681592df012
workflow-type: tm+mt
source-wordcount: '1817'
ht-degree: 49%

---

# Partage de projets

Vous pouvez partager un projet Analysis Workspace avec les types de personnes suivants :

* Utilisateurs et groupes de votre entreprise ayant accès à Adobe Analytics

  Vous pouvez partager l’accès Modifier, Dupliquer ou Afficher

* Utilisateurs et groupes de votre entreprise qui n’ont pas accès à Adobe Analytics

  Les destinataires ont un accès en lecture seule

* Personnes en dehors de votre organisation

  Les destinataires ont un accès en lecture seule

Quelconque [traitement](curate.md) votre demande avant le partage est prise en compte lorsque les destinataires ouvrent le projet.

Regardez cet aperçu vidéo sur le partage de projet :

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Partager avec les utilisateurs et les groupes Analysis Workspace de votre entreprise {#Add}

Vous pouvez partager un projet avec des utilisateurs ou des groupes Analysis Workspace existants de votre entreprise. Lorsque vous partagez un projet comme décrit dans cette section, les utilisateurs avec lesquels vous partagez doivent déjà avoir accès à Adobe Analytics.

Vous pouvez partager un rôle spécifique avec des utilisateurs et utilisatrices ou des groupes, ainsi que partager un lien.

* [Partager un rôle de projet spécifique](#share-a-specific-project-role)

* [Partager un lien vers un projet](#share-a-link-to-a-project)

## Partager un rôle de projet spécifique

Lorsque vous partagez un rôle de projet spécifique avec des utilisateurs et utilisatrices et des groupes de votre organisation, tenez compte des points suivants :

* Les rôles de projet (**[!UICONTROL Peut modifier]**, **[!UICONTROL Peut dupliquer]** et **[!UICONTROL Peut afficher]**) s’appliquent à l’utilisateur ou à l’utilisatrice et à un ID de projet spécifique. Les rôles de projet ne dépendent pas des autorisations d’utilisation gérées dans l’[Admin Console d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr).

* Dans Adobe Analytics, les groupes sont définis par profils de produits dans l’[Admin Console d’Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr). Les administrateurs et administratrices peuvent partager des projets avec n’importe quel groupe, y compris « Tous ». Les personnes ne disposant pas de droit d’administration peuvent partager des projets avec des groupes dont elles sont membres, à l’exception de « Tous ».

* Si un utilisateur ou une utilisatrice reçoit plusieurs rôles, le rôle le plus élevé s’applique. Cela peut se produire si la personne est ajouté à la fois en tant que personne individuelle et en tant que membre d’un groupe. Par exemple, si un utilisateur ou une utilisatrice reçoit le rôle **[!UICONTROL Peut modifier]** en tant que personne individuelle et le rôle **[!UICONTROL Peut afficher]** en tant que membre d’un groupe, le rôle **[!UICONTROL Peut modifier]** s’applique pour le projet.

* Les administrateurs et administratrices se voyant attribuer un rôle **[!UICONTROL Peut dupliquer]** ou **[!UICONTROL Peut afficher]** bénéficient de ces rôles limités lorsqu’ils ouvrent un projet. Un administrateur peut remplacer son rôle par **[!UICONTROL Peut modifier]** en partageant le projet avec eux-mêmes et en accordant le rôle Modifier, comme décrit dans la procédure suivante.

Pour partager un rôle de projet spécifique avec des utilisateurs et utilisatrices ou des groupes de votre organisation, procédez comme suit :

1. Accédez au projet que vous souhaitez partager, puis cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Partage avec les utilisateurs de Workspace]**.
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

1. Cliquez sur **[!UICONTROL Partager]**. (Si le projet a déjà été partagé, cliquez sur [!UICONTROL **Mettre à jour**].)

   OU

   Cliquez sur **[!UICONTROL Traitement et partage]** pour appliquer automatiquement le traitement du projet. (Si le projet a déjà été partagé, cliquez sur **[!UICONTROL Traitement et mise à jour]**.) En savoir plus sur le [traitement des projets](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=fr).

## Partager un lien vers un projet

Lorsque vous partagez un lien comme décrit dans cette section, tenez compte des points suivants :

* Les destinataires qui utilisent le lien doivent se connecter à Adobe Analytics avant d’accéder au projet.

* Si un destinataire ne se voit pas attribuer un rôle et reçoit une [link](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=fr) au projet, un rôle leur est attribué par défaut. Les administrateurs reçoivent **[!UICONTROL Peut modifier]** et les non-administrateurs reçoivent **[!UICONTROL Peut dupliquer]**.

Pour partager le lien du projet avec les utilisateurs et utilisatrices de votre organisation, procédez comme suit :

1. Enregistrez le projet. En cas de modifications non enregistrées, vous êtes invité à enregistrer votre projet avant de partager un lien.

1. Sélectionner **[!UICONTROL Partager]** > **[!UICONTROL Partage avec les utilisateurs de Workspace]**, puis sélectionnez **[!UICONTROL Copier]** en regard de **[!UICONTROL Partager par lien]** champ .

   ![](assets/share-proj-modal.png)

1. Partagez le lien avec les utilisateurs et utilisatrices de votre organisation. Vous pouvez par exemple le coller dans un email, sur un site web interne, etc.

## Partage d’un projet avec quiconque (aucune connexion requise) {#share-public-link}

Vous pouvez accorder [accès en lecture seule](/help/analyze/analysis-workspace/curate-share/view-only-projects.md) aux projets Analysis Workspace destinés aux personnes qui n’ont pas accès à Adobe Analytics. Cela peut inclure :

* Personnes en dehors de votre organisation

* Personnes de votre entreprise qui n’ont pas accès à Adobe Analytics

>[!NOTE]
>
>Tenez compte des points suivants lors du partage d’un projet Analysis Workspace avec des personnes qui n’ont pas accès à Adobe Analytics :
>
>* La possibilité de partager un projet de cette manière peut être désactivée par l’administrateur Analytics, comme décrit dans la section [Préférences](/help/analyze/analysis-workspace/user-preferences.md). Si vous ne pouvez pas partager un projet comme décrit dans cette section, votre administrateur Analytics a désactivé cette fonctionnalité.
>
>* Les projets comportant plus de 50 visualisations étendues ne peuvent pas être partagés avec des personnes qui n’ont pas accès à Adobe Analytics.
>
>* Les utilisateurs avec lesquels vous partagez le projet peuvent afficher les filtres qui ont été appliqués au projet pendant la [traitement](curate.md).
> 
>* Les utilisateurs avec lesquels vous partagez peuvent modifier la période du projet. La période que vous définissez pour le projet s’affiche par défaut.
>
>* Un projet peut devenir inaccessible si de nombreux utilisateurs tentent d’accéder simultanément à un lien donné. Par défaut, plus de 190 personnes peuvent accéder à un seul lien toutes les 5 minutes. Si votre entreprise atteint cette limite, patientez 5 minutes, puis tentez à nouveau d’accéder au lien.

La vidéo de démonstration suivante et la documentation qui l’accompagne décrivent les options associées au partage d’un lien avec n’importe qui :

>[!VIDEO](https://video.tv.adobe.com/v/3420093/?learn=on)

Pour partager un projet Analysis Workspace avec des personnes qui n’ont pas accès à Adobe Analytics :

1. Ouvrez le projet Analysis Workspace que vous souhaitez partager.

1. Cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Partager avec n’importe qui]**.

   En cas de modifications non enregistrées, vous êtes invité à enregistrer votre projet.

   <!-- Add screen shot of new modal -->

1. Activez la variable **[!UICONTROL Le lien est principal]** s’il n’est pas déjà activé.

   Cette option crée un lien vers le projet qui peut être partagé avec n’importe qui. Vous pouvez désactiver l’accès au projet à tout moment en désactivant cette option.

   Le propriétaire du projet est également propriétaire de ce lien. La propriété du lien ne peut être transférée à un autre utilisateur que lorsque la propriété du projet est transférée, comme décrit dans la section [Transfert de ressources utilisateur ou définition de l’expiration du compte](/help/admin/admin/user-management2/users-assets.md) dans le guide d’administration d’Analytics.

1. Indiquez si l’option de sécurité suivante doit être activée (cette option peut être contrôlée par votre administrateur Analytics) :

   * **[!UICONTROL Exiger une authentification Experience Cloud]:**

     Lorsque cette option est activée, les seuls utilisateurs qui peuvent accéder au projet sont ceux qui peuvent se connecter à l’organisation Adobe Experience Cloud dans laquelle le projet que vous partagez a été créé. Toutefois, les utilisateurs avec lesquels vous partagez n’ont pas besoin d’avoir accès à Adobe Analytics.

     Les administrateurs d’Analytics peuvent configurer cette préférence pour l’entreprise, comme décrit dans la section [Préférences](/help/analyze/analysis-workspace/user-preferences.md). Selon la configuration de cette option par l’administrateur, vous pouvez rencontrer les scénarios suivants :

      * Si cette option n’est pas visible, votre administrateur Analytics n’a pas activé cette fonctionnalité.

      * Si cette option est activée et grisée, votre administrateur Analytics nécessite une authentification Experience Cloud pour toute personne accédant à des projets Analysis Workspace.

1. En regard de **[!UICONTROL Partager avec quiconque (aucune connexion requise)]** , cliquez sur le champ **Copier le lien** icon ![Icône Copier le lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Link_18_N.svg) pour copier le lien dans le presse-papiers du système.

1. Partagez le lien avec les personnes qui doivent avoir accès au projet. Vous pouvez par exemple coller le lien dans un email.

   Toute personne avec laquelle vous partagez le lien peut afficher le projet Analysis Workspace.

1. (Facultatif) Vous pouvez cliquer sur le bouton **Générer un nouveau lien** icon ![Icône Générer un lien](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) pour supprimer l’accès des utilisateurs qui ont reçu un lien vers le projet. Un nouveau lien est généré, que vous pouvez partager avec les utilisateurs auxquels vous souhaitez accéder.

1. Sélectionner **[!UICONTROL Fermer]** pour fermer la boîte de dialogue de partage. Vos modifications sont automatiquement enregistrées.

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
| Que se passe-t-il si un destinataire reçoit un rôle en tant qu’individu et un autre rôle en tant que membre d’un groupe ? | Si un destinataire reçoit plusieurs rôles, il obtient toujours l’expérience la plus élevée. Par exemple, si un destinataire reçoit le rôle **[!UICONTROL Peut modifier]** en tant qu’individu et le rôle **[!UICONTROL Peut afficher]** en tant que membre d’un groupe, il reçoit une expérience de projet **[!UICONTROL Peut modifier]**. |
| Quelle expérience obtient un destinataire s’il ouvre un lien de projet ? | Les destinataires reçoivent le rôle que vous leur avez attribué dans le modal de partage. Si un destinataire ne se voit pas attribuer un rôle et reçoit un lien vers le projet (**[!UICONTROL Partager]** > **[!UICONTROL Partage avec les utilisateurs de Workspace]**, puis sélectionnez **[!UICONTROL Copier]** en regard de **[!UICONTROL Partager par lien]** ), ils seront placés par défaut dans un rôle . Les personnes chargées de l’administration reçoivent **[!UICONTROL Peut modifier]** et les autres reçoivent **[!UICONTROL Peut dupliquer]**. |
