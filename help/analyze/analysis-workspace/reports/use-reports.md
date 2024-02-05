---
description: Vue d’ensemble de l’utilisation des rapports par défaut dans Analysis Workspace.
title: Utiliser les rapports
feature: Analysis Workspace
role: User, Admin
exl-id: 0d43fa5e-9167-4af7-891d-e49b0249bca2
source-git-commit: dcc517c2cd24a1aeeb2594094d09b9187ea7d144
workflow-type: ht
source-wordcount: '1516'
ht-degree: 100%

---

# Utiliser les rapports préconfigurés

Les rapports préconfigurés dans Analysis Workspace fournissent des aperçus rapides sur les scénarios de création de rapports les plus courants. Voici quelques exemples de questions auxquelles vous pouvez répondre à l’aide de rapports préconfigurés :

* Nombre de visiteurs sur votre site
* Nombre de ces visiteurs qui sont uniques (comptabilisés une seule fois)
* Leur acheminement vers le site (s’ils ont suivi un lien ou se sont rendus directement dessus)
* Mots-clés utilisés par les visiteurs pour rechercher le contenu du site
* Leur durée passée sur une page donnée ou sur le site entier
* Liens sur lesquels les visiteurs ont cliqué et le moment où ils ont quitté le site
* Les canaux marketing les plus efficaces pour générer des recettes ou des événements de conversion
* Le temps passé à regarder une vidéo
* Les navigateurs et appareils utilisés pour consulter votre site

Les informations suivantes décrivent comment accéder aux rapports préconfigurés à partir de l’onglet [!UICONTROL Rapports] dans Analysis Workspace.

## Accéder à un rapport et l’exécuter

1. Dans Analysis Workspace, sélectionnez l’onglet [!UICONTROL **Workspace**].

1. Sélectionnez [!UICONTROL **Rapports**].

   ![Onglet Rapports.](assets/view-prebuilt-reports.png)

1. Dans le champ de recherche, commencez à saisir le nom du rapport à rechercher, puis sélectionnez-le dans la liste des rapports. Vous pouvez également filtrer la liste de rapports par propriété, eVar et numéro d’événement. <!-- still true? -->

   Ou

   Sélectionnez la catégorie de rapport à afficher, puis le rapport dans la liste des rapports.

   >[!TIP]
   >
   >   Pour naviguer dans le menu à l’aide des touches fléchées, appuyez sur la touche Barre oblique (/), puis sur la touche Flèche vers le bas. Appuyez sur Entrée pour charger le rapport sélectionné.

Pour obtenir la liste des rapports disponibles, reportez-vous à la section [Rapports disponibles](#available-reports) ci-dessous.

## Enregistrer un rapport {#use-reports}

Si vous quittez un rapport après avoir apporté des modifications, nous vous demandons d’enregistrer ou d’ignorer vos modifications. L’enregistrement des modifications dans un rapport enregistre le rapport en tant que nouveau projet.

1. Accédez à l’onglet [!UICONTROL **Rapports**].
1. Sélectionnez le rapport à afficher. Par exemple, sous [!UICONTROL **Les plus populaires**], sélectionnez le rapport [!UICONTROL **Pages**].

   ![Rapport Pages](assets/pages-report.png)

1. Le rapport Pages, comme affiché dans Analysis Workspace, affiche deux [visualisations](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([Graphique à barres](/help/analyze/analysis-workspace/visualizations/bar.md) et [Numéro de la synthèse](/help/analyze/analysis-workspace/visualizations/summary-number-change.md)) ainsi qu’un [Tableau à structure libre](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md). La mesure utilisée est Occurrences.
1. Effectuez l’une des opérations suivantes :

   * Affichez le rapport.
   * Faites glisser un ou plusieurs segments dans la zone de dépôt de segments située en haut. Par exemple, faites glisser le segment [!UICONTROL **Clients mobiles**] et observez les résultats.
   * Modifiez la période en accédant au calendrier en haut à droite.
   * Ajoutez des répartitions de dimension, faites glisser d’autres mesures et personnalisez généralement le rapport selon vos besoins.

1. (Facultatif) Enregistrez le rapport en tant que projet en sélectionnant [!UICONTROL **Projet**] > [!UICONTROL **Enregistrer**].

   Le rapport est enregistré comme nouveau projet. Le rapport existant n’est pas modifié. Pour plus d’informations sur l’enregistrement d’un rapport en tant que projet, voir [Enregistrer des projets](/help/analyze/analysis-workspace/build-workspace-project/save-projects.md).

## Rapports disponibles

Le tableau suivant contient la liste complète des rapports préconfigurés disponibles.

Voici quelques-uns des rapports prédéfinis les plus populaires : Flux, Abandons, Canal marketing et Rapports en temps réel.

| Élément de menu | Rapports relevant de cet élément de menu |
| --- | --- |
| **[!UICONTROL Plus populaires]** | <ul><li>Tutoriel de formation (modèle d’espace de travail préexistant)</li><li>Pages (quelles sont mes pages les plus vues ?)</li><li>Vues de page (combien de vues de pages est-ce que je génère ?)</li><li>Visites (combien de visites est-ce que jʼobtiens ?)</li><li>Visiteurs (combien de visiteurs est-ce que jʼai ?)</li><li>Mesures clés (comment se portent mes mesures les plus importantes ?)</li><li>Sections du site (quelles sections de mon site ont généré le plus de vues de page ?)</li><li>Temps réel (quelles sont les tendances sur mon site et pourquoi ?)</li><li>Page suivante (quelles sont les pages suivantes consultées par mes visiteurs ?)</li><li>Page précédente (quelles sont les pages précédentes consultées par mes visiteurs ?)</li><li>Campagnes (quelles campagnes génèrent mes mesures clés ?)</li><li>Produits (quels produits génèrent mes mesures clés ?)</li><li>Canal Dernière touche (quel canal Dernière touche est le plus performant ?)</li><li>Détails du canal Dernière touche (quel canal Dernière touche spécifique est plus performant que les autres ?)</li><li>Chiffre dʼaffaires (comment se porte mon chiffre dʼaffaires ?)</li><li>Commandes (comment se portent mes commandes ?)</li><li>Unités (combien dʼunités est-ce que je vends ?)</li></ul> |
| **[!UICONTROL Engagement]** | <ul><li>Mesures clés (comment se portent mes mesures les plus importantes ?)</li><li>Vues de page (combien de vues de pages est-ce que je génère ?)</li><li>Pages (quelles sont mes pages les plus vues ?)</li><li>Visites (combien de visites est-ce que jʼobtiens ?)</li><li>Visiteurs (combien de visiteurs est-ce que jʼai ?)</li><li>Durée de la visite (combien de temps mes utilisateurs passent-ils par visite ?)</li><li>Durée avant événement (combien de temps mes utilisateurs passent-ils avant un événement de succès ?)</li><li>Sections du site (quelles sections de mon site ont généré le plus de vues de page ?)</li><li>Consommation de contenu web (quel contenu est le plus consommé et attire le plus dʼutilisateurs ?)</li><li>Consommation de contenu multimédia (quel contenu est le plus consommé et attire le plus dʼutilisateurs ?)</li><li>Flux de pages suivantes et précédentes (quels sont/étaient les chemins suivants/précédents empruntés par mes visiteurs ?)</li><li>Abandon (où puis-je voir lʼabandon dans mes propriétés numériques ?)</li><li>Analyse entre appareils (utilisation de lʼanalyse entre appareils dans Analysis Workspace)</li><li>Rétention web (qui sont mes utilisateurs fidèles et que font-ils ?)</li><li>Consommation de médias audio (quelles sont les tendances et les principales mesures de la consommation audio ?)</li><li>Récence de médias, fréquence, fidélité (qui sont mes lecteurs fidèles ?)</li><li>Analyse de page > Actualisations (quelles sont les pages les plus actualisées ?)</li><li>Analyse de page > Durée de consultation de page (combien de temps les utilisateurs passent-ils sur mes pages ?)</li><li>Entrées et sorties > Pages dʼaccès (quelles sont mes principales pages dʼaccès ?)</li><li>Entrées et sorties > Pages dʼaccès dʼorigine (à partir de quelle page mon visiteur est-il entré ?)</li><li>Entrées et sorties > Visites sur une seule page (quelles pages ont généré le plus de visites sur une seule page ?)</li><li>Entrées et sorties > Pages de sortie (quelles sont mes principales pages de sortie ?)</li></ul> |
| **[!UICONTROL Conversion]** | <ul><li>Produits > Produits (quels produits génèrent mes mesures clés ?)</li><li>Produits > Performances des produits (quels sont les produits qui ont les meilleures performances ?)</li><li>Produits > Catégories (quelles sont mes catégories de produits qui ont les meilleures performances ?)</li><li>Panier > Paniers (combien dʼutilisateurs ont ajouté un produit au panier ?)</li><li>Panier > Consultations du panier (combien de fois mes visiteurs ont-ils consulté leur panier ?)</li><li>Panier > Ajouts au panier (à quelle fréquence les utilisateurs ajoutent-ils un produit à leur panier ?)</li><li>Panier > Retraits du panier (à quelle fréquence les utilisateurs suppriment-ils un produit de leur panier ?)</li><li>Achats > Chiffre dʼaffaires (comment mon chiffre dʼaffaires se porte-t-il ?)</li><li>Achats > Commandes (comment mes commandes se portent-elles ?)</li><li>Achats > Unités (combien dʼunités est-ce que je vends ?)</li><li>[Magento : marketing et commerce](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr#commerce)</li></ul> |
| **[!UICONTROL Audience]** | <ul><li>Mesure relative aux personnes (combien de personnes interagissent avec ma marque ?)</li><li>Profil du visiteur > Aperçu de lʼemplacement (quels sont les emplacements qui génèrent le plus dʼutilisation parmi les utilisateurs ?)</li><li>Profil du visiteur > Segmentation géographique > Départements, états américains, régions, villes, DMA États-Unis (dʼoù mes utilisateurs viennent-ils ?)</li><li>Profil du visiteur > Langues (quelle langue mes utilisateurs préfèrent-ils ?)</li><li>Profil du visiteur > Fuseaux horaires (quels sont les fuseaux horaires de mes visiteurs ?)</li><li>Profil du visiteur > Domaines (quels FAI mes visiteurs utilisent-ils pour accéder à mon site ?)</li><li>Profil du visiteur > Domaines de niveau supérieur (quels domaines génèrent du trafic sur mon site ?)</li><li>Profil du visiteur > Technologie > Aperçu des technologies (quelles technologies mes visiteurs utilisent-ils pour accéder à mon site ?)</li><li>Profil du visiteur > Technologie > Navigateurs, type de navigateur, largeur du navigateur, hauteur du navigateur (quelles sont lʼentreprise propriétaire, la version, la largeur et la hauteur du navigateur utilisé par les personnes qui accèdent à mon site ?)</li><li>Profil du visiteur > Technologie > Système dʼexploitation, types de systèmes dʼexploitation (quel système dʼexploitation et quelle version les visiteurs utilisent-ils ?)</li><li>Profil du visiteur > Technologie > Opérateur de téléphonie mobile (quels opérateurs de téléphonie mobile les visiteurs utilisent-ils pour accéder à mon site ?)</li><li>Rétention des visiteurs > Fréquence des retours (combien de temps sʼécoule-t-il entre la visite actuelle de mon utilisateur et ses visites précédentes ?)</li><li>Rétention des visiteurs > Visites récurrentes (combien de mes visites concernent des utilisateurs ayant précédemment accédé à mon site ?)</li><li>Rétention des visiteurs > Nombre de visites (quel nombre de visites génère-t-il la plupart de mes mesures clés ?)</li><li>Rétention des visiteurs > Cycle de vente > Fidélisation des clients (à quel segment de fidélité appartiennent mes utilisateurs ?)</li><li>Rétention des visiteurs > Cycle de vente > Jours avant le premier achat (combien de jours se sont écoulés entre la première visite de mes utilisateurs et leur premier achat ?)</li><li>Rétention des visiteurs > Cycle de vente > Jours depuis le dernier achat (combien de jours se sont écoulés entre la visite actuelle de mes utilisateurs et leur dernier achat ?) )</li><li>Rétention des visiteurs > Mobile > Appareils et types dʼappareils (quels appareils et types dʼappareils mes visiteurs utilisent-ils ?)</li><li>Rétention des visiteurs > Mobile > Fabricant (quel fabricant d’appareil mobile mes visiteurs utilisent-ils ?)</li><li>Rétention des visiteurs > Mobile > Taille dʼécran, hauteur dʼécran, largeur dʼécran (quelle est la taille, la hauteur et la largeur de lʼécran mobile de mes visiteurs ?)</li><li>Rétention des visiteurs > Mobile > [Utilisation des applications mobiles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr#mobile)</li><li>Rétention des visiteurs > Mobile > [Parcours sur les application mobiles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr#mobile)</li><li>Rétention des visiteurs > Mobile > [Mesures dʼapplications mobiles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr#mobile)</li><li>Rétention des visiteurs > Mobile > [Messages sur les applications mobiles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr#mobile)</li><li>Rétention des visiteurs > Mobile > [Performances des applications mobiles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr#mobile)</li><li>Rétention des visiteurs > Mobile > [Rétention des applications mobiles](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr#mobile)</li></ul> |
| **[!UICONTROL Acquisition]** | <ul><li>Canaux marketing > Canal Première touche, détails du canal Première touche (quel canal Première touche, et quel canal Première touche spécifique est le plus performant ?)</li><li>Canaux marketing > Canal Dernière touche, détails du canal Dernière touche (quel canal Dernière touche, et quel canal Dernière touche spécifique est le plus performant ?)</li><li>Campagnes > Campagnes (quelles campagnes génèrent mes mesures clés ?)</li><li>Campagnes > Performances de la campagne (quelles campagnes génèrent le plus de chiffre d’affaires ?)</li><li>Campagnes > Code de suivi (quels sont les codes de suivi de campagne les plus performants ?)</li><li>[Acquisition web](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr#web)</li><li>[Acquisition mobile](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr#mobile)</li><li>[Advertising Analytics : référencement payant](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html?lang=fr#advertising)</li><li>Mots-clés de recherche - tous, payants, naturels (quels mots-clés de recherche et mots-clés de référencement payant/naturel offrent les meilleures performances pour mes mesures clés ?)</li><li>Moteurs de recherche - tous, payants, naturels (quels sont les moteurs de recherche et les moteurs de référencement payant/naturel qui offrent les meilleures performances pour mes mesures clés ?)</li><li>Classement de toutes les pages de recherche (de quelle page de recherche mes utilisateurs proviennent-ils ?)</li><li>Domaines référents (quels domaines génèrent du trafic sur mon site ?)</li><li>Domaines référents d’origine (sur quel premier domaine les utilisateurs se trouvaient-ils avant de visiter mon site ?)</li><li>Référents (sur quelles URL mes visiteurs se trouvaient-ils avant de naviguer vers mon site ?)</li><li>Types de référents (à quelle catégorie mes URL de référence appartiennent-elles ?)</li></ul> |
