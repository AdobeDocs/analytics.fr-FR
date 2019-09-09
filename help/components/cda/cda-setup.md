---
title: Définition - Analytics sur plusieurs périphériques
description: Découvrez comment configurer Analytics sur plusieurs périphériques après avoir satisfait aux conditions préalables.
translation-type: tm+mt
source-git-commit: 1ab4c27d6635167be475b6669ff6ed1913adc455

---


# Définition - Analytics sur plusieurs périphériques

> [!IMPORTANT] Toutes les conditions préalables doivent être remplies avant de suivre ces étapes. Si toutes les conditions préalables ne sont pas remplies, la fonction n'est pas disponible ou ne fonctionne pas. Pour [plus d'informations sur les conditions préalables et les limites, reportez-vous à la](cda-home.md) section Analyses inter-périphériques.

Une fois toutes les conditions préalables satisfaites, suivez les étapes ci-après pour activer les analyses inter-périphériques. Vous devez appartenir à un groupe d'administrateurs de profil de produit ou disposer des droits d'administrateur dans Adobe Analytics pour suivre ces étapes.

## Choisir la suite de rapports sur plusieurs périphériques qui sera activée pour CDA

Lorsque votre organisation est configurée pour utiliser CDA, vous choisissez la suite de rapports à utiliser. Ce choix peut être communiqué via votre gestionnaire de compte Adobe. Adobe active ensuite la suite de rapports choisie pour le traitement CDA.

## Création d'une suite de rapports virtuelle sur plusieurs périphériques pour afficher la vue sur plusieurs périphériques

Les administrateurs ayant accès à la création de suites de rapports virtuelles peuvent créer des suites de rapports virtuelles CDA comme suit :

1. Accédez à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) et connectez-vous à l'aide de vos informations d'identification adobeid.
2. Cliquez sur l'icône en 9 grille dans la partie supérieure, puis cliquez sur Analytics.
3. Passez la souris sur Composants en haut, puis cliquez sur Suites de rapports virtuelles.
4. Cliquez sur Ajouter.
5. Saisissez un nom pour votre suite de rapports virtuelle et assurez-vous que la suite de rapports activée pour CDA est sélectionnée.
6. Cochez la case Activer le traitement du temps de rapport, qui active plusieurs autres options, y compris les analyses inter-périphériques.
7. Cochez la case « Visites de l'utilisateur sur plusieurs périphériques ».
8. Cliquez sur Continuer, terminez la configuration de la suite de rapports virtuelle, puis cliquez sur Enregistrer.

![Case à cocher CDA](assets/cda-checkbox.png)

## Ajouts et modifications des suites de rapports virtuelles sur plusieurs périphériques

Lorsque l'option Analyses croisées est activée sur une suite de rapports virtuelle, tenez compte des modifications suivantes :

* Une nouvelle icône sur plusieurs périphériques apparaît en regard du nom de la suite de rapports virtuelle. Cette icône est exclusive aux suites de rapports virtuelles inter-périphériques.
* De nouvelles mesures intitulées « Personnes » et « Périphériques uniques » sont disponibles.
* La mesure Visiteurs uniques n'est pas disponible, car elle est remplacée par des personnes et des périphériques uniques.
* Lors de la création de segments, le conteneur de segments du visiteur est remplacé par un conteneur Personne.

## Mesure calculée Compression

La possibilité de regrouper les périphériques sur plusieurs périphériques dépend d'un large éventail de facteurs. L'efficacité de la fonctionnalité de raccordement des données peut être mesurée avec une mesure calculée appelée compression. Les facteurs qui contribuent à la compression sont les suivants :

* Utilisation du graphique Co-op ou du graphique privé : En général, les organisations qui utilisent le périphérique co-op ont tendance à voir de meilleurs taux de compression que les organisations utilisant le graphique privé.
* Taux de connexion : Plus les utilisateurs se connectent sur votre site, plus Adobe peut identifier et réunir les visiteurs sur l'ensemble des périphériques. Les sites dont le taux de connexion est faible ont également un faible taux de compression.
* Couverture d'identifiant Experience Cloud : Seuls les visiteurs ayant un ECID peuvent être assemblés. Un pourcentage inférieur de visiteurs sur votre site utilisant un ID d'ECID est en corrélation avec des taux de compression plus faibles.
* Utilisation de plusieurs périphériques : Si les visiteurs de votre site n'utilisent pas de périphériques multiples, les taux de compression sont faibles.
* Granularité des rapports : La compression par jour est généralement plus petite que la compression par mois ou par année. La probabilité qu'une personne d'utiliser plusieurs périphériques soit plus petite qu'un mois entier. La segmentation, le filtrage ou l'utilisation des dimensions de ventilation peuvent également afficher un taux de compression plus faible.

Pour connaître la compression de votre entreprise pour une période donnée :

1. Cliquez sur Espace de travail en haut, puis sur Créer un projet.
2. Commencez par un projet vierge, puis cliquez sur Créer.
3. Faites glisser la mesure Périphériques uniques sur la zone de travail intitulée « Déposer une mesure ici ».
4. Faites glisser la mesure Personnes sur la trame directement à droite de l'en-tête de mesure Périphériques uniques, de sorte que les deux mesures soient côte à côte.
5. Cliquez sur le symbole « + » en regard des mesures disponibles sur la gauche pour ouvrir le créateur de mesures calculées.
6. Attribuez à cette mesure calculée les paramètres suivants :
   * Nom : Compression entre plusieurs périphériques
   * Format : Pourcentage
   * Nombre de décimales : 2
   * Définition: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!NOTE] Cliquez sur Ajouter dans le coin supérieur droit de la zone de définition pour ajouter un numéro statique. Faites glisser les personnes et les périphériques uniques à partir de la liste des mesures disponibles à gauche.
7. Cliquez sur Enregistrer.
8. Faites glisser la nouvelle mesure calculée sur la trame directement à droite de l'en-tête de mesure Personnes, de sorte que les trois mesures soient côte à côte.
9. Facultatif : L'espace de travail charge la dimension Jour par défaut. Faites glisser une autre dimension de date, telle que semaine ou mois, sur la dimension Jour si une granularité temporelle différente est souhaitée.
