---
title: Guide Adobe Analytics pour le premier administrateur
description: Découvrez comment faire vos premiers pas avec Adobe Analytics, les types de rôles généraux et la connexion à l’interface utilisateur.
exl-id: fbbbd335-0d22-473e-adef-f92f8eab7bf0
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 72%

---

# Guide Adobe Analytics pour le premier administrateur

Un premier administrateur est le point de départ pour permettre au reste de l’organisation d’utiliser chaque solution Experience Cloud. Une fois le contrat signé, une équipe de mise en service d’Adobe se prépare à créer le compte. Le premier administrateur reçoit un courrier électronique contenant les informations de connexion avant la date d’entrée en vigueur du contrat. Il est vivement recommandé de s’assurer que les coordonnées du premier administrateur sont fournies à Adobe et sont exactes avant de signer le contrat.

## Rôles clés dans l’utilisation d’Experience Cloud

Si votre entreprise a acheté Adobe Analytics, vous devez tenir compte de plusieurs rôles clés :

* **Administrateurs Adobe Analytics :** ces utilisateurs disposent d’un accès complet à tous les éléments d’Adobe Analytics, y compris les paramètres de la suite de rapports et les autorisations d’utilisateur. Selon la structure de votre entreprise, différentes personnes ou équipes peuvent être responsables de différentes facettes de l’administration d’Analytics. Par exemple, une personne est responsable de la désignation des variables à utiliser dans une implémentation. Une autre personne peut être chargée de permettre aux utilisateurs d’extraire correctement des rapports en s’assurant que chacun dispose des autorisations appropriées. Identifiez au moins un utilisateur qui peut assumer la responsabilité des paramètres de la suite de rapports Analytics et des autorisations d’utilisateur. Il peut y inviter d’autres administrateurs Analytics.
* **Administrateurs de collecte de données :**  ces utilisateurs disposent d’un accès complet à tous les éléments de l’interface utilisateur de collecte de données (anciennement l’interface utilisateur Experience Platform Launch), y compris les autorisations de publication, la création de conteneurs et les autorisations d’utilisateur. Ces utilisateurs ne sont pas nécessairement des programmeurs, mais une connaissance de base du code HTML, CSS et JavaScript est un plus. Il leur incombe de travailler avec les propriétaires du site web de votre entreprise pour que les balises Experience Platform soient implémentées sur votre site. Identifiez au moins un utilisateur responsable de la mise en oeuvre de votre entreprise et qui peut y inviter d’autres administrateurs de collecte de données.
* **Délégués de l’assistance** : ils ne disposent pas de privilèges supplémentaires dans l’interface d’Analytics. Au lieu de cela, ils bénéficient de privilèges supplémentaires lorsqu’ils communiquent avec l’assistance clientèle d’Adobe. Généralement, ces utilisateurs sont également des administrateurs Analytics, car ils aident l’assistance clientèle à résoudre les problèmes rencontrés. Identifiez au moins un administrateur Analytics chargé de faciliter les interactions entre les utilisateurs finaux et l’assistance clientèle d’Adobe.
* **Propriétaires de site web :** ces personnes ou ces équipes sont responsables du codage et du développement de votre site web. Ils ne nécessitent pas de comptes, mais ils souhaitent travailler avec les administrateurs de collecte de données pour obtenir le code de balise et l’implémenter sur votre site web.
* **Utilisateurs finaux :** ces utilisateurs consultent généralement des rapports et recherchent des réponses aux questions opérationnelles. Les administrateurs Analytics accordent à ces utilisateurs l’autorisation de travailler au sein du produit.

En tant que premier administrateur, votre rôle peut se chevaucher dans un ou plusieurs de ces rôles. Tant que chacune de ces responsabilités de base sont assumées, vous pouvez accorder des autorisations afin que d’autres membres de votre organisation soient opérationnels.

## Octroi d’un accès d’administrateur de produit pour Analytics

Les administrateurs au niveau du système n’ont pas d’accès direct aux produits, mais ils peuvent s’y accorder un accès en s’ajoutant en tant qu’administrateurs au niveau du produit. Si vous souhaitez accorder l’accès à Adobe Analytics à d’autres utilisateurs ou à vous-même, procédez comme suit.

1. Connectez-vous à [Admin Console](https://adminconsole.adobe.com/) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’onglet Produits sur la partie supérieure. Tous les produits achetés par votre entreprise se trouvent sur la gauche. Cliquez sur Adobe Analytics, puis sur le bouton Nouveau profil.
1. Nommez ce profil « Accès administrateur complet Analytics », puis cliquez sur Terminé.
1. De retour sur la page Profils du produit, cliquez sur le profil récemment créé, puis sur l’onglet Autorisations.
1. Cliquez sur l’un des éléments de la ligne d’autorisation. Si l’inclusion automatique est disponible, activez-la. Si l’inclusion automatique n’est pas disponible, cliquez sur Ajouter tout. Les deux options déplacent tous les éléments d’autorisation vers la colonne de droite.
1. Cliquez sur Enregistrer. Répétez l’étape ci-dessus pour toutes les catégories d’autorisations.
1. Une fois que toutes les catégories d’autorisations ont été accordées au profil, revenez à la page Aperçu en cliquant sur Aperçu sur la partie supérieure.
1. Sous le volet Adobe Analytics, cliquez sur Attribuer des utilisateurs.
1. Entrez l’adresse électronique à laquelle vous souhaitez accorder un accès Analytics complet et attribuez-lui le profil d’accès administrateur complet récemment créé. Cliquez sur Enregistrer.
1. L’utilisateur dispose désormais d’un accès complet à Adobe Analytics.

## Octroi d’un accès administrateur de produit pour la collecte de données dans Experience Platform

L’accès administrateur de produit à la collecte de données dans Experience Platform est presque identique à l’octroi de l’accès administrateur de produit à Analytics.

1. Connectez-vous à [Adobe Admin Console](https://adminconsole.adobe.com) à l’aide de vos informations d’identification Adobe ID.
1. Cliquez sur l’onglet **[!UICONTROL Produits]** en haut. Tous les produits achetés par votre entreprise se trouvent sur la gauche. Cliquez sur **[!UICONTROL Experience Platform Launch]**, puis sur **[!UICONTROL Nouveau profil]**.
1. Nommez ce profil &quot;Accès administrateur complet à la collecte de données&quot;, puis cliquez sur **[!UICONTROL Terminé]**.
1. De retour sur la page **[!UICONTROL Profils produit]** , cliquez sur le profil nouvellement créé, puis sur l’onglet **[!UICONTROL Autorisations]** .
1. Cliquez sur l’un des éléments de la ligne d’autorisation. Si **[!UICONTROL Auto-include]** est disponible, activez-le. Si l’inclusion automatique n’est pas disponible, cliquez sur **[!UICONTROL Ajouter tout]**. Les deux options déplacent tous les éléments d’autorisation vers la colonne de droite.
1. Cliquez sur **[!UICONTROL Enregistrer]**. Répétez l’étape ci-dessus pour toutes les catégories d’autorisations.
1. Une fois toutes les catégories d’autorisations accordées au profil, revenez à la page Aperçu en cliquant sur **[!UICONTROL Aperçu]** en haut de la page.
1. Sous la mosaïque [!UICONTROL Experience Platform Launch], cliquez sur **[!UICONTROL Attribuer des utilisateurs]**.
1. Entrez l’adresse électronique à laquelle vous souhaitez accorder un accès Analytics complet et attribuez-lui le profil d’accès administrateur complet récemment créé. Cliquez sur **[!UICONTROL Enregistrer]**.
1. L’utilisateur dispose désormais d’un accès complet à la collecte de données Experience Platform.

## Étapes suivantes

[Créer une suite de rapports](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) : demandez à votre administrateur Analytics de se connecter à l’outil et de créer une suite de rapports pour la collecte de données.

[Créez une propriété](/help/implement/launch/create-analytics-property.md) de balise Analytics : Demandez à l’administrateur de la collecte de données de se connecter à l’outil et de créer une propriété à implémenter sur votre site.
