---
title: Rôles d’administrateur dans Adobe Analytics
description: Découvrez comment faire vos premiers pas avec Adobe Analytics, les types de rôles généraux et la connexion à l’interface utilisateur.
feature: Admin Tools
exl-id: 9d10716f-5b66-42dc-b288-af34da203c35
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 96%

---

# Rôles d’administrateur dans Adobe Analytics

Adobe Analytics prend en charge différents types d’administrateurs. Les administrateurs Adobe Analytics complets ont accès à toutes les fonctionnalités d’Adobe Analytics, tandis que les autres administrateurs et utilisateurs peuvent effectuer des tâches plus spécialisées.

>[!NOTE]
>
>Pour qu’un utilisateur puisse se voir attribuer des rôles dans Adobe Analytics, il doit être désigné comme premier administrateur dans Experience Cloud. Le premier administrateur peut ensuite configurer les utilisateurs alloués de l’organisation avec d’autres rôles clés, comme décrit dans cet article. Pour plus d’informations sur le premier administrateur, consultez le [Guide Adobe Analytics pour le premier administrateur](/help/admin/admin-console/first-admin-guide.md).


## Rôles clés dans Experience Cloud et Adobe Analytics

Tenez compte des rôles clés suivants lors de l’utilisation d’Adobe Analytics :

* **Administrateurs Adobe Analytics complets :** ces utilisateurs disposent d’un accès complet à toutes les fonctionnalités d’Adobe Analytics, y compris les paramètres de la suite de rapports et les autorisations utilisateur. Selon la structure de votre entreprise, différentes personnes ou équipes peuvent être responsables de différentes facettes de l’administration d’Analytics. Par exemple, une personne est responsable de la désignation des variables à utiliser dans une implémentation. Une autre personne peut être chargée de permettre aux utilisateurs d’extraire correctement des rapports en s’assurant que chacun dispose des autorisations appropriées. Identifiez au moins un utilisateur qui peut assumer la responsabilité des paramètres de la suite de rapports Analytics et des autorisations d’utilisateur. Il peut y inviter d’autres administrateurs Analytics.
* **Administrateurs de collecte de données :** ces utilisateurs disposent d’un accès complet à toutes les fonctionnalités de la collecte de données Adobe Experience Platform, y compris les autorisations de publication, la création de conteneurs et les autorisations utilisateur. Ces utilisateurs ne sont pas nécessairement des programmeurs, mais une connaissance de base du code HTML, CSS et JavaScript est un plus. Il leur incombe de travailler avec les propriétaires du site Web de votre organisation pour que les balises soient implémentées sur votre site. Identifiez au moins un utilisateur responsable de l’implémentation de votre organisation et qui peut y inviter d’autres administrateurs de la collecte de données.
* **Administrateur de produit :** un administrateur de produit gère un produit dans Admin Console, ainsi que les droits des utilisateurs sur ce produit.
* **Administrateurs de profil de produit :** ces utilisateurs peuvent ajouter des utilisateurs à un profil de produit ou en supprimer, ajuster les éléments d’autorisation dans leur profil de produit et affecter des profils de produit à des groupes d’utilisateurs ou en supprimer. Les administrateurs de profil de produit ne disposent pas d’un accès complet à Adobe Analytics. Toutefois, ils sont parfaits pour les chefs dʼéquipe ou les gestionnaires qui doivent octroyer et gérer lʼaccès à Adobe Analytics pour leur équipe. Pour plus d’informations sur les profils de produit, consultez [Profils de produit pour Adobe Analytics](/help/admin/admin-console/permissions/product-profile.md).
* **Administrateur d’assistance** : également appelés utilisateurs pris en charge, ils ne disposent d’aucun privilège supplémentaire dans l’interface Analytics. Au lieu de cela, ils bénéficient de privilèges supplémentaires lorsqu’ils communiquent avec l’assistance clientèle d’Adobe. Généralement, ces utilisateurs sont également des administrateurs Analytics, car ils aident l’assistance clientèle à résoudre les problèmes rencontrés. Identifiez au moins un administrateur Analytics chargé de faciliter les interactions entre les utilisateurs finaux et l’assistance clientèle d’Adobe.
* **Propriétaires de site web :** ces personnes ou ces équipes sont responsables du codage et du développement de votre site web. Elles n’ont pas besoin de comptes, mais travailler avec les administrateurs de la collecte de données leur permettra d’obtenir le code des balises afin de l’implémenter sur votre site Web.
* **Utilisateurs finaux :** ces utilisateurs consultent généralement des rapports et recherchent des réponses aux questions opérationnelles. Les administrateurs Analytics accordent à ces utilisateurs l’autorisation de travailler au sein du produit.

## Octroyer un accès administrateur de produit complet pour Analytics

Les administrateurs au niveau du système n’ont pas d’accès direct aux produits, mais ils peuvent s’y accorder un accès en s’ajoutant en tant qu’administrateurs au niveau du produit.

S’accorder ou accorder à d’autres personnes l’accès à Adobe Analytics :

1. Connectez-vous à [Admin Console](https://adminconsole.adobe.com/) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’onglet **[!UICONTROL Produits]** dans la partie supérieure. Tous les produits achetés par votre entreprise se trouvent sur la gauche. Cliquez sur **[!UICONTROL Adobe Analytics]**, puis sur le bouton **[!UICONTROL Nouveau profil]**.
1. Nommez ce profil « Accès administrateur complet Analytics », puis cliquez sur **[!UICONTROL Suivant]** > **[!UICONTROL Enregistrer]**.
1. De retour sur la page Profils de produit, cliquez sur le profil récemment créé, puis sur l’onglet **[!UICONTROL Autorisations]**.
1. Cliquez sur l’un des éléments de la ligne d’autorisation. Si l’**[!UICONTROL inclusion automatique]** est disponible, activez-la. Si l’**[!UICONTROL inclusion automatique]** n’est pas disponible, cliquez sur **[!UICONTROL Ajouter tout]**. Les deux options déplacent tous les éléments d’autorisation vers la colonne de droite.
1. Cliquez sur **[!UICONTROL Enregistrer]**.
Répétez l’étape ci-dessus pour toutes les catégories d’autorisations.
1. Une fois que toutes les catégories d’autorisations ont été accordées au profil, revenez à la page Produits en cliquant sur **[!UICONTROL Produit]** dans la partie supérieure.
1. Sous le volet Adobe Analytics, cliquez sur **[!UICONTROL Attribuer des utilisateurs]**.
1. Entrez l’adresse e-mail à laquelle vous souhaitez accorder un accès Analytics complet et attribuez-lui le profil d’accès administrateur complet récemment créé. Cliquez sur **[!UICONTROL Enregistrer]**.

L’utilisateur dispose désormais d’un accès complet à Adobe Analytics.

## Octroyer un accès administrateur de produit pour la collecte de données dans Experience Platform

L’accès administrateur de produit pour la collecte de données dans Experience Platform est presque identique à l’octroi d’un accès administrateur de produit pour Analytics.

1. Connectez-vous à [Adobe Admin Console](https://adminconsole.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’onglet **[!UICONTROL Produits]** dans la partie supérieure. Tous les produits achetés par votre entreprise se trouvent sur la gauche. Cliquez sur **[!UICONTROL Experience Platform Launch]**, puis sur **[!UICONTROL Nouveau profil]**.
1. Nommez ce profil « Accès administrateur complet à la collecte de données », puis cliquez sur **[!UICONTROL Terminé]**.
1. De retour sur la page **[!UICONTROL Profils de produit]**, cliquez sur le profil récemment créé, puis sur l’onglet **[!UICONTROL Autorisations]**.
1. Cliquez sur l’un des éléments de la ligne d’autorisation. Si l’**[!UICONTROL inclusion automatique]** est disponible, activez-la. Si l’inclusion automatique n’est pas disponible, cliquez sur **[!UICONTROL Ajouter tout]**. Les deux options déplacent tous les éléments d’autorisation vers la colonne de droite.
1. Cliquez sur **[!UICONTROL Enregistrer]**. Répétez l’étape ci-dessus pour toutes les catégories d’autorisations.
1. Une fois que toutes les catégories d’autorisations ont été acordées au profil, revenez à la page Aperçu en cliquant sur **[!UICONTROL Aperçu]** dans la partie supérieure.
1. Sous le volet [!UICONTROL Experience Platform Launch], cliquez sur **[!UICONTROL Attribuer des utilisateurs]**.
1. Entrez l’adresse e-mail à laquelle vous souhaitez accorder un accès Analytics complet et attribuez-lui le profil d’accès administrateur complet récemment créé. Cliquez sur **[!UICONTROL Enregistrer]**.
1. L’utilisateur dispose désormais d’un accès complet à la collecte de données Experience Platform.

## Octroyer un accès administrateur de produit pour les profils de produit

Pour plus d’informations sur l’affectation d’utilisateurs en tant qu’administrateurs de profil de produit, consultez la section « Gérer les administrateurs de profil de produit » de l’article [Gérer les profils de produit pour les utilisateurs d’entreprise](https://helpx.adobe.com/fr/enterprise/using/manage-product-profiles.html) dans le guide d’utilisation Enterprise.

## Étapes suivantes

[Créer une suite de rapports](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md) : demandez à votre administrateur Analytics de se connecter à l’outil et de créer une suite de rapports pour la collecte de données.

[Créer une propriété de balise Analytics](/help/implement/launch/create-analytics-property.md) : demandez à l’administrateur de la collecte de données de se connecter à l’outil et de créer une propriété à implémenter sur votre site.

Pour qu’un utilisateur puisse se voir attribuer des rôles dans Adobe Analytics, il doit être désigné comme premier administrateur dans Experience Cloud. Le premier administrateur peut ensuite configurer les utilisateurs alloués de l’organisation avec d’autres rôles clés, comme décrit dans cet article.

Un premier administrateur est le point de départ pour permettre au reste de l’organisation d’utiliser chaque solution Experience Cloud.

Une fois le contrat signé

1. L’équipe d’attribution des privilèges d’accès d’Adobe se prépare à créer le compte.

1. La première personne en charge de l’administration reçoit un e-mail contenant les informations de connexion avant la date de début du contrat.

>[!IMPORTANT]
>
>   Il est vivement recommandé de s’assurer que les coordonnées du premier administrateur sont fournies à Adobe et sont exactes avant de signer le contrat.
