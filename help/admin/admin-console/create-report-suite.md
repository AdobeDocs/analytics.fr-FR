---
title: Création d’une suite de rapports
seo-title: Création d'une suite de rapports dans Adobe Analytics
description: Créez un conteneur de base pour la collecte de données dans Adobe Analytics.
seo-description: Créez un conteneur de base pour la collecte de données dans Adobe Analytics.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Création d’une suite de rapports

Une suite de rapports est un silo de données qu'Adobe Analytics utilise pour extraire des rapports. Une organisation peut avoir de nombreuses suites de rapports, chacune contenant des ensembles de données différents. Bien que les suites de rapports distinctes soient importantes auparavant, l'utilisation d'une suite de rapports unique devient plus avantageuse. L'introduction aux suites de rapports virtuelles et au traitement du temps de rapport permet à l'utilisateur de créer ses propres sous-ensembles de données, ce qui permet d'obtenir des données globales et spécifiques au site.

Cet article est conçu pour les administrateurs ou administrateurs d'analyses au niveau système pour préparer la collecte de données.

## Conditions préalables

[Guide d'administration d'Adobe Analytics pour la première fois](first-admin-guide.md): Assurez-vous qu'un administrateur de niveau système vous a accordé l'accès à Adobe Analytics via la console d'administration Experience Cloud.

## Création d’une suite de rapports

> [!NOTE]Remarque : Il existe également un moyen de créer une suite de rapports dans Adobe Analytics à l'aide de l'ancien administrateur. Adobe recommande d'utiliser l'assistant de configuration de la suite de rapports décrit ici.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Cliquez sur l'icône 9 carrée dans l'angle supérieur droit, puis cliquez sur le logo Analytics coloré.
1. Une fenêtre modale Bienvenue dans Adobe Analytics doit s'afficher automatiquement. Dans le cas contraire, cliquez sur l'icône d'aide dans l'angle supérieur droit, puis sélectionnez Bienvenue dans Adobe Analytics.
1. Dans la fenêtre modale, cliquez sur Démarrer la configuration.
1. Suivez chaque invite qui décrit les concepts de base tels que le type de propriété, les secteurs et le fuseau horaire. Cliquez sur Suivant.
1. La suite de rapports est maintenant créée. Adobe recommande également d'utiliser une suite de rapports de développement. De ce fait, le test ne recueille pas les données des clients. Cliquez sur l'icône d'aide dans l'angle supérieur droit, puis sélectionnez de nouveau Bienvenue dans Adobe Analytics.
1. Dans la fenêtre modale, cliquez sur Démarrer Configuration.
Attribuez un nom à cette suite de rapports, à l'exception de « -dev » à la fin. Cette suite de rapports recevant uniquement le trafic interne, la taille estimée peut être la plus petite.
1. Cliquez sur Suivant pour terminer la création de votre suite de rapports de développement.

## Résolution des problèmes

**Une fois connecté à Experience Cloud, l'icône Analytics est grisée.**

Cela signifie que votre compte n'a pas reçu les autorisations correctes pour Analytics. Travaillez avec un administrateur au niveau du système de votre organisation pour vous assurer que vous appartenez à un profil avec des autorisations suffisantes pour accéder à Adobe Analytics.

**Une fois connecté à Adobe Analytics, la fenêtre contextuelle Bienvenue dans Adobe Analytics est absente.**

Vérifiez que vous êtes connecté via Experience Cloud et non via my. omniture. com. L'utilisateur qui se connecte via my.omniture.com n'est pas doté de l'assistant de configuration de la suite de rapports.

## Étapes suivantes

[Créez et configurez une propriété pour Adobe Analytics au lancement](../../implement/implement-with-launch/create-analytics-property.md): Création d'une zone de gestion de votre mise en œuvre Analytics
