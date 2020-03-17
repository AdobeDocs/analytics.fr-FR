---
description: valeur nulle
title: Modèles
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
translation-type: tm+mt
source-git-commit: 08d564f7fb06b94c2010515ea4a1dcbb2e6e2815

---


# Modèles

## Modèles {#topic_40932F09E18A467983AFBB29908E1CB8}

Vous pouvez créer un projet d’après :

* **Projet vierge (par défaut)**: Pour plus d’informations, voir [Création d’un projet](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)d’espace de travail  .
* **Modèle** standard : Ces modèles sont créés par Adobe et livrés avec le produit.
* **Modèle** personnalisé : Ces modèles peuvent être créés, partagés ou supprimés par les utilisateurs disposant de droits d’administration ou par des non-administrateurs, à condition qu’ils aient obtenu l’autorisation [!UICONTROL Analysis Workspace: Save as Template] dans la Console d’administration. [En savoir plus...](https://docs.adobe.com/content/help/en/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Création d’un modèle personnalisé {#create-custom-template}

Les utilisateurs dotés de droits d’administration peuvent convertir n’importe quel projet qu’ils créent en un modèle personnalisé. Procédez comme suit :

1. Ouvrez le projet.
1. Accédez à **[!UICONTROL Project]** > **[!UICONTROL Save As Template]**.

   ![](assets/save_project_template.png)

   Le projet enregistré sera nommé avec le nom du projet en cours suivi du mot « (Modèle) ». Les administrateurs peuvent changer ce nom en modifiant le modèle.

   >[!NOTE]
   >
   >Par défaut, toutes les personnes de l’organisation ont accès aux modèles de projet. Vous pouvez organiser les modèles en leur appliquant des balises. (Accédez à **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]** pour modifier les balises et les descriptions.)

### Actions possibles sur les modèles personnalisés

![](assets/custom_templates.png)

| Action | Description |
|--- |--- |
| Modifier  le modèle | Permet à un administrateur de modifier le modèle en changeant sa source de données, en modifiant les composants, les visualisations, les plages de dates, etc.  Pour modifier un modèle personnalisé, procédez de l’une des manières suivantes :<ul><li>affichez la liste des modèles personnalisés dans Analysis Workspace, sélectionnez-en un, puis cliquez sur Modifier le modèle ; ou</li><li>dans Analytics, sélectionnez Composants > Projets, puis filtrez les projets en fonction des Modèles. Cliquez sur le nom du modèle à modifier.</li></ul>**Remarque :** Après avoir modifié un modèle, deux options se présentent, selon le cas : Enregistrer ou Enregistrer sous. Ces deux options diffèrent comme suit :<ul><li>**Enregistrer :** Met à jour le modèle personnalisé pour tous les utilisateurs. Si quelqu’un crée un projet d’après ce modèle personnalisé, il verra les modifications que vous avez apportées.</li><li>**Enregistrer sous :** Crée une copie du modèle personnalisé avec vos modifications. (En mode de modification, le menu Partager > Partager le projet est désactivé.)</li></ul> |
| Rechercher des modèles | Dans la boîte de dialogue Modèles personnalisés, cliquez sur Rechercher des modèles. |
| Trier des modèles | Vous pouvez trier les modèles par ordre alphabétique, par pertinence et par date de création.  Dans la boîte de dialogue Modèles personnalisés, cliquez sur Tri :. |
| Appliquer des balises à un modèle | Ouvrez le modèle et sélectionnez Projet > Informations et paramètres du projet. Cliquez sur Ajouter des balises. |
| Modifier la description du modèle | Ouvrez le modèle et sélectionnez Projet > Informations et paramètres du projet. Double-cliquez sur la description pour la modifier. |


## Modèles standard {#concept_4FE900FEEC894E849CB6C6A0E0ADA524}

Lorsque vous ouvrez un Workspace pour la première fois, les modèles sont disponibles dans le rail de gauche. Les modèles Analysis Workspace couvrent les cas d’utilisation courants. Ils sont groupés selon le marché vertical auquel ils appartiennent et comprennent différents segments, dimensions, mesures et visualisations, selon la suite de rapports sélectionnée.

Utilisez ces modèles prérenseignés tels quels ou adaptez-les en fonction de vos besoins (en ajoutant des mesures ou des visualisations, ou en les remplaçant, par exemple) et enregistrez-les sous un nouveau nom.

[Modèles standard dans Analysis Workspace sur YouTube](https://www.youtube.com/watch?v=aRgYwPneVXg&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&index=6) (2:46)

Voici les modèles disponibles et les questions auxquelles chaque modèle peut répondre.

* **Didacticiel** de formation : Ce modèle standard vous guide tout au long de la terminologie et des étapes courantes pour créer votre premier   dans Workspace. Il est disponible sous forme de modèle standard dans le modal Nouveau projet et remplace l’exemple de projet qui existe aujourd’hui pour les nouveaux utilisateurs qui n’ont pas d’autres projets dans leur liste.

### Publicité

>[!IMPORTANT]
>
>Les modèles Publicité sont accessibles uniquement si votre suite de rapports est activée pour Advertising Cloud.

* **Moteurs** de recherche payante : Ce modèle ventile les tendances publicitaires, les plateformes publicitaires, les mots-clés, les comptes, les campagnes, etc.

### Commerce

* **Magento : Marketing et commerce** : ce modèle ventile la conversion de votre commerce électronique en fonction de l’attribution du canal marketing et fournit des informations par mot-clé de recherche, page d’entrée, emplacement géographique, etc. Pour une présentation vidéo, voir >[!VIDEO](https://www.youtube.com/watch?v=AQOViVLEMHw)

### Média

* **Consommation audio** : quel contenu est le plus consommé et attire le plus d’utilisateurs ?
* **Récence, fréquence, fidélité** : qui sont mes fidèles lecteurs ?

### Mobile

>[!IMPORTANT]
>
>Les modèles mobiles sont accessibles uniquement si votre suite de rapports est activée pour Mobile.

* **Message :** est axé sur les performances de la messagerie in-app et push.
* **Emplacement :** comprend une carte représentant les données de positionnement.
* **Mesures clés :** sachez de quelle façon se comportent les mesures clés de votre application.
* **Utilisation de l’application :** combien d’utilisateurs, de lancements et de premiers lancements de l’application avait l’application et quelle est la durée de session moyenne ?
* **Acquisition :** contrôlez les performances des liens d’acquisition mobile.
* **Performances :** quelles sont les performances de l’application et où les utilisateurs rencontrent-ils des problèmes ?
* **Rétention :** qui sont mes fidèles utilisateurs et que font-ils ?
* **Parcours :** quels sont les schémas d’utilisation dominants de mon application ?

### Vente au détail

* **Performances de la campagne :** quelles campagnes génèrent le plus de recettes ?
* **Produits :** quels produits sont les plus performants ?

### Web

* **Acquisition :** quels sont les principaux facteurs orientant le trafic vers mon site web ?
* **Consommation de contenu :** où se rendent surtout les personnes sur mon site ?
* **Rétention :** quels types d’utilisateurs seront a priori les plus fidèles à mon site ?
* **Technologie :** quelle technologie utilisent les visiteurs de mon site ?

### Personnes

> [!NOTE] Le modèle Personnes et la mesure Personnes associée peuvent être utilisés uniquement dans le cadre d’[Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-people.html).

Ce modèle est basé sur la mesure Personnes, qui est une version dédupliquée de la mesure uniques. La mesure Personnes permet d’évaluer à quelle fréquence les internautes utilisent différents appareils pour interagir avec votre marque. Le modèle permet d’accomplir ce qui suit :

* Segmenter vos données pour les États-Unis/le Canada et le reste du monde. Device Co-op est actuellement uniquement disponible aux États-Unis.
* Comparer côte à côte les mesures Personnes et Visiteurs uniques.
* Afficher le « taux de compression », une mesure calculée qui détermine à quel point le résultat de la mesure Personnes, en pourcentage, est plus petit que celui de la mesure Visiteurs uniques.
* Comparer les nombres totaux de types de périphériques utilisés par vos clients.
* Afficher le nombre moyen de périphériques utilisés par personne.
* Découvrir comment utiliser l’empilement des segments avec la mesure Personnes.
* Découvrir comment l’utilisation d’Experience Cloud ID dans votre environnement améliore l’efficacité de la mesure Personnes.

### Journey IQ : Modèle Analytics sur plusieurs périphériques

<!-->This content is mirrored in the CDA doc.<-->

Ce modèle vous permet d’afficher des données de performances interpériphériques essentielles. Il est disponible uniquement pour les clients qui ont accès à Analytics [](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) multipériphériques (CDA).

* **Note spéciale à l&#39;intention des membres du Graphique** coopératif : Indique la partie de votre suite de rapports qui contient des dans les régions où le graphique coopératif est pris en charge et les régions où il n’est pas pris en charge.
* **Identification des utilisateurs**: Indique la fréquence à laquelle les de votre site sont identifiés à l’aide de méthodes basées sur les analyses multipériphériques.
* **Mesure  taille** du : Affiche une comparaison entre &quot;Dispositifs uniques&quot; et &quot;Personnes&quot;. La proportion de ces deux nombres est connue sous le nom de &quot;compression inter-périphériques&quot;, une mesure calculée visible dans ce panneau. Cette mesure de compression dépend d’un large éventail de facteurs :
   * **Utilisation du graphique coopératif ou du graphique** privé : En général, les organisations qui utilisent la coopérative de l&#39;appareil ont tendance à voir de meilleurs taux de compression que les organisations qui utilisent le graphique privé.
   * **Taux** de connexion : Plus les utilisateurs se connectent sur votre site, plus Adobe peut identifier et assembler des sur plusieurs périphériques. Les sites qui présentent un faible taux de connexion ont aussi de faibles taux de compression.
   * **Couverture** d’ID Experience Cloud : Seuls les avec un ECID peuvent être assemblés. Un pourcentage plus faible de visiteurs qui accèdent à votre site en utilisant un ECID correspond à des taux de compression plus faibles.
   * **Utilisation** de plusieurs périphériques : Si les de votre site n’utilisent pas plusieurs périphériques, les taux de compression sont plus faibles.
   * **de granularité** du : La compression par jour est généralement plus petite que la compression par mois ou par année. Les chances qu’une personne utilise plusieurs appareils sont moindres au cours d’un seul jour qu’au cours d’un mois entier. La segmentation, le filtrage ou l’utilisation de dimensions de ventilation peuvent également indiquer un taux de compression plus faible.
* **Segments** basés sur les personnes : Contient une liste déroulante de segments qui vous permet de  données spécifiques au périphérique. Ce panneau encourage l’expérimentation de segments afin de voir comment l’inclusion ou l’exclusion des types de périphériques affectent les rapports.
* **Analyse du parcours** inter-périphériques : Fournit des rapports de flux et d’abandons en fonction du type de périphérique.
* **Attribution** sur plusieurs périphériques : Combinez les caractéristiques de Journey IQ et d’Attribution IQ.
* **Autres conseils et astuces**: Rubriques utiles sur l&#39;ADC qui vous permettent de mieux l&#39;utiliser.