---
title: Rôles d’administrateur dans Adobe Analytics
description: Découvrez comment faire vos premiers pas avec Adobe Analytics, les types de rôles généraux et la connexion à l’interface utilisateur.
exl-id: fbbbd335-0d22-473e-adef-f92f8eab7bf0
feature: Admin Tools
source-git-commit: 88ed2f874d680f9ed1aea9bfb60e303f123cbc37
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 59%

---

# Rôles d’administrateur dans Adobe Analytics

Adobe Analytics prend en charge différents types d’administrateurs. Les administrateurs Adobe Analytics complets ont un accès complet à tous les éléments d’Adobe Analytics, tandis que d’autres administrateurs et utilisateurs peuvent effectuer des tâches plus spécialisées.

>[!NOTE]
>
>Pour qu’un utilisateur puisse se voir attribuer des rôles dans Adobe Analytics, il doit être désigné comme premier administrateur dans Experience Cloud. Le premier administrateur peut ensuite configurer les utilisateurs de l’organisation avec d’autres rôles clés.


## Rôles clés dans Experience Cloud et Adobe Analytics

Tenez compte des rôles clés suivants lors de l’utilisation d’Adobe Analytics :

* **Premier administrateur Experience Cloud :** Un premier administrateur est le point de départ pour permettre au reste de l’organisation d’utiliser chaque solution Experience Cloud. Une fois le contrat signé, une équipe de mise en service de Adobe se prépare à créer le compte. Le premier administrateur reçoit un courrier électronique contenant les informations de connexion avant la date d’entrée en vigueur du contrat. Il est vivement recommandé de s’assurer que les coordonnées du premier administrateur sont fournies à Adobe et sont exactes avant de signer le contrat.
* **Administrateurs Adobe Analytics complets :** Ces utilisateurs disposent d’un accès complet à tous les éléments d’Adobe Analytics, y compris les paramètres de la suite de rapports et les autorisations d’utilisateur. Selon la structure de votre entreprise, différentes personnes ou équipes peuvent être responsables de différentes facettes de l’administration d’Analytics. Par exemple, une personne est responsable de la désignation des variables à utiliser dans une implémentation. Une autre personne peut être chargée de permettre aux utilisateurs d’extraire correctement des rapports en s’assurant que chacun dispose des autorisations appropriées. Identifiez au moins un utilisateur qui peut assumer la responsabilité des paramètres de la suite de rapports Analytics et des autorisations d’utilisateur. Il peut y inviter d’autres administrateurs Analytics.
* **Administrateurs de collecte de données :** Ces utilisateurs disposent d’un accès complet à tous les éléments de la collecte de données Adobe Experience Platform, y compris les autorisations de publication, la création de conteneurs et les autorisations d’utilisateur. Ces utilisateurs ne sont pas nécessairement des programmeurs, mais une connaissance de base du code HTML, CSS et JavaScript est un plus. Il leur incombe de travailler avec les propriétaires de site web de votre entreprise pour que les balises soient implémentées sur votre site. Identifiez au moins un utilisateur responsable de l’implémentation de votre organisation et qui peut y inviter d’autres administrateurs de la collecte de données.
* **Administrateurs de profil de produit :** Ces utilisateurs peuvent ajouter ou supprimer des utilisateurs à un profil de produit, ajuster les éléments d’autorisation dans leur profil de produit et attribuer ou supprimer des profils de produit à des groupes d’utilisateurs. Les administrateurs de profil de produit n’ont pas un accès complet à Adobe Analytics. Toutefois, ils sont idéaux pour les chefs d’équipe ou les gestionnaires qui doivent accorder et gérer l’accès à Adobe Analytics pour leur équipe. Pour plus d’informations sur les profils de produit, voir [Profils de produit pour Adobe Analytics](/help/admin/admin-console/permissions/product-profile.md).
* **Délégués de l’assistance** : ils ne disposent pas de privilèges supplémentaires dans l’interface d’Analytics. Au lieu de cela, ils bénéficient de privilèges supplémentaires lorsqu’ils communiquent avec l’assistance clientèle d’Adobe. Généralement, ces utilisateurs sont également des administrateurs Analytics, car ils aident l’assistance clientèle à résoudre les problèmes rencontrés. Identifiez au moins un administrateur Analytics chargé de faciliter les interactions entre les utilisateurs finaux et l’assistance clientèle d’Adobe.
* **Propriétaires de site web :** ces personnes ou ces équipes sont responsables du codage et du développement de votre site web. Elles n’ont pas besoin de comptes, mais travailler avec les administrateurs de la collecte de données leur permettra d’obtenir le code des balises afin de l’implémenter sur votre site Web.
* **Utilisateurs finaux :** ces utilisateurs consultent généralement des rapports et recherchent des réponses aux questions opérationnelles. Les administrateurs Analytics accordent à ces utilisateurs l’autorisation de travailler au sein du produit.

## Octroi d’un accès administrateur de produit complet pour Analytics

Les administrateurs au niveau du système n’ont pas d’accès direct aux produits ; toutefois, ils peuvent se donner un accès en s’ajoutant en tant qu’administrateur au niveau du produit.

Pour permettre à Adobe Analytics d’accéder à vous-même ou à d’autres utilisateurs :

1. Connectez-vous à [Admin Console](https://adminconsole.adobe.com/) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’onglet **[!UICONTROL Produits]** dans la partie supérieure. Tous les produits achetés par votre entreprise se trouvent sur la gauche. Cliquez sur **[!UICONTROL Adobe Analytics]**, puis cliquez sur le bouton **[!UICONTROL Nouveau profil]** bouton .
1. Nommez ce profil &quot;Accès administrateur complet Analytics&quot;, puis cliquez sur **[!UICONTROL Suivant]** > **[!UICONTROL Enregistrer]**.
1. De retour sur la page Profils de produit, cliquez sur le profil récemment créé, puis sur l’onglet **[!UICONTROL Autorisations]**.
1. Cliquez sur l’un des éléments de la ligne d’autorisation. Si l’**[!UICONTROL inclusion automatique]** est disponible, activez-la. If **[!UICONTROL Inclusion automatique]** n’est pas disponible, cliquez sur **[!UICONTROL Tout ajouter]**. Les deux options déplacent tous les éléments d’autorisation vers la colonne de droite.
1. Cliquez sur **[!UICONTROL Enregistrer]**.
Répétez l’étape ci-dessus pour toutes les catégories d’autorisations.
1. Une fois toutes les catégories d’autorisations accordées au profil, revenez à la page Produits en cliquant sur **[!UICONTROL Produit]** en haut.
1. Sous la mosaïque Adobe Analytics, cliquez sur **[!UICONTROL Affecter des utilisateurs]**.
1. Entrez l’adresse e-mail à laquelle vous souhaitez accorder un accès Analytics complet et attribuez-lui le profil d’accès administrateur complet récemment créé. Cliquez sur **[!UICONTROL Enregistrer]**.

L’utilisateur dispose désormais d’un accès complet à Adobe Analytics.

## Accorder l’accès administrateur de produit à la collecte de données dans Experience Platform

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

## Octroi d’un accès administrateur de produit pour les profils de produit

Pour plus d’informations sur l’affectation d’utilisateurs en tant qu’administrateurs de profil de produit, reportez-vous à la section &quot;Gestion des administrateurs de profil de produit&quot; de l’article, [Gestion des profils de produit pour les utilisateurs d’entreprise](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) dans le guide d’utilisation Enterprise.

## Étapes suivantes

[Création d’une suite de rapports](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Demandez à votre administrateur Analytics de se connecter à l’outil et de créer une suite de rapports pour la collecte de données.

[Créer une propriété de balise Analytics](/help/implement/launch/create-analytics-property.md) : demandez à l’administrateur de la collecte de données de se connecter à l’outil et de créer une propriété à implémenter sur votre site.
