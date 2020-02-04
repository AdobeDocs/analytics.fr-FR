---
title: Guide Adobe Analytics pour le premier administrateur
description: Découvrez comment faire vos premiers pas avec Adobe Analytics, les types de rôles généraux et la connexion à l’interface utilisateur.
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Guide Adobe Analytics pour le premier administrateur

Un premier administrateur est le point de départ pour permettre au reste de l’organisation d’utiliser chaque solution Experience Cloud. Une fois le contrat signé, une équipe de mise en service d’Adobe se prépare à créer le compte. Le premier administrateur reçoit un courrier électronique contenant les informations de connexion avant la date d’entrée en vigueur du contrat. Il est vivement recommandé de s’assurer que les coordonnées du premier administrateur sont fournies à Adobe et sont exactes avant de signer le contrat.

## Rôles clés dans l’utilisation d’Experience Cloud

Si votre entreprise a acheté Adobe Analytics, vous devez tenir compte de plusieurs rôles clés :

- **Administrateurs Adobe Analytics :** ces utilisateurs disposent d’un accès complet à tous les éléments d’Adobe Analytics, y compris les paramètres de la suite de rapports et les autorisations d’utilisateur. Selon la structure de votre entreprise, différentes personnes ou équipes peuvent être responsables de différentes facettes de l’administration d’Analytics. Par exemple, une personne est responsable de la désignation des variables à utiliser dans une implémentation. Une autre personne peut être chargée de permettre aux utilisateurs d’extraire correctement des rapports en s’assurant que chacun dispose des autorisations appropriées. Identifiez au moins un utilisateur qui peut assumer la responsabilité des paramètres de la suite de rapports Analytics et des autorisations d’utilisateur. Il peut y inviter d’autres administrateurs Analytics.
- **Administrateurs Adobe Experience Platform Launch :** ces utilisateurs disposent d’un accès complet à tout ce que contient Experience Platform Launch, y compris les autorisations de publication, la création de conteneurs et les autorisations d’utilisateur. Ces utilisateurs ne sont pas nécessairement des programmeurs, mais une connaissance de base du code HTML, CSS et JavaScript est un plus. Il leur incombe de travailler avec les propriétaires de site web de votre entreprise pour que le code Experience Platform Launch soit implémenté sur votre site. Identifiez au moins un utilisateur qui peut être responsable de l’implémentation de votre entreprise et qui peut y inviter d’autres administrateurs Experience Platform Launch.
- **Propriétaires de site web :** ces personnes ou ces équipes sont responsables du codage et du développement de votre site web. Elles n’ont pas besoin de comptes, mais elles souhaitent travailler avec les administrateurs Experience Platform Launch pour obtenir le code Experience Platform Launch et l’implémenter sur votre site web.
- **Utilisateurs finaux :** ces utilisateurs consultent généralement des rapports et recherchent des réponses aux questions opérationnelles. Les administrateurs Analytics accordent à ces utilisateurs l’autorisation de travailler au sein du produit.

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

## Octroi d’un accès administrateur de produit pour Experience Platform Launch

L’accès administrateur de produit pour Experience Platform Launch est presque identique à l’octroi de l’accès administrateur de produit pour Analytics.

1. Connectez-vous à Admin Console à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’onglet Produits sur la partie supérieure. Tous les produits achetés par votre entreprise se trouvent sur la gauche. Cliquez sur Experience Platform Launch par Adobe, puis sur le bouton Nouveau profil.
1. Nommez ce profil « Accès administrateur complet Experience Platform Launch », puis cliquez sur Terminé.
1. De retour sur la page Profils du produit, cliquez sur le profil récemment créé, puis sur l’onglet Autorisations.
1. Cliquez sur l’un des éléments de la ligne d’autorisation. Si l’inclusion automatique est disponible, activez-la. Si l’inclusion automatique n’est pas disponible, cliquez sur Ajouter tout. Les deux options déplacent tous les éléments d’autorisation vers la colonne de droite.
1. Cliquez sur Enregistrer. Répétez l’étape ci-dessus pour toutes les catégories d’autorisations.
1. Une fois que toutes les catégories d’autorisations ont été accordées au profil, revenez à la page Aperçu en cliquant sur Aperçu sur la partie supérieure.
1. Sous le volet Experience Platform Launch par Adobe, cliquez sur Affecter des utilisateurs.
1. Entrez l’adresse électronique à laquelle vous souhaitez accorder un accès Analytics complet et attribuez-lui le profil d’accès administrateur complet récemment créé. Cliquez sur Enregistrer.
1. L’utilisateur dispose désormais d’un accès complet à Experience Platform Launch.

## Étapes suivantes

[Créer une suite de rapports](create-report-suite.md) : demandez à votre administrateur Analytics de se connecter à l’outil et de créer une suite de rapports pour la collecte de données.

[Créer une propriété dans Experience Platform Launch](/help/implement/launch/create-analytics-property.md) : demandez à votre administrateur Experience Platform Launch de se connecter à l’outil et de créer une propriété à implémenter sur votre site.
