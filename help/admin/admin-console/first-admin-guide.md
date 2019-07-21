---
title: Guide d'administration d'Adobe Analytics First Admin
seo-title: Guide d'administration d'Adobe Analytics First Admin
description: Découvrez comment commencer avec Adobe Analytics, les types de rôles généraux et la connexion à l'interface utilisateur.
seo-description: Découvrez comment commencer avec Adobe Analytics, les types de rôles généraux et la connexion à l'interface utilisateur.
translation-type: tm+mt
source-git-commit: 800d4ed34a816bd331b339295dc3acd2a03a2cd5

---


# Guide d'administration d'Adobe Analytics First Admin

Un premier administrateur est le point de départ d'autoriser le reste de l'organisation à utiliser chaque solution Experience Cloud. Une fois le contrat signé, une équipe d'attribution des privilèges d'accès chez Adobe prépare la création du compte. Le premier administrateur reçoit un courrier électronique contenant les informations de connexion avant la date de début du contrat. Il est fortement recommandé de s'assurer que les informations de contact du premier administrateur sont transmises à Adobe et précise avant la signature du contrat.

## Rôles clés dans l'utilisation d'Experience Cloud

Si votre entreprise a acheté Adobe Analytics, il existe plusieurs rôles clés à prendre en compte :

- **Administrateurs d'Adobe Analytics :** Ces utilisateurs ont accès à tout ce qui se trouve dans Adobe Analytics, y compris les paramètres de suite de rapports et les permissions utilisateur. Selon la structure de votre organisation, différentes personnes ou équipes peuvent être responsables de différentes facettes de l'administration d'Analytics. Par exemple, une personne est responsable de la désignation des variables à utiliser dans une implémentation. Une autre personne peut être responsable de l'extraction correcte des rapports par les utilisateurs en s'assurant que tous les utilisateurs disposent des autorisations appropriées. Identifiez au moins un utilisateur qui peut être responsable des paramètres de la suite de rapports Analytics et des autorisations utilisateur, et il peut inviter d'autres administrateurs Analytics à y accéder.
- **Administrateurs de lancement de plateforme Adobe Experience Platform :** Ces utilisateurs ont accès à tout ce qui se trouve dans le lancement de plateforme Experience Platform, y compris les autorisations de publication, la création de conteneurs et les permissions utilisateur. Ces utilisateurs ne sont pas nécessairement des programmeurs, mais ils possèdent au moins une connaissance du code HTML, CSS et JavaScript. Ils sont chargés de travailler avec les propriétaires de sites Web de votre organisation pour obtenir le code de lancement de la plate-forme Experience Platform sur votre site. Identifiez au moins un utilisateur qui peut être responsable de l'implémentation de votre organisation et qui peut inviter d'autres administrateurs de lancement de plateforme Experience à partir de là.
- **Propriétaires du site Web :** Ces personnes ou équipes sont responsables du codage et du développement de votre site Web. Ils n'ont pas besoin de comptes, mais veulent travailler avec les administrateurs de lancement de plateforme Experience pour obtenir le code de lancement de la plateforme Experience et le mettre en œuvre sur votre site Web.
- **Fin - utilisateurs :** ces utilisateurs affichent généralement des rapports et recherchent des réponses aux questions professionnelles. Les administrateurs d'Analytics octroient aux utilisateurs ces permissions pour travailler dans le produit.

En tant qu'administrateur, votre rôle peut se chevaucher dans un ou plusieurs de ces rôles. Tant que chacune de ces responsabilités de base est couverte, vous pouvez octroyer des autorisations pour en obtenir d'autres dans votre organisation.

## Octroi d'un accès administrateur pour les produits Analytics

Les administrateurs au niveau du système n'ont pas accès directement aux produits, mais ils peuvent lui donner accès en s'ajoutant en tant qu'administrateur au niveau du produit. Pour vous donner accès à Adobe Analytics ou d'autres personnes, procédez comme suit.

1. Log in to the [Admin Console](https://adminconsole.adobe.com/) with your Adobe ID credentials.
1. Cliquez sur l'onglet Produits en haut. Tous les produits achetés par votre organisation se trouvent à gauche. Cliquez sur Adobe Analytics, puis sur le bouton Nouveau profil.
1. Donnez un nom à ce profil « Accès admin complet à Analytics », puis cliquez sur Terminé.
1. Revenez sur la page Profils du produit, cliquez sur le nouveau profil, puis sur l'onglet Autorisations.
1. Cliquez sur l'une des lignes d'autorisation. Si l'option Inclusion automatique est disponible, activez-la. Si l'inclusion automatique n'est pas disponible, cliquez sur Ajouter tout. Les deux options déplacent tous les éléments d'autorisation vers la colonne de droite.
1. Cliquez sur Enregistrer. Répétez l'étape ci-dessus pour toutes les catégories d'autorisations.
1. Une fois toutes les catégories d'autorisations accordées au profil, revenez à la page Aperçu en cliquant sur Aperçu en haut.
1. Sous le volet Adobe Analytics, cliquez sur « Affecter des utilisateurs ».
1. Saisissez l'adresse électronique à laquelle vous souhaitez accorder un accès Analytics complet et affectez-lui le profil d'accès admin qui vient d'être créé. Cliquez sur Enregistrer.
1. L'utilisateur dispose désormais d'un accès complet à Adobe Analytics.

## Octroi d'un accès d'administrateur du produit pour le lancement de Platform Platform

L'accès administrateur des produits pour le lancement de la plateforme Experience est pratiquement identique à l'octroi d'un accès administrateur pour les produits Analytics.

1. Connectez-vous à la console d'administration avec vos informations d'identification Adobe ID.
1. Cliquez sur l'onglet Produits en haut. Tous les produits achetés par votre organisation se trouvent à gauche. Cliquez sur Lancer la plateforme d'expérience par Adobe, puis sur le bouton Nouveau profil.
1. Donnez un nom à ce profil « Launch Platform Launch Full admin access », puis cliquez sur Done.
1. Revenez sur la page Profils du produit, cliquez sur le nouveau profil, puis sur l'onglet Autorisations.
1. Cliquez sur l'une des lignes d'autorisation. Si l'option Inclusion automatique est disponible, activez-la. Si l'inclusion automatique n'est pas disponible, cliquez sur Ajouter tout. Les deux options déplacent tous les éléments d'autorisation vers la colonne de droite.
1. Cliquez sur Enregistrer. Répétez l'étape ci-dessus pour toutes les catégories d'autorisations.
1. Une fois toutes les catégories d'autorisations accordées au profil, revenez à la page Aperçu en cliquant sur Aperçu en haut.
1. Sous le volet Lancement de plateforme d'expérience par Adobe, cliquez sur Affecter les utilisateurs.
1. Saisissez l'adresse électronique à laquelle vous souhaitez accorder un accès Analytics complet et affectez-lui le profil d'accès admin qui vient d'être créé. Cliquez sur Enregistrer.
1. L'utilisateur dispose maintenant d'un accès complet au lancement de Platform Platform.

## Étapes suivantes

[Création d'une suite de rapports](create-report-suite.md): Demandez à votre administrateur Analytics de se connecter à l'outil et de créer une suite de rapports pour la collecte de données

[Création d'une propriété dans Launch Platform Launch](../../implement/implement-with-launch/create-analytics-property.md): Demander à votre administrateur de lancer la plate-forme Experience Platform de se connecter à l'outil et de créer une propriété à implémenter sur votre site
