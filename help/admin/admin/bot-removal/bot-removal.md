---
title: Suppression de robots dans Adobe Analytics
seo-title: Suppression de robots dans Adobe Analytics
description: 3 méthodes pour supprimer des robots dans Adobe Analytics
seo-description: 3 méthodes pour supprimer des robots dans Adobe Analytics
translation-type: tm+mt
source-git-commit: ef17712b4a8a4a5c13dde9be9fdf2281eeb40091

---


# Suppression de robots dans Adobe Analytics

Dans Adobe Analytics, vous disposez de plusieurs options pour supprimer le trafic de robots des rapports :

## Utiliser des règles de robots

Les méthodes de filtrage de robots standard et personnalisées sont prises en charge dans **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; Suites **[!UICONTROL de]** rapports &gt; **[!UICONTROL Modifier les paramètres &gt; Général &gt; Règlesde robots de :]**********

| Type de règle | Description |
|--- |--- |
| Règles de robots IAB standard | La sélection de l’option **[!UICONTROL Activer les règles]** de filtrage des robots IAB utilise la liste internationale des moteurs de balayage et des robots de l’ [](https://www.iab.com/) IAB (Bureau international de la publicité) pour supprimer le trafic de robots. La plupart des clients sélectionnent cette option au minimum. |
| Règles de robots personnalisées | Vous pouvez définir et ajouter des règles de robots personnalisées basées sur des agents utilisateur, des adresses IP ou des plages d’adresses IP. |

Pour plus d’informations, voir Présentation [des règles](/help/admin/admin/bot-removal/bot-rules.md)de robots.

## Utilisation du module `hitGovernor` d’implémentation

Utilisez le module [d’implémentation](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/plugins/hitgovernor.html)s.hitGovernor, qui supprime les visiteurs qui se comportent comme des robots, ce qui signifie que ces visiteurs envoient des dizaines ou des centaines d’accès par minute.

## Utilisation d’une combinaison d’outils Adobe

En outre, comme les robots se transforment rapidement, Adobe propose plusieurs autres fonctionnalités puissantes qui, lorsqu’ils sont combinés correctement et régulièrement, peuvent contribuer à la suppression de ces ennemis de la qualité des données. Ces fonctionnalités sont les suivantes : Service d’ID Experience Cloud, Segmentation, Entrepôt de données, Attributs du client et Suites de rapports virtuelles. Voici un aperçu de la manière dont vous pouvez tirer parti de ces outils.

### Étape 1 : Transférez l’ID Experience Cloud de vos visiteurs dans un nouvel ID déclaré.

Pour commencer, vous souhaiterez créer un nouvel identifiant déclaré dans le service [principal](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html)Personnes. Vous devez transmettre l’ID Experience Cloud de votre visiteur à ce nouvel ID déclaré, qui peut être effectué rapidement et facilement avec le lancement [d’](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html)Adobe Experience Platform. Utilisons le nom "ECID" pour l’identifiant déclaré.

![](assets/bot-cust-attr-setup.png)

Voici comment cet identifiant peut être capturé via l’élément de données. Veillez à renseigner correctement votre ID d’organisation Experience Cloud dans l’élément de données.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Une fois cet élément de données configuré, suivez [ces instructions](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) pour transmettre les ID déclarés à l’outil ECID au lancement.

### Étape 2 : Utiliser la segmentation pour identifier les robots

Maintenant que l’ECID de votre visiteur est transmis dans un identifiant déclaré, vous pouvez utiliser [la segmentation dans Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) pour identifier les visiteurs qui se comportent comme des robots. Les robots sont souvent définis par leur comportement : visites à accès unique, agents utilisateur inhabituels, informations inconnues sur le périphérique ou le navigateur, aucun référent, nouveaux visiteurs, pages d'entrée inhabituelles, etc. Utilisez les fonctions d’exploration et de segmentation de Workspace pour identifier les robots qui ont échappé au filtrage IAB et les règles de robots de votre suite de rapports. Par exemple, voici une capture d’écran d’un segment que vous pouvez utiliser :

![](assets/bot-filter-seg1.png)

### Étape 3 : Exporter tout [!DNL Experience Cloud IDs] du segment via l’entrepôt de données

Maintenant que vous avez identifié les robots à l’aide de segments, l’étape suivante consiste à exploiter l’entrepôt de données pour extraire tous les ID Experience Cloud associés à ce segment. Voici comment configurer votre requête [Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) :

![](assets/bot-dwh-3.png)

N’oubliez pas d’utiliser l’identifiant visiteur Experience Cloud comme dimension et d’appliquer le segment Robots.

### Étape 4 : Renvoyer cette liste à Adobe en tant qu’attribut du client

Une fois le rapport Entrepôt de données généré, vous disposez d’une liste d’ECID qui doivent être filtrés à partir des données historiques. Copiez et collez ces fichiers ECID dans un fichier .CSV vide contenant seulement deux colonnes, ECID et Bot Flag.

* **ECID**: Assurez-vous que cet en-tête de colonne correspond au nom que vous avez donné au nouvel ID déclaré ci-dessus.
* **Indicateur** de robot : Ajoutez-le en tant que dimension de schéma d’attribut client.

Utilisez ce fichier .CSV comme fichier d’importation d’attributs du client, puis abonnez vos suites de rapports à l’attribut du client, comme décrit dans cette publication [de](https://theblog.adobe.com/link-digital-behavior-customers)blog.

![](assets/bot-csv-4.png)

### Étape 5 : Créez un segment qui tire parti du nouvel attribut du client

Une fois votre jeu de données traité et intégré dans Analysis Workspace, créez un segment supplémentaire qui exploite votre nouvelle dimension d’attribut client "Bot Flag" et un conteneur [!UICONTROL Exclure] :

![](assets/bot-filter-seg2.png)

### Étape 6 : Utiliser ce segment comme filtre de suite de rapports virtuelle

Enfin, vous devez créer une suite [de rapports](/help/components/vrs/vrs-about.md) virtuelle qui utilise ce segment pour filtrer les robots identifiés :

![](assets/bot-vrs.png)

Cette suite de rapports virtuelle nouvellement segmentée se traduit désormais par un ensemble de données significativement plus propre, les robots identifiés étant complètement supprimés.

### Étape 7 : Répétez régulièrement les étapes 2, 3 et 4

Définissez au moins un rappel mensuel pour identifier et filtrer les nouveaux robots, peut-être avant l’analyse programmée régulièrement.
