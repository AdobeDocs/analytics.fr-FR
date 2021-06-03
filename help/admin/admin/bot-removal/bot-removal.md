---
title: Suppression de robots dans Adobe Analytics
description: Comment supprimer des robots dans Adobe Analytics
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 52%

---

# Suppression de robots dans Adobe Analytics

Dans Adobe Analytics, vous disposez de plusieurs options pour supprimer le trafic des robots des rapports :

## Utiliser des règles de robots

Les méthodes de filtrage de robots standard et personnalisées sont prises en charge dans **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de robots]** :

| Type de règle | Description |
|--- |--- |
| Règles de robots IAB standard | En sélectionnant l’option **[!UICONTROL Activer les règles de filtrage de robots IAB]**, vous utilisez la liste internationale des robots (International Spiders &amp; Robots List) fournie par l’[IAB](https://www.iab.com/) (Bureau international de la publicité) pour supprimer le trafic de robots. La plupart des clients sélectionnent au moins cette option. |
| Règles de robots personnalisées | Vous pouvez définir et ajouter des règles de robots personnalisées basées sur des agents utilisateur, des adresses IP ou des plages d’adresses IP. |

Pour plus d’informations, voir [Présentation des règles de robots](/help/admin/admin/bot-removal/bot-rules.md).

## Utilisez le plug-in [!UICONTROL websiteBot] pour identifier les robots.

Le plug-in [!UICONTROL websiteBot] vous permet d’identifier dynamiquement si les visiteurs de bureau sont des robots. Vous pouvez utiliser ces données pour accroître la précision de tous les types de comptes rendus des performances, ce qui vous permet de mieux mesurer le trafic légitime sur le site.

Ce module effectue deux vérifications :

* Tout d’abord, il détermine si l’appareil est un ordinateur de bureau ou un appareil mobile à l’aide de la variable navigator.UserAgent . Les appareils mobiles sont ignorés.
* S’il s’agit d’un ordinateur, il ajoute un écouteur d’événements pour les mouvements de souris.

Pour plus d’informations, voir le [Guide de mise en oeuvre d’Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html).

## Utiliser une combinaison d’outils Adobe

En outre, comme les robots se transforment rapidement, Adobe propose plusieurs autres fonctionnalités performantes qui, lorsqu’elles sont combinées correctement et régulièrement, peuvent contribuer à venir à bout de ces ennemis de la qualité des données. Ces fonctionnalités sont les suivantes : le service Experience Cloud ID, la segmentation, Data Warehouse, les attributs du client et les suites de rapports virtuelles. Voici un aperçu de la manière dont vous pouvez utiliser ces outils.

### Étape 1 : transférer l’Experience Cloud ID de vos visiteurs dans un nouvel ID déclaré

Pour commencer, créez un ID déclaré dans le [service principal People](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html). Transmettez l’identifiant Experience Cloud de votre visiteur dans ce nouvel identifiant déclaré, ce qui peut être effectué rapidement et facilement avec [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html). Utilisons le nom « ECID » pour l’ID déclaré.

![](assets/bot-cust-attr-setup.png)

Voici la manière de capturer cet ID via l’élément de données. Veillez à renseigner correctement votre ID d’organisation Experience Cloud dans l’élément de données.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Une fois cet élément de données configuré, suivez [ces instructions](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) pour transmettre les identifiants déclarés à l’outil ECID dans Adobe Launch.

### Étape 2 : utiliser la segmentation pour identifier les robots

Maintenant que l’ECID de votre visiteur est transmis dans un ID déclaré, vous pouvez utiliser la [segmentation dans Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) pour identifier les visiteurs qui se comportent comme des robots. Les robots sont souvent définis par leur comportement : visites à accès unique, agents utilisateurs inhabituels, informations inconnues de l’appareil ou du navigateur, aucun référent, nouveaux visiteurs, pages d’entrée inhabituelles, etc. Utilisez les fonctions d’exploration et de segmentation de Workspace pour identifier les robots qui ont échappé au filtrage IAB et les règles de robots de votre suite de rapports. Par exemple, voici une capture d’écran d’un segment que vous pouvez utiliser :

![](assets/bot-filter-seg1.png)

### Étape 3 : exporter tous les [!DNL Experience Cloud IDs] du segment via Data Warehouse

Maintenant que vous avez identifié les robots à l’aide de segments, l’étape suivante consiste à utiliser Data Warehouse pour extraire tous les identifiants Experience Cloud associés à ce segment. Cette capture d’écran montre comment configurer votre requête [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) :

![](assets/bot-dwh-3.png)

N’oubliez pas d’utiliser l’identifiant visiteur Experience Cloud comme dimension et d’appliquer le segment &quot;Robots&quot;.

### Étape 4 : Renvoyer cette liste à Adobe en tant qu’attribut du client

Une fois le rapport du Data Warehouse généré, vous disposez d’une liste d’ECID qui doivent être filtrés à partir des données historiques. Copiez et collez ces ECID dans un fichier .CSV vide avec seulement deux colonnes, ECID et Indicateur de robot.

* **ECID** : Assurez-vous que cet en-tête de colonne correspond au nom que vous avez donné au nouvel ID déclaré ci-dessus.
* **Indicateur de robot** : Ajoutez &quot;Indicateur de robot&quot; en tant que dimension de schéma d’attribut du client.

Utilisez ce fichier .CSV comme fichier d’importation d’attribut du client, puis abonnez vos suites de rapports à l’attribut du client, comme décrit dans cet [article de blog](https://theblog.adobe.com/link-digital-behavior-customers).

![](assets/bot-csv-4.png)

### Étape 5 : Créer un segment qui tire parti du nouvel attribut du client

Une fois votre jeu de données traité et intégré dans Analysis Workspace, créez un segment supplémentaire qui tire parti de votre nouvelle dimension d’attribut client &quot;Indicateur de robot&quot; et un conteneur [!UICONTROL Exclure] :

![](assets/bot-filter-seg2.png)

### Étape 6 : Utiliser ce segment comme filtre de suite de rapports virtuelle

Enfin, créez une [suite de rapports virtuelle](/help/components/vrs/vrs-about.md) qui utilise ce segment pour filtrer les robots identifiés :

![](assets/bot-vrs.png)

Cette suite de rapports virtuelle nouvellement segmentée génèrera désormais un jeu de données plus propre, avec les robots identifiés supprimés.

### Étape 7 : Répéter régulièrement les étapes 2, 3 et 4

Définissez au moins un rappel mensuel pour identifier et filtrer les nouveaux robots, peut-être avant une analyse régulièrement planifiée.
