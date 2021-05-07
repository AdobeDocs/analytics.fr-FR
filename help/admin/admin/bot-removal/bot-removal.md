---
title: Suppression de robots dans Adobe Analytics
description: Suppression de robots en Adobe Analytics
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
translation-type: tm+mt
source-git-commit: bb8ccbf782a1431e5278a95923a42c9e9e9e862b
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 53%

---

# Suppression de robots dans Adobe Analytics

Dans Adobe Analytics, vous disposez de plusieurs options pour supprimer le trafic des robots des rapports :

## Utiliser des règles de robots

Les méthodes de filtrage de robots standard et personnalisées sont prises en charge dans **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de robots]** :

| Type de règle | Description |
|--- |--- |
| Règles de robots IAB standard | En sélectionnant l’option **[!UICONTROL Activer les règles de filtrage de robots IAB]**, vous utilisez la liste internationale des robots (International Spiders &amp; Robots List) fournie par l’[IAB](https://www.iab.com/) (Bureau international de la publicité) pour supprimer le trafic de robots. La plupart des clients sélectionnent au moins cette option. |
| Règles de robots personnalisées | Vous pouvez définir et ajouter des règles de robots personnalisées en fonction des agents utilisateur, des adresses IP ou des plages d’adresses IP. |

Pour plus d’informations, voir [Présentation des règles de robots](/help/admin/admin/bot-removal/bot-rules.md).

## Utilisez le module externe [!UICONTROL webBot] pour identifier les robots

Le module externe [!UICONTROL webBot] vous permet d’identifier de manière dynamique si les visiteurs de bureau sont des robots. Vous pouvez utiliser ces données pour accroître la précision de tous les types de comptes rendus des performances, ce qui vous permet de mieux mesurer le trafic légitime sur le site.

Ce module effectue deux vérifications :

* Tout d’abord, il détermine si le périphérique est un ordinateur de bureau ou un périphérique mobile à l’aide de la variable navigator.UserAgent. Les appareils mobiles sont ignorés.
* S’il s’agit d’un ordinateur, il ajoute un écouteur d’événements pour les mouvements de souris.

Pour plus d’informations, consultez le [Guide de mise en oeuvre Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html).

## Utiliser une combinaison d’outils Adobe

En outre, comme les robots se transforment rapidement, Adobe propose plusieurs autres fonctionnalités performantes qui, lorsqu’elles sont combinées correctement et régulièrement, peuvent contribuer à venir à bout de ces ennemis de la qualité des données. Ces fonctionnalités sont les suivantes : le service Experience Cloud ID, la segmentation, Data Warehouse, les attributs du client et les suites de rapports virtuelles. Voici un aperçu de la façon dont vous pouvez utiliser ces outils.

### Étape 1 : transférer l’Experience Cloud ID de vos visiteurs dans un nouvel ID déclaré

Pour début, créez un nouvel identifiant déclaré dans le service principal [Personnes](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html). Transférez votre Experience Cloud visiteur ID dans ce nouvel ID déclaré, qui peut être effectué rapidement et facilement avec [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html). Utilisons le nom « ECID » pour l’ID déclaré.

![](assets/bot-cust-attr-setup.png)

Voici la manière de capturer cet ID via l’élément de données. Veillez à renseigner correctement votre OrgID Experience Cloud dans l’élément de données.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Une fois cet élément de données configuré, suivez [ces instructions](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) pour transmettre les identifiants déclarés à l&#39;outil ECID dans le lancement d&#39;Adobe.

### Étape 2 : utiliser la segmentation pour identifier les robots

Maintenant que l’ECID de votre visiteur est transmis dans un ID déclaré, vous pouvez utiliser la [segmentation dans Analysis Workspace](https://docs.adobe.com/content/help/fr-FR/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) pour identifier les visiteurs qui se comportent comme des robots. Les robots sont souvent définis par leur comportement : visites à accès unique, agents utilisateurs inhabituels, informations inconnues de l’appareil ou du navigateur, aucun référent, nouveaux visiteurs, pages d’entrée inhabituelles, etc. Utilisez les fonctions d’exploration et de segmentation de Workspace pour identifier les robots qui ont échappé au filtrage IAB et les règles de robots de votre suite de rapports. Par exemple, voici une capture d’écran d’un segment que vous pouvez utiliser :

![](assets/bot-filter-seg1.png)

### Étape 3 : exporter tous les [!DNL Experience Cloud IDs] du segment via Data Warehouse

Maintenant que vous avez identifié les robots à l’aide de segments, l’étape suivante consiste à utiliser le Data Warehouse pour extraire tous les ID d’Experience Cloud associés à ce segment. Cette capture d’écran montre comment configurer votre requête [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) :

![](assets/bot-dwh-3.png)

N’oubliez pas d’utiliser l’ID de Visiteur Experience Cloud comme dimension et d’appliquer le segment Robots.

### Étape 4 : Renvoyer cette liste à Adobe en tant qu’attribut du client

Une fois le rapport du Data Warehouse reçu, vous disposez d’une liste d’ECID qui doit être filtrée à partir des données historiques. Copiez et collez ces ECID dans un fichier .CSV vide avec seulement deux colonnes, ECID et Indicateur de robot.

* **ECID** : Assurez-vous que cet en-tête de colonne correspond au nom que vous avez attribué au nouvel ID déclaré ci-dessus.
* **Indicateur** de robot : Ajoutez &quot;Bot Flag&quot; en tant que dimension schéma d’attributs du client.

Utilisez ce fichier .CSV comme fichier d’importation d’attribut du client, puis abonnez vos suites de rapports à l’attribut du client, comme décrit dans cet [article de blog](https://theblog.adobe.com/link-digital-behavior-customers).

![](assets/bot-csv-4.png)

### Étape 5 : Créer un segment qui tire parti du nouvel attribut du client

Une fois que votre jeu de données a été traité et intégré à Analysis Workspace, créez un segment supplémentaire qui exploite votre nouvelle dimension d’attribut client &quot;Bot Flag&quot; et un conteneur [!UICONTROL Exclure] :

![](assets/bot-filter-seg2.png)

### Étape 6 : Utiliser ce segment comme filtre de suite de rapports virtuelle

Enfin, créez une [suite de rapports virtuelle](/help/components/vrs/vrs-about.md) qui utilise ce segment pour filtrer les robots identifiés :

![](assets/bot-vrs.png)

Cette suite de rapports virtuelle nouvellement segmentée génère désormais un ensemble de données plus propre, les robots identifiés étant supprimés.

### Étape 7 : Répéter régulièrement les étapes 2, 3 et 4

Définissez au moins un rappel mensuel pour identifier et filtrer les nouveaux robots, peut-être avant une analyse planifiée régulièrement.
