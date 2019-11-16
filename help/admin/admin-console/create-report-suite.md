---
title: Création d’une suite de rapports
description: Créez un conteneur de base pour la collecte de données dans Adobe Analytics.
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# Création d’une suite de rapports

Une suite de rapports est un ensemble de données utilisé par Adobe Analytics pour extraire des rapports. Une organisation peut avoir plusieurs suites de rapports, chacune contenant différents jeux de données. Bien que des suites de rapports distinctes aient été importantes par le passé, le fait d’avoir une seule suite de rapports est devenu plus avantageux. L’introduction aux suites de rapports virtuelles et au traitement du temps des rapports permet à un utilisateur de créer ses propres sous-ensembles de données, ce qui lui permet d’obtenir des données globales et spécifiques au site.

Cet article est destiné aux administrateurs au niveau du système ou aux administrateurs des analyses afin de les préparer à la collecte de données.

## Conditions préalables

[Guide](first-admin-guide.md)d’administration initial d’Adobe Analytics : Assurez-vous qu’un administrateur au niveau du système vous a accordé l’accès à Adobe Analytics via la console d’administration d’Experience Cloud.

## Création d’une suite de rapports

> [!NOTE] Il existe également un moyen de créer une suite de rapports dans Adobe Analytics à l’aide de l’administrateur hérité. Adobe recommande d’utiliser l’assistant de configuration de la suite de rapports décrit ici.

1. Connectez-vous à [experience.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’icône à 9 carrés dans l’angle supérieur droit, puis sur le logo Analytics coloré.
1. Une fenêtre modale "Bienvenue dans Adobe Analytics" doit s’afficher automatiquement. Dans le cas contraire, cliquez sur l’icône d’aide dans l’angle supérieur droit, puis sélectionnez "Bienvenue dans Adobe Analytics".
1. Dans la fenêtre modale, cliquez sur Démarrer la configuration.
1. Suivez chaque invite qui décrit les concepts de base tels que le type de propriété, les industries et le fuseau horaire. Cliquez sur Suivant.
1. La suite de rapports est maintenant créée. Adobe recommande également d’avoir une suite de rapports de développement. Les tests ne nuisent donc pas aux données des clients. Cliquez sur l’icône d’aide dans l’angle supérieur droit, puis sélectionnez de nouveau "Bienvenue dans Adobe Analytics".
1. Dans la fenêtre modale, cliquez sur Démarrer la configuration.
Nommez cette suite de rapports de la même manière, sauf ajouter "- DEV" à la fin. Cette suite de rapports ne recevant que du trafic interne, la taille estimée peut être la plus petite.
1. Cliquez sur Suivant pour terminer la création de votre suite de rapports de développement.

## Résolution des problèmes

**Une fois connecté à Experience Cloud, l’icône Analytics est grisée.**

Cela signifie que votre compte n’a pas reçu les autorisations appropriées pour Analytics. Admin au niveau du système dans votre entreprise pour vous assurer que vous appartenez à un profil doté des autorisations adéquates pour accéder à Adobe Analytics.

**Une fois connecté à Adobe Analytics, il manque la fenêtre contextuelle "Bienvenue dans Adobe Analytics".**

Vérifiez que vous vous êtes connecté via Experience Cloud et non via my.omniture.com. Les utilisateurs qui se connectent via my.omniture.com ne disposent pas de l’assistant de configuration de suite de rapports.

## Étapes suivantes

[Créez et configurez une propriété pour Adobe Analytics au lancement](/help/implement/implement-with-launch/create-analytics-property.md): Création d’une zone pour gérer votre implémentation Analytics
