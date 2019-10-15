---
title: Configuration des analyses entre appareils
description: Découvrez comment configurer Analytics sur plusieurs périphériques une fois que vous avez satisfait aux conditions préalables.
translation-type: tm+mt
source-git-commit: 8c5e8d18ce4e09049d3fea07b8dd75ded6894313

---


# Configuration des analyses entre appareils

> [!NOTE] La documentation d’Analytics sur plusieurs périphériques peut être modifiée au fur et à mesure que la fonctionnalité est développée. Consultez régulièrement les mises à jour.

Une fois toutes les conditions préalables remplies, procédez comme suit pour activer Analytics sur plusieurs périphériques. Vous devez appartenir à un groupe d’administrateurs de profil de produit ou disposer de droits d’administrateur dans Adobe Analytics pour suivre ces étapes.

> [!IMPORTANT] Toutes les conditions préalables doivent être remplies avant de suivre ces étapes. Si toutes les conditions préalables ne sont pas remplies, la fonction n’est pas disponible ou ne fonctionne pas. Pour connaître les conditions préalables et les limites, reportez-vous à la section Analyses [](cda-home.md) sur plusieurs périphériques.

## Choisissez la suite de rapports multipériphériques qui sera activée pour CDA

Lorsque votre organisation est configurée pour utiliser CDA, vous choisissez la suite de rapports à utiliser. Ce choix peut être communiqué par l’intermédiaire de votre gestionnaire de compte Adobe. Adobe active ensuite la suite de rapports choisie pour le traitement CDA.

## Création d’une suite de rapports virtuelle sur plusieurs périphériques pour afficher l’affichage sur plusieurs périphériques

Les administrateurs ayant accès à la création de suites de rapports virtuelles peuvent créer des suites de rapports virtuelles CDA comme suit :

1. Accédez à [experience.adobe.com](https://experiencecloud.adobe.com) et connectez-vous à l’aide de vos identifiants AdobeID.
2. Cliquez sur l’icône de la grille 9 en haut, puis sur Analytics.
3. Passez la souris sur Composants en haut, puis cliquez sur Suites de rapports virtuelles.
4. Cliquez sur Ajouter.
5. Entrez un nom pour votre suite de rapports virtuelle et assurez-vous que la suite de rapports CDA est sélectionnée.
6. (Facultatif) Appliquez un segment à la suite de rapports virtuelle. Par exemple, vous pouvez appliquer un segment qui limite la suite de rapports virtuelle aux dates après l’activation de l’outil de collecte de données et le début de l’assemblage. Ce segment permet aux utilisateurs de voir uniquement les plages de dates cousues dans la suite de rapports virtuelle.
7. Cochez la case "Activer le traitement du temps des rapports", qui active plusieurs autres options, notamment Analyses sur plusieurs périphériques.
8. Cochez la case "Effectuer des visites de l’utilisateur sur plusieurs périphériques".
9. Cliquez sur Continuer, terminez la configuration de la suite de rapports virtuelle, puis cliquez sur Enregistrer.

![Case à cocher CDA](assets/cda-checkbox.png)

## Ajouts et modifications aux suites de rapports virtuelles sur plusieurs périphériques

Si Analytics sur plusieurs périphériques est activé sur une suite de rapports virtuelle, notez les modifications suivantes :

* Une nouvelle icône inter-périphériques apparaît en regard du nom de la suite de rapports virtuelle. Cette icône est réservée aux suites de rapports virtuelles sur plusieurs périphériques.
* De nouvelles mesures intitulées "Personnes" et "Périphériques uniques" sont disponibles.
* La mesure Visiteurs uniques n’est pas disponible, car elle est remplacée par Personnes et Dispositifs uniques.
* Lors de la création de segments, le conteneur de segments Visiteur est remplacé par un conteneur Personne.

## Mesure calculée Compression

La possibilité pour Analytics sur plusieurs périphériques de réunir les périphériques dépend d’un large éventail de facteurs. L’efficacité de la capacité de la fonction à assembler des données peut être mesurée à l’aide d’une mesure calculée appelée compression. Les facteurs qui contribuent à la compression incluent :

* Utilisation du graphique Co-op ou du graphique Privé : En général, les organisations qui utilisent la coopérative de l'appareil ont tendance à voir de meilleurs taux de compression que les organisations qui utilisent le graphique privé.
* Taux de connexion : Plus les utilisateurs se connectent sur votre site, plus Adobe est en mesure d’identifier et de rassembler les visiteurs sur plusieurs périphériques. Les sites avec un faible taux de connexion ont aussi de faibles taux de compression.
* Couverture d’ID Experience Cloud : Seuls les visiteurs avec un ECID peuvent être assemblés. Un pourcentage plus faible de visiteurs de votre site utilisant un ECID correspond à des taux de compression plus faibles.
* Utilisation de plusieurs périphériques : Si les visiteurs de votre site n’utilisent pas plusieurs périphériques, les taux de compression sont plus faibles.
* Granularité des rapports : La compression par jour est généralement plus petite que la compression par mois ou par année. Les chances qu’une personne utilise plusieurs périphériques sont moindres en un seul jour que pendant tout un mois. La segmentation, le filtrage ou l’utilisation de dimensions de ventilation peuvent également indiquer un taux de compression plus faible.

Pour afficher la compression de votre entreprise pour une période donnée :

1. Cliquez sur Espace de travail dans la partie supérieure, puis sur Créer un projet.
2. Commencez par un projet vierge, puis cliquez sur Créer.
3. Faites glisser la mesure Périphériques uniques sur la zone de travail intitulée "Déposer une mesure ici".
4. Faites glisser la mesure Personnes sur le canevas directement à droite de l’en-tête de mesure Périphériques uniques. Les deux mesures sont donc côte à côte.
5. Cliquez sur le symbole "`+`" en regard des mesures disponibles sur la gauche pour ouvrir le créateur de mesures calculées.
6. Attribuez à cette mesure calculée les paramètres suivants :
   * Nom : Compression sur plusieurs périphériques
   * Format : Pourcentage
   * Nombre de décimales : 2
   * Définition: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!TIP] Cliquez sur Ajouter dans le coin supérieur droit de la zone de définition pour ajouter un nombre statique. Faites glisser Personnes et Dispositifs uniques dans la liste des mesures disponibles à gauche.
7. Cliquez sur Enregistrer.
8. Faites glisser la nouvelle mesure calculée sur le canevas directement à droite de l’en-tête de mesure Personnes, de sorte que les trois mesures soient côte à côte.
9. Facultatif : L’espace de travail charge la dimension Jour par défaut. Faites glisser une autre dimension de date (semaine ou mois, par exemple) au-dessus de la dimension Jour si vous souhaitez une granularité temporelle différente.
