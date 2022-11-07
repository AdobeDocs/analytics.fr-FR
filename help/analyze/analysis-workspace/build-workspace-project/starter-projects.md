---
description: Création de projets Workspace basés sur des modèles standard ou personnalisés.
title: Modèles
feature: Workspace Basics
role: User, Admin
exl-id: 751399fe-6d4f-47cc-8827-82c992079b52
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '1311'
ht-degree: 100%

---

# Modèles

Vous pouvez créer un projet d’après :

* **Projet vierge (par défaut)** : Pour obtenir des instructions, voir [Création d’un projet Analysis Workspace](/help/analyze/analysis-workspace/home.md).
* **Modèle standard** : Ces modèles sont créés par Adobe et livrés avec le produit.
* **Modèle personnalisé** : Ces modèles peuvent être créés, partagés ou supprimés par les utilisateurs disposant ou non de droits d’administration, à condition qu’ils aient reçu l’autorisation [!UICONTROL Analysis Workspace : enregistrer comme modèle] dans l’Admin Console. [En savoir plus...](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=fr)

![](assets/start_modal.png)

## Création de modèles personnalisés {#create-custom-template}

Les utilisateurs dotés de droits d’administration peuvent convertir n’importe quel projet qu’ils créent en un modèle personnalisé. Procédez comme suit :

1. Ouvrez le projet.
1. Sélectionnez **[!UICONTROL Projet]** > **[!UICONTROL Enregistrer comme modèle]**.

   ![](assets/save_project_template.png)

   Le projet enregistré sera nommé avec le nom du projet en cours suivi du mot « (Modèle) ». Les administrateurs peuvent changer ce nom en modifiant le modèle.

   >[!NOTE]
   >
   >Par défaut, toutes les personnes de l’organisation ont accès aux modèles de projet. Vous pouvez organiser les modèles en leur appliquant des balises. (Sélectionnez **[!UICONTROL Projet]** > **[!UICONTROL Informations et paramètres du projet]** pour modifier les balises et les descriptions.)

Regardez cette vidéo sur la création et la gestion de modèles personnalisés :

>[!VIDEO](https://video.tv.adobe.com/v/23231/?quality=12)

### Gestion de modèles personnalisés {#manage-custom-template}

| Action | Description |
|--- |--- |
| Modifier   le modèle | Permet à un administrateur de modifier le modèle en changeant sa source de données, en modifiant les composants, les visualisations, les périodes, etc.  Pour modifier un modèle personnalisé, procédez de l’une des manières suivantes :<ul><li>affichez la liste des modèles personnalisés dans Analysis Workspace, sélectionnez-en un, puis cliquez sur Modifier le modèle ; ou</li><li>dans Analytics, sélectionnez Composants > Projets, puis filtrez les projets en fonction des Modèles. Cliquez sur le nom du modèle à modifier.</li></ul>**Remarque :** après avoir modifié un modèle, deux options se présentent, selon le cas : Enregistrer ou Enregistrer sous. Ces deux options diffèrent comme suit :<ul><li>**Enregistrer :** met à jour le modèle personnalisé pour tous les utilisateurs. Si quelqu’un crée un projet d’après ce modèle personnalisé, il verra les modifications que vous avez apportées.</li><li>**Enregistrer sous :** crée une copie du modèle personnalisé avec vos modifications. (En mode de modification, le menu Partager > Partager le projet est désactivé.)</li></ul> |
| Rechercher des modèles | Dans la boîte de dialogue Modèles personnalisés, cliquez sur Rechercher des modèles. |
| Trier des modèles | Vous pouvez trier les modèles par ordre alphabétique, par pertinence et par date de création.  Dans la boîte de dialogue Modèles personnalisés, cliquez sur Tri. |
| Appliquer des balises à un modèle | Ouvrez le modèle et sélectionnez Projet > Informations et paramètres du projet. Cliquez sur Ajouter des balises. |
| Modifier la description du modèle | Ouvrez le modèle et sélectionnez Projet > Informations et paramètres du projet. Double-cliquez sur la description pour la modifier. |


## Modèles standard

Lorsque vous ouvrez un Workspace pour la première fois, les modèles sont disponibles dans le rail de gauche. Les modèles Analysis Workspace couvrent les cas d’utilisation courants. Ils sont groupés selon le marché vertical auquel ils appartiennent et comprennent différents segments, dimensions, mesures et visualisations, selon la suite de rapports sélectionnée.

Utilisez ces modèles prérenseignés tels quels ou adaptez-les en fonction de vos besoins (en ajoutant des mesures ou des visualisations, ou en les remplaçant, par exemple) et enregistrez-les sous un nouveau nom.

Voici un tutoriel vidéo sur les [modèles standard dans Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/standard-templates-in-analysis-workspace.html?lang=fr) (2:46)

Voici les modèles disponibles et les questions auxquelles chaque modèle peut contribuer à répondre.

### Formation

Ce modèle standard vous guide dans la terminologie et les étapes courantes de création de votre première analyse dans Workspace. Il est disponible sous forme de modèle standard dans le modal Nouveau projet et remplace l’exemple de projet qui existe aujourd’hui pour les nouveaux utilisateurs qui n’ont pas d’autres projets dans leur liste.

Regardez cette vidéo sur le modèle [!UICONTROL Tutoriel de formation] :

>[!VIDEO](https://video.tv.adobe.com/v/33773/?quality=12)

### Publicité

>[!IMPORTANT]
>
>Les modèles Publicité sont accessibles uniquement si votre suite de rapports est activée pour [Advertising Analytics](https://experienceleague.adobe.com/docs/analytics/integration/advertising-analytics/overview.html?lang=fr).

* **Moteurs de recherche payante** : ce modèle ventile les tendances publicitaires, les plateformes publicitaires, les mots-clés, les comptes, les campagnes, etc.

### Commerce

* **Magento : Marketing et commerce** : ce modèle ventile la conversion de votre commerce sur internet en fonction de l’attribution du canal marketing et fournit des informations par mot-clé de recherche, landing page, emplacement géographique, etc. Regardez ce tutoriel vidéo sur [Magento : modèle Marketing et Commerce](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/magento/magento-analysis-workspace-template.html?lang=fr).

### Collecte de données

* **Effets de lʼITP** : comprenez comment la fonctionnalité ITP dʼApple affecte vos données et comment ajuster les rapports en conséquence.

### Média

* **Consommation de contenu** : qui sont mes fidèles lecteurs ?
* **Récence - Fréquence - Fidélité** : quel est le contenu le plus consommé et qui intéresse le plus les utilisateurs ?
* **Consommation de médias en continu** : fournit des tendances et des mesures principales relatives à la consommation des médias sur tous les appareils numériques. Regardez cette vidéo sur le modèle de consommation de médias en continu :

   >[!VIDEO](https://video.tv.adobe.com/v/23901/?quality=12)

### Mobile

>[!IMPORTANT]
>
>Les modèles mobiles sont accessibles uniquement si votre suite de rapports est activée pour les analyses des applications mobiles.

* **Acquisition :** contrôlez les performances des liens d’acquisition mobile.
* **Utilisation de l’application :** combien d’utilisateurs, de lancements et de premiers lancements de l’application avait l’application et quelle est la durée de session moyenne ?
* **Parcours :** quels sont les schémas d’utilisation dominants de mon application ?
* **Mesures clés :** sachez de quelle façon se comportent les mesures clés de votre application.
* **Emplacement :** comprend une carte représentant les données de positionnement.
* **Message :** est axé sur les performances de la messagerie in-app et push.
* **Performances :** quelles sont les performances de l’application et où les utilisateurs rencontrent-ils des problèmes ?
* **Rétention :** qui sont mes fidèles utilisateurs et que font-ils ?

### Vente au détail

* **Performances de la campagne :** quelles campagnes génèrent le plus de recettes ?
* **Produits :** quels produits sont les plus performants ?

### Web

* **Acquisition :** quels sont les principaux facteurs orientant le trafic vers mon site web ?
* **Performances du site AEM - Aperçu :** quelles sont les performances de mon site Adobe Experience Manager ?
* **Consommation de contenu :** où se rendent surtout les personnes sur mon site ?
* **Rétention :** quels types d’utilisateurs seront a priori les plus fidèles à mon site ?
* **Technologie :** quelle technologie utilisent les visiteurs de mon site ?

### Personnes

Ce modèle repose sur la mesure Personnes, qui est une version dédupliquée de la mesure Visiteurs uniques. La mesure Personnes permet d’évaluer à quelle fréquence les internautes utilisent différents appareils pour interagir avec votre marque. Le modèle permet d’accomplir ce qui suit : 

* Segmenter vos données pour les États-Unis/le Canada et le reste du monde
* Comparer côte à côte les mesures Personnes et Visiteurs uniques
* Afficher le « taux de compression », une mesure calculée qui détermine à quel point le résultat de la mesure Personnes, en pourcentage, est plus petit que celui de la mesure Visiteurs uniques
* Comparer les nombres totaux de types de périphériques utilisés par vos clients.
* Afficher le nombre moyen de périphériques utilisés par personne
* Découvrir comment utiliser l’empilement des segments avec la mesure Personnes
* Découvrir comment l’utilisation d’Experience Cloud ID dans votre environnement améliore l’efficacité de la mesure Personnes

### Journey IQ : modèle dʼanalyses entre appareils

<!--This content is mirrored in the CDA doc.-->

Ce modèle vous permet de visualiser des données de performances cruciales entre appareils. Il est disponible uniquement pour les clients qui ont accès à [l’Analyse entre appareils](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=fr) (CDA).

* **Identification des utilisateurs** : Indique la fréquence à laquelle les visiteurs de votre site sont identifiés à l’aide de méthodes basées sur les analyses entre appareils.
* **Mesure de la taille des audiences** : Affiche une comparaison entre « Appareils uniques » et « Personnes ». La proportion entre ces deux nombres est connue sous le nom de « Compression entre appareils », une mesure calculée visible dans ce panneau. Cette mesure de compression dépend d’un large éventail de facteurs :
   * **Taux de connexion** : plus les utilisateurs se connectent sur votre site, plus Adobe est en mesure d’identifier et de regrouper les visiteurs entre plusieurs appareils. Les sites qui présentent un faible taux de connexion ont aussi de faibles taux de compression.
   * **Couverture d’Experience Cloud ID** : seuls les visiteurs avec un ECID peuvent être regroupés. Un pourcentage plus faible de visiteurs qui accèdent à votre site en utilisant un ECID correspond à des taux de compression plus faibles.
   * **Utilisation de plusieurs appareils** : si les visiteurs qui se rendent sur votre site n’utilisent pas plusieurs appareils, les taux de compression sont plus faibles.
   * **Granularité des rapports** : la compression par jour est généralement plus petite que la compression par mois ou par année. Les chances qu’une personne utilise plusieurs appareils sont moindres au cours d’un seul jour qu’au cours d’un mois entier. La segmentation, le filtrage ou l’utilisation de dimensions de ventilation peuvent également indiquer un taux de compression plus faible.
* **Segments basés sur les personnes** : Contient une liste déroulante de segments qui vous permet d’afficher des données spécifiques à l’appareil. Ce panneau encourage l’expérimentation de segments afin de déterminer comment l’inclusion ou l’exclusion de types d’appareil affectent les rapports.
* **Analyse du parcours entre appareils** : Fournit des rapports de flux et d’abandons en fonction du type d’appareil.
* **Attribution entre appareils** : Combinez les fonctionnalités Journey IQ et Attribution IQ.
* **Autres conseils et astuces** : Rubriques utiles sur les Analyses entre appareils qui vous permettent de mieux l’utiliser.
