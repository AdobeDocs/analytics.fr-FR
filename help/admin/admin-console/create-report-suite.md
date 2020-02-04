---
title: Création d’une suite de rapports
description: Créez un conteneur de base pour la collecte de données dans Adobe Analytics.
translation-type: tm+mt
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Création d’une suite de rapports

Une suite de rapports est un ensemble de données utilisé par Adobe Analytics pour extraire des rapports. Une entreprise peut avoir plusieurs suites de rapports, contenant chacune différents jeux de données. Bien que des suites de rapports distinctes aient été importantes par le passé, le fait d’avoir une seule suite de rapports est devenu plus avantageux. L’introduction aux suites de rapports virtuelles et au traitement de la période de rapport permet à l’utilisateur de créer ses propres sous-ensembles de données, pour ainsi obtenir des données globales et spécifiques au site.

Cet article est destiné aux administrateurs au niveau du système ou aux administrateurs Analytics afin de les préparer à la collecte de données.

## Conditions préalables

[Guide Adobe Analytics pour le premier administrateur](first-admin-guide.md) : assurez-vous qu’un administrateur au niveau du système vous a accordé l’accès à Adobe Analytics via Admin Console pour Experience Cloud.

## Création d’une suite de rapports

> [!NOTE] Il existe également un moyen de créer une suite de rapports dans Adobe Analytics à l’aide de l’administrateur hérité. Adobe recommande d’utiliser l’assistant de configuration de suites de rapports présenté ici.

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’icône à 9 carrés dans l’angle supérieur droit, puis sur le logo Analytics coloré.
1. Une fenêtre modale « Bienvenue dans Adobe Analytics » devrait s’afficher automatiquement. Dans le cas contraire, cliquez sur l’icône d’aide dans le coin supérieur droit, puis sélectionnez « Bienvenue dans Adobe Analytics ».
1. Dans la fenêtre modale, cliquez sur Commencer la configuration.
1. Suivez chaque invite qui décrit les concepts de base tels que le type de propriété, les secteurs d’activité et le fuseau horaire. Cliquez sur Suivant.
1. La suite de rapports est maintenant créée. Adobe recommande également de disposer d’une suite de rapports de développement afin que les tests ne nuisent pas aux données des clients. Cliquez sur l’icône d’aide dans le coin supérieur droit, puis sélectionnez à nouveau « Bienvenue dans Adobe Analytics ».
1. Dans la fenêtre modale, cliquez sur Commencer la configuration.
Nommez cette suite de rapports de la même manière, en ajoutant simplement « - DEV » à la fin. Cette suite de rapports ne recevant que du trafic interne, la taille estimée peut être la plus petite.
1. Cliquez sur Suivant pour terminer la création de votre suite de rapports de développement.

Pour plus d’informations sur les étapes de cette fenêtre modale, voir [Mise en oeuvre modale](/help/implement/prepare/implementation-modal.md) dans le guide de l’utilisateur Mise en oeuvre.

## Résolution des problèmes

**Une fois connecté à Experience Cloud, l’icône Analytics est grisée.**

Cela signifie que votre compte n’a pas reçu les autorisations appropriées pour Analytics. Collaborez avec un administrateur au niveau du système de votre entreprise pour vous assurer que vous appartenez à un profil doté des autorisations adéquates pour accéder à Adobe Analytics.

**Une fois connecté à Adobe Analytics, la fenêtre contextuelle « Bienvenue dans Adobe Analytics » ne s’affiche pas.**

Vérifiez que vous vous êtes connecté via Experience Cloud et non via my.omniture.com. En effet, les utilisateurs qui se connectent via my.omniture.com ne disposent pas de l’assistant de configuration de suite de rapports.

## Étapes suivantes

[Créer et configurez une propriété pour Adobe Analytics dans Launch](/help/implement/launch/create-analytics-property.md) : Créer une zone pour gérer votre implémentation Analytics
