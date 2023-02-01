---
description: Partage de projets et rôles de projets dans Workspace
keywords: Partage de projets Analysis Workspace
title: Partage de projets
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
source-git-commit: 4b11a7057177bec9d2e9d7c435ad0d5476a46602
workflow-type: tm+mt
source-wordcount: '1631'
ht-degree: 34%

---

# Partage de projets

Vous pouvez partager un projet Analysis Workspace avec les types de personnes suivants :

* Utilisateurs et groupes de votre entreprise ayant accès à Adobe Analytics

* Utilisateurs et groupes de votre entreprise qui n’ont pas accès à Adobe Analytics

* Personnes en dehors de votre organisation

Quelconque [traitement](curate.md) votre demande avant le partage est prise en compte lorsque les destinataires ouvrent le projet.

Regardez cet aperçu vidéo sur le partage de projet :

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Partager avec les utilisateurs et les groupes Adobe Analytics de votre entreprise {#Add}

Vous pouvez partager un projet avec des utilisateurs ou des groupes Adobe Analytics existants de votre entreprise. Lorsque vous partagez un projet comme décrit dans cette section, les utilisateurs avec lesquels vous partagez un projet doivent déjà disposer d’un compte Adobe Analytics.

Vous pouvez partager un rôle spécifique avec des utilisateurs ou des groupes, ou partager un lien.

* [Partage d’un rôle de projet spécifique](#share-a-specific-project-role)

* [Partage d’un lien vers un projet](#share-a-link-to-a-project)

### Partage d’un rôle de projet spécifique

Lorsque vous partagez un rôle de projet spécifique avec des utilisateurs et des groupes de votre entreprise, tenez compte des points suivants :

* Rôles de projet (**[!UICONTROL Peut modifier]**, **[!UICONTROL Peut dupliquer]**, et **[!UICONTROL Peut afficher]**) sont liés à l’utilisateur et à un ID de projet spécifique. Les rôles de projet ne dépendent pas des autorisations d’utilisateurs gérées dans l’[Admin Console pour Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr).

* Dans Adobe Analytics, les groupes sont définis par profils de produits dans l’[Admin Console pour Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=fr). Les administrateurs peuvent partager des données avec n’importe quel groupe, y compris &quot;Tous&quot;. Les non-administrateurs peuvent partager avec n’importe quel groupe dont ils sont membres, à l’exception de &quot;Tous&quot;.

* Un utilisateur placé dans plusieurs rôles obtient toujours l’expérience la plus élevée. Cela peut se produire si un utilisateur est ajouté à la fois en tant qu’individu et dans le cadre d’un groupe. Par exemple, si un utilisateur reçoit la variable **[!UICONTROL Peut modifier]** rôle en tant qu’individu et **[!UICONTROL Peut afficher]** en tant que membre d’un groupe, ils recevront un **[!UICONTROL Peut modifier]** expérience du projet.

* Les administrateurs placés dans la variable **[!UICONTROL Peut dupliquer]** ou **[!UICONTROL Peut afficher]** reçoivent ces expériences limitées lorsqu’ils ouvrent un projet. Si vous le souhaitez, un administrateur peut augmenter son rôle pour obtenir le rôle **[!UICONTROL Peut modifier]** à tout moment via **[!UICONTROL Composants] > [!UICONTROL Projets]**.

Pour partager un rôle de projet spécifique avec des utilisateurs ou des groupes de votre entreprise :

1. Accédez au projet que vous souhaitez partager, puis cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Partager le projet]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
En cas de modifications non enregistrées, vous êtes d’abord invité à enregistrer votre projet.

   ![](assets/share-proj-modal.png)

   Pour plus d’informations sur le partage simultané de plusieurs projets, voir [Partage de projets dans le gestionnaire de projets](#share-projects-in-the-project-manager).

1. Ajoutez des destinataires ou des groupes de destinataires dans l’un des champs de rôle fournis :

   **Peut modifier :** Les destinataires peuvent **[!UICONTROL Enregistrer]** modifications apportées à un projet et à sa fonction de copropriétaires. Ce rôle est utile si vous souhaitez cogérer un projet avec d’autres collègues. Cela comprend la modification, la suppression et la modification des listes de destinataires pour un projet partagé. <br>Remarque : Analysis Workspace ne prend actuellement pas en charge la collaboration en direct. Il est donc recommandé qu’un seul utilisateur modifie un projet à la fois. Si les projets sont enregistrés en même temps, la dernière version est conservée.

   **Peut dupliquer :** Les destinataires peuvent **[!UICONTROL Enregistrer sous]** et ont accès au rail de gauche. Les interactions avec le projet ne sont pas limitées dans ce rôle. Ce rôle est utile si vous souhaitez partager un projet avec des utilisateurs qui comprennent les données de votre entreprise et comment utiliser Analysis Workspace, mais que vous ne souhaitez pas que votre projet soit modifié.

   **Peut afficher :** Les destinataires ne peuvent pas **[!UICONTROL Enregistrer]** ou **[!UICONTROL Enregistrer sous]** et n’ont pas accès au rail de gauche. Les interactions avec le projet sont également limitées. Ce rôle est utile si vous souhaitez partager un projet avec des utilisateurs qui connaissent moins bien la structure de données de votre entreprise, Analysis Workspace ou Adobe Analytics en général. Cependant, vous souhaitez tout de même qu’ils consomment des données et des informations dans un environnement sûr. En savoir plus sur l’[expérience du projet Peut afficher](/help/analyze/analysis-workspace/curate-share/view-only-projects.md).

1. Choisissez d’activer les options suivantes lors du partage du projet :

   * **Partage des composants de projet incorporés :** Partage des segments, des mesures calculées et des plages de dates avec tous les destinataires. Une fois partagés, ces composants apparaîtront dans le menu déroulant des composants du Workspace du destinataire. Ce paramètre n’est pas conservé. Il s’agit d’une action unique au moment du partage.

   * **Défini comme page d’entrée pour les destinataires :** Définit cette page comme page d’entrée pour les destinataires. Ce paramètre n’est pas conservé. Il s’agit d’une action unique au moment du partage.

1. Cliquez sur **[!UICONTROL Partager]**.
Vous pouvez également cliquer sur **[!UICONTROL Traiter et partager]** pour appliquer automatiquement le traitement du projet. Si un projet a déjà été partagé, ces boutons indiqueront **[!UICONTROL Mettre à jour]** et **[!UICONTROL Traiter et mettre à jour]**. En savoir plus sur le [traitement des projets](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=fr).

### Partage d’un lien vers un projet

Lorsque vous partagez un lien comme décrit dans cette section, tenez compte des points suivants :

* Les destinataires qui utilisent le lien doivent se connecter à Adobe Analytics avant d’accéder au projet.

* Si un destinataire ne se voit pas attribuer un rôle et reçoit une [link](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=fr) au projet (**[!UICONTROL Partager] > [!UICONTROL Obtenir le lien du projet]**), un rôle leur est attribué par défaut. Les administrateurs reçoivent **[!UICONTROL Peut modifier]** et les non-administrateurs reçoivent **[!UICONTROL Peut dupliquer]**.

Pour partager le lien du projet avec les utilisateurs de votre entreprise :

1. Cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Partager le projet]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
En cas de modifications non enregistrées, vous êtes d’abord invité à enregistrer votre projet.

   ![](assets/share-proj-modal.png)

1. Cliquez sur **[!UICONTROL Copier le lien]** en regard de **[!UICONTROL Champ de partage d’URL]**.

1. Partagez le lien avec les utilisateurs de votre entreprise. Vous pouvez par exemple le coller dans un email, sur un site web interne, etc.

## Partager un lien public avec quiconque (aucune connexion requise) {#share-public-link}

{{release-limited-testing-section}}

Vous pouvez partager des projets Analysis Workspace avec des personnes qui n’ont pas accès à Adobe Analytics. Cela peut inclure :

* Personnes en dehors de votre organisation

* Personnes de votre entreprise qui ne sont pas configurées avec Adobe Analytics

>[!NOTE]
>
>Cette option peut être désactivée par l’administrateur Analytics, comme décrit dans la section [Préférences](/help/analyze/analysis-workspace/user-preferences.md). Si vous ne pouvez pas partager un lien public comme décrit dans cette section, votre administrateur Analytics a désactivé cette fonctionnalité.

Pour partager un lien public vers un projet Analysis Workspace :

1. Ouvrez le projet Analysis Workspace que vous souhaitez partager.

1. Cliquez sur **[!UICONTROL Partager]** > **[!UICONTROL Partager le lien public]**.

   En cas de modifications non enregistrées, vous êtes invité à enregistrer votre projet.

   <!-- Add screen shot of new modal -->

1. Activez la variable **[!UICONTROL Principal du lien]** s’il n’est pas déjà activé.

1. Choisissez d’activer ou non les options de sécurité suivantes (ces options peuvent être contrôlées par votre administrateur Analytics) :

   * **[!UICONTROL Authentification SSO requise pour l’authentification unique]:**

      Exiger que les personnes disposant du lien s’authentifient via SSO avant d’accéder au projet partagé. Sélectionnez cette option si vous souhaitez que le projet soit accessible uniquement aux utilisateurs de votre entreprise.

      Les administrateurs d’Analytics peuvent définir cette préférence pour l’entreprise, comme décrit dans la section [Préférences](/help/analyze/analysis-workspace/user-preferences.md). Selon la configuration de cette option par l’administrateur, vous pouvez rencontrer les scénarios suivants :

      * Si cette option n’est pas visible, l’authentification unique n’est pas activée pour votre organisation ou votre administrateur Analytics n’a pas activé cette fonctionnalité.

      * Si cette option est activée et grisée, votre administrateur Analytics nécessite une authentification SSO pour accéder à tous les liens publics.
   * **[!UICONTROL Mot de passe requis]:** Exiger que les personnes disposant du lien spécifient un mot de passe avant d’accéder au projet Analysis Workspace. Vous bénéficiez ainsi d’un niveau de sécurité supplémentaire pour votre projet.

      Si vous sélectionnez cette option, indiquez un mot de passe. N’oubliez pas de partager ce mot de passe avec le lien du projet lorsque vous le partagez avec d’autres personnes. <!--go through this workflow and see how it works.-->

      Si cette option est activée et grisée, votre administrateur Analytics nécessite que tous les liens publics soient protégés par mot de passe. Les administrateurs d’Analytics peuvent définir cette préférence pour l’entreprise, comme décrit dans la section [Préférences](/help/analyze/analysis-workspace/user-preferences.md).


1. En regard de **[!UICONTROL Partager avec quiconque (aucune connexion requise)]** , cliquez sur le champ **Copier le lien** pour copier le lien dans le Presse-papiers du système.

1. Partagez le lien avec les personnes qui doivent avoir accès au projet. Vous pouvez par exemple coller le lien dans un email.

   Toute personne avec laquelle vous partagez le lien peut afficher le projet Analysis Workspace. Si vous choisissez d’exiger un mot de passe, vous devez également le partager avec toute personne souhaitant accéder au lien.

1. Sélectionner **[!UICONTROL Fermer]** pour fermer la boîte de dialogue de partage. Vos modifications sont automatiquement enregistrées. <!-- True? -->


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
