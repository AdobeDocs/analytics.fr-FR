---
title: Suppression de robots dans Adobe Analytics
description: Comment supprimer des robots dans Adobe Analytics ?
feature: Bot Removal
role: Admin
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: de9d2039411a7f8539f8e7b4eb840f03c964f489
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 75%

---

# Suppression de robots dans Adobe Analytics

Adobe Analytics propose plusieurs options pour supprimer le trafic de robots des rapports :

## Utiliser des règles de robots

Les méthodes de filtrage de robots standard et personnalisées sont prises en charge dans **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Général]** > **[!UICONTROL Règles de robots]** :

| Type de règle | Description |
|--- |--- |
| Règles de robots IAB standard | En sélectionnant l’option **[!UICONTROL Activer les règles de filtrage de robots IAB]**, vous utilisez la liste internationale des robots (International Spiders &amp; Robots List) fournie par l’[IAB](https://www.iab.com/) (Bureau international de la publicité) pour supprimer le trafic de robots. La plupart des clients sélectionnent au moins cette option. |
| Règles de robots personnalisées | Vous pouvez définir et ajouter des règles de robots personnalisées basées sur des agents utilisateurs, des adresses IP ou des plages d’adresses IP. |

Pour plus d’informations, voir [Comprendre et configurer les règles de robots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

## Utiliser une combinaison d’outils Adobe

En outre, comme les robots se transforment rapidement, Adobe propose plusieurs autres fonctionnalités performantes qui, lorsqu’elles sont combinées correctement et régulièrement, peuvent contribuer à venir à bout de ces ennemis de la qualité des données. Ces fonctionnalités sont les suivantes : service Experience Cloud ID, segmentation, Data Warehouse, attributs du client et suites de rapports virtuelles. Voici un aperçu de la manière dont vous pouvez utiliser ces outils.

### Étape 1 : transférer l’Experience Cloud ID de vos visiteurs dans un nouvel ID déclaré

Pour commencer, créez un nouvel ID déclaré dans le [Service principal People](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=fr). Transmettez l’Experience Cloud ID de votre visiteur à ce nouvel ID déclaré. Cela peut s’effectuer rapidement et facilement à l’aide des [balises dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=fr). Utilisons le nom « ECID » pour l’ID déclaré.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-cust-attr-setup.png)

Voici la manière de capturer cet ID via l’élément de données. Veillez à renseigner correctement votre ID d’organisation Experience Cloud dans l’élément de données.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Une fois cet élément de données configuré, suivez [ces instructions](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=fr) pour transmettre les ID déclarés à l’outil ECID à l’aide des balises dans Adobe Experience Platform.

### Étape 2 : utiliser la segmentation pour identifier les robots

Maintenant que l’ECID de votre visiteur est transmis dans un ID déclaré, vous pouvez utiliser la [segmentation dans Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=fr) pour identifier les visiteurs qui se comportent comme des robots. Les robots sont souvent définis par leur comportement : visites à accès unique, agents utilisateurs inhabituels, informations inconnues de l’appareil ou du navigateur, aucun référent, nouveaux visiteurs, pages de destination inhabituelles, etc. Utilisez les fonctions d’exploration et de segmentation de Workspace pour identifier les robots qui ont échappé au filtrage IAB et les règles de robots de votre suite de rapports. Par exemple, voici une capture d’écran d’un segment que vous pouvez utiliser :

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg1.png)

### Étape 3 : exporter tous les [!DNL Experience Cloud IDs] du segment via Data Warehouse

Maintenant que vous avez identifié les robots à l’aide de segments, l’étape suivante consiste à utiliser Data Warehouse pour extraire tous les Experience Cloud ID associés à ce segment. La copie d’écran montre comment vous devez configurer votre demande [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) :

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-dwh-3.png)

N’oubliez pas d’utiliser l’identifiant visiteur Experience Cloud comme dimension et d’appliquer le segment « Robots ».

### Étape 4 : renvoyer cette liste à Adobe en tant qu’attribut du client

Une fois le rapport Data Warehouse généré, vous disposez d’une liste des ECID qui doivent être filtrés à partir des données historiques. Copiez et collez ces ECID dans un fichier .CSV vide avec seulement deux colonnes, ECID et Indicateur de robot.

* **ECID** : assurez-vous que cet en-tête de colonne correspond au nom que vous avez donné au nouvel ID déclaré ci-dessus.
* **Indicateur de robot** : ajoutez « Indicateur de robot » en tant que dimension de schéma d’attribut du client.

Utilisez ce fichier .CSV comme fichier d’importation d’attributs du client, puis abonnez vos suites de rapports à l’attribut du client, comme décrit dans cet [article de blog](https://blog.adobe.com/en/publish/2016/10/20/link-digital-behavior-customers).

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-csv-4.png)

### Étape 5 : créer un segment qui utilise le nouvel attribut du client

Une fois votre jeu de données traité et intégré dans Analysis Workspace, créez un segment supplémentaire qui tire parti de votre nouvelle dimension d’attribut client « Indicateur de robot » et un conteneur [!UICONTROL Exclure] :

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg2.png)

### Étape 6 : utiliser ce segment comme filtre de suite de rapports virtuelle

Enfin, créez une [suite de rapports virtuelle](/help/components/vrs/vrs-about.md) qui utilise ce segment pour filtrer les robots identifiés :

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-vrs.png)

Cette suite de rapports virtuelle récemment segmentée se caractérise désormais par un ensemble de données plus propre, les robots identifiés étant supprimés.

### Étape 7 : répéter régulièrement les étapes 2, 3 et 4

Définissez au moins un rappel mensuel pour identifier et filtrer les nouveaux robots, peut-être avant l’analyse régulièrement programmée.

>[!MORELIKETHIS]
>
>* [Meilleur Blocage Des Robots (Partie 1) : Principes De Base](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-1-the-basics/ba-p/715839?profile.language=fr)
>* [Meilleur blocage des robots (partie 2) : identification des robots et utilisation de CIDR](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-2-identifying-bots-and-leveraging-cidr/ba-p/722132?profile.language=fr)
>* [Meilleur Blocage Des Robots (Partie 3) : Le Gouverneur D’Accès](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/better-bot-blocking-part-3-the-hit-governor/ba-p/727051?profile.language=fr)

