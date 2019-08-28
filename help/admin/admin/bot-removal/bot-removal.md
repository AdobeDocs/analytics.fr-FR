---
title: Suppression de robots dans Adobe Analytics
seo-title: Suppression de robots dans Adobe Analytics
description: 3 méthodes de suppression des robots dans Adobe Analytics
seo-description: 3 méthodes de suppression des robots dans Adobe Analytics
translation-type: tm+mt
source-git-commit: 0e882f4908dababaf96cf225c62f7ab3bb35860e

---


# Suppression de robots dans Adobe Analytics

Dans Adobe Analytics, vous disposez de plusieurs options pour supprimer le trafic de robots des rapports :

1. La méthode de filtrage des robots par défaut d'Adobe Analytics consiste à [créer des règles](/help/admin/admin/bot-removal/bot-rules.md) de robots basées sur la liste des robots IAB. Cette liste est mise à jour tous les mois et compile sa liste à partir de nombreuses sources, notamment les CDN et les principales propriétés Internet. Il comprend des milliers de robots connus, dont tous vos favoris : Google, Bing, Mozilla, etc. Cette liste couvre la plupart des cas d'utilisation et besoins liés à la filtration des robots.

1. Utilisez le module de mise en œuvre [s. hitdictionary](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/plugins/hitgovernor.html), ce qui supprime les visiteurs qui se comportent comme des robots en envoyant des dizaines ou des centaines d'accès par minute.

1. De plus, comme les robots avancent rapidement, Adobe propose plusieurs autres fonctionnalités puissantes qui, lorsqu'elles sont combinées correctement et régulièrement, peuvent contribuer à la suppression de ces ennemis de la qualité des données. Ces fonctionnalités sont les suivantes : Service d'identification d'expérience, segmentation, entrepôt de données, attributs du client et suites de rapports virtuelles. Vous trouverez ci-dessous un aperçu de la manière dont vous pouvez exploiter ces outils :

## Étape 1 : Transmettez l'identifiant d'expérience de vos visiteurs dans un nouvel identifiant déclaré.

Pour commencer, vous souhaitez créer un identifiant déclaré dans le service principal [Audiences](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html). Vous devez transmettre l'identifiant d'expérience du visiteur à ce nouvel identifiant déclaré, ce qui peut être effectué rapidement et facilement avec [le lancement d'Adobe Experience Platform. ](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) Utilisons le nom « ECID » pour l'identifiant déclaré.

capture d'écran ici

Voici comment cet ID peut être capturé via l'élément de données. Veillez à renseigner correctement votre ID Adobe ecorg dans l'élément de données.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Une fois cet élément de données configuré, suivez [ces instructions](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) pour transmettre les ID déclarés à l'outil ECID au lancement.

## Étape 2 : Utilisation de la segmentation pour identifier les robots

Maintenant que l'ECID du visiteur est transmis à un ID déclaré, il est temps d'utiliser la segmentation dans Analysis Workspace pour identifier les visiteurs qui agissent comme des robots. Les robots sont souvent définis par leur comportement : visites d'accès unique, agents utilisateur inhabituels, informations inconnues sur le périphérique/navigateur, aucun référent, nouveaux visiteurs, pages d'entrée inhabituelles, etc. Utilisez les puissances des listes déroulantes Workspace et de la segmentation pour identifier les robots qui ont un filtrage IAB evéré et les règles de robots de vos suites de rapports. Par exemple, voici une capture d'écran d'un segment que vous pouvez utiliser :

![](assets/bot-filter-seg1.png)

## Étape 3 : Exportation de tous les identifiants électroniques du segment via l'entrepôt de données

Maintenant que vous avez identifié les robots à l'aide de segments, l'étape suivante consiste à tirer parti de Data Warehouse pour extraire tous les ID d'expérience associés à ce segment. Voici comment configurer votre rapport [Entrepôt](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) de données :

![](assets/bot-dwh-3.png)

Pensez à utiliser l'identifiant visiteur Experience Cloud comme dimension et appliquez le segment Robots.

## Étape 4 : Renvoi de cette liste à Adobe en tant qu'attribut du client

Une fois le rapport Entrepôt de données arrivé, vous disposez d'une liste des identifiants électroniques qui doivent être filtrés à partir des données historiques. Copiez et collez ces ecid dans un fichier. CSV vide avec uniquement deux colonnes, ECID et Flag Flag :

![](assets/bot-csv-4.png)

Assurez-vous que le premier en-tête de colonne correspond au nom que vous avez attribué au nouvel identifiant déclaré ci-dessus. Utilisez ce fichier. CSV comme fichier d'importation d'attributs du client, puis abonnez-vous à votre ou vos suites de rapports à l'attribut du client comme décrit dans cette publication [de blog](https://theblog.adobe.com/link-digital-behavior-customers).

## Étape 5 : Création d'un segment qui exploite le nouvel attribut du client

Une fois votre jeu de données traité et intégré à Analysis Workspace, créez un segment supplémentaire qui exploite votre nouvelle dimension d'attribut « Indicateur de robot » :

![](assets/bot-filter-seg2.png)

## Étape 6 : Utiliser ce segment comme filtre de suite de rapports virtuelle

Enfin, vous devez créer une suite de rapports virtuelle qui utilise ce segment pour filtrer les robots identifiés :

![](assets/bot-vrs.png)

Cette suite de rapports virtuelle nouvellement segmentée va maintenant déboucher sur un ensemble de données nettement plus restreint avec les robots identifiés complètement supprimés.

## Étape 7 : Répétez les étapes 2, 3 et 4 régulièrement.

Définissez au moins un rappel mensuel pour identifier et filtrer les nouveaux robots, avant d'effectuer une analyse régulière.

