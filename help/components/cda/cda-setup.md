---
title: Configuration des analyses entre appareils
description: Découvrez comment configurer Analytics sur plusieurs périphériques une fois que vous avez satisfait aux conditions préalables.
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# Configuration des analyses entre appareils

> [!NOTE] La documentation d’Analytics sur plusieurs périphériques peut être modifiée au fur et à mesure que la fonctionnalité est développée. Consultez régulièrement les mises à jour.

Une fois toutes les conditions préalables remplies, procédez comme suit pour activer Analytics sur plusieurs périphériques. Vous devez appartenir à un groupe d’administrateurs de profil de produit ou disposer de droits d’administrateur dans Adobe Analytics pour suivre ces étapes.

> [!IMPORTANT] Toutes les conditions préalables doivent être remplies avant de suivre ces étapes. Si toutes les conditions préalables ne sont pas remplies, la fonction n’est pas disponible ou ne fonctionne pas. Pour connaître les conditions préalables et les limites, reportez-vous à la section Analyses [](cda-home.md) sur plusieurs périphériques.

## Choisissez la suite de rapports multipériphériques qui sera activée pour CDA

When your organization is provisioned to use CDA, you choose which report suite to use. Ce choix peut être communiqué par l’intermédiaire de votre gestionnaire de compte Adobe. Adobe then enables your chosen report suite for CDA processing.

## Create a cross-device virtual report suite to see the cross-device view

Administrators with access to create virtual report suites can create CDA virtual report suites as follows:

1. Navigate to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) and log in using your AdobeID credentials.
2. Cliquez sur l’icône de la grille 9 en haut, puis sur Analytics.
3. Passez la souris sur Composants en haut, puis cliquez sur Suites de rapports virtuelles.
4. Cliquez sur Ajouter.
5. Entrez un nom pour votre suite de rapports virtuelle et assurez-vous que la suite de rapports CDA est sélectionnée.
6. Click the checkbox 'Enable Report Time Processing', which enables several more options including Cross-Device Analytics.
7. Cochez la case "Effectuer des visites de l’utilisateur sur plusieurs périphériques".
8. Cliquez sur Continuer, terminez la configuration de la suite de rapports virtuelle, puis cliquez sur Enregistrer.

![Case à cocher CDA](assets/cda-checkbox.png)

## Ajouts et modifications aux suites de rapports virtuelles sur plusieurs périphériques

Si Analytics sur plusieurs périphériques est activé sur une suite de rapports virtuelle, notez les modifications suivantes :

* A new cross-device icon appears next to the virtual report suite name. This icon is exclusive to cross-device virtual report suites.
* De nouvelles mesures intitulées "Personnes" et "Périphériques uniques" sont disponibles.
* La mesure Visiteurs uniques n’est pas disponible, car elle est remplacée par Personnes et Dispositifs uniques.
* Lors de la création de segments, le conteneur de segments Visiteur est remplacé par un conteneur Personne.

## Mesure calculée Compression

La possibilité pour Analytics sur plusieurs périphériques de réunir les périphériques dépend d’un large éventail de facteurs. The effectiveness of the feature's ability to stitch data can be measured with a calculated metric called compression. Factors that contribute to compression include:

* Utilisation du graphique Co-op ou du graphique Privé : En général, les organisations qui utilisent la coopérative de l'appareil ont tendance à voir de meilleurs taux de compression que les organisations qui utilisent le graphique privé.
* Taux de connexion : Plus les utilisateurs se connectent sur votre site, plus Adobe est en mesure d’identifier et de rassembler les visiteurs sur plusieurs périphériques. Sites with a low log in rate also have low compression rates.
* Experience Cloud ID coverage: Only visitors with an ECID can be stitched. A lower percentage of visitors to your site using an ECID correlates to lower compression rates.
* Multiple device usage: If visitors to your site don't use multiple devices, you can see lower compression rates.
* Reporting granularity: Compression by day is typically smaller than compression by month or year. Les chances qu’une personne utilise plusieurs périphériques sont moindres en un seul jour que pendant tout un mois. La segmentation, le filtrage ou l’utilisation de dimensions de ventilation peuvent également indiquer un taux de compression plus faible.

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
9. Facultatif : L’espace de travail charge la dimension Jour par défaut. Drag an alternate date dimension, such as week or month, on top of the Day dimension if a different time granularity is desired.
