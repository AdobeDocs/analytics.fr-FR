---
title: Configuration des analyses entre appareils
description: Configurez une suite de rapports virtuelle pour activer les analyses entre appareils.
translation-type: ht
source-git-commit: 97e1c0ac5fbf7f932c3f772c33e7fa8880c653a6
workflow-type: ht
source-wordcount: '507'
ht-degree: 100%

---


# Configuration des analyses entre appareils

Une fois toutes les conditions préalables remplies, procédez comme suit pour activer les analyses entre appareils. Vous devez appartenir à un groupe d’administrateurs de profil de produit ou disposer de droits d’administrateur dans Adobe Analytics pour suivre cette procédure.

>[!IMPORTANT]
>
>Toutes les conditions préalables doivent être remplies avant de suivre cette procédure. Si toutes les conditions préalables ne sont pas remplies, la fonction n’est pas disponible ou ne fonctionne pas. Pour connaître les conditions préalables et les limites, consultez la [page d’aperçu](overview.md) et la méthode de regroupement souhaitée ([Regroupement basé sur les champs](field-based-stitching.md) ou [Graphique d’appareil](device-graph.md), respectivement).

## Contactez votre Customer Success Manager pour que les analyses entre appareils soient configurées sur votre suite de rapports contenant des données de plusieurs appareils.

Les analyses entre appareils sont configurées sur votre suite de rapports contenant des données de plusieurs appareils par les ingénieurs d’Adobe. Contactez votre Customer Success Manager avec les informations suivantes :

* Votre identifiant d’organisation Adobe Experience Cloud (chaîne alphanumérique se terminant par @AdobeOrg)
* L’identifiant de la suite de rapports contenant des données de plusieurs appareils à laquelle vous souhaitez appliquer l’analyse entre appareils
* La méthode d’analyses entre appareils que vous souhaitez utiliser (groupement basé sur les champs, Adobe Private Graph ou Adobe Co-Op Graph)
* Si vous envisagez d’utiliser le groupement basé sur les champs, la prop ou l’eVar qui contient l’identifiant utilisateur
* Votre préférence en matière de fréquence de relecture et de durée de période de recherche arrière. Les options incluent une relecture une fois par semaine avec une période de recherche arrière de 7 jours ou une relecture chaque jour avec une période de recherche arrière de 1 jour.

Une fois que vous avez fourni ces informations à votre Customer Success Manager, ce dernier collabore avec les ingénieurs d’Adobe pour intégrer le traitement des analyses entre appareils à la suite de rapports choisie.

## Créer une suite de rapports virtuelle sur plusieurs appareils pour afficher la vue sur plusieurs appareils

Les administrateurs ayant accès à la création de suites de rapports virtuelles peuvent créer des suites de rapports virtuelles des analyses entre appareils comme suit :

1. Accédez à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) et connectez-vous à l’aide de vos identifiants Adobe ID.
2. Cliquez sur l’icône à neuf grilles en haut de l’écran, puis sur Analytics.
3. Passez la souris sur Composants en haut de l’écran, puis cliquez sur Suites de rapports virtuelles.
4. Cliquez sur Ajouter.
5. Saisissez le nom de votre suite de rapports virtuelle et assurez-vous que la suite de rapports compatible avec les analyses entre appareils est sélectionnée.
6. (Facultatif) Appliquez un segment à la suite de rapports virtuelle. Par exemple, vous pouvez appliquer un segment qui limite la suite de rapports virtuelle aux dates suivant l’activation des analyses entre appareils et le début du regroupement. Ce segment permet aux utilisateurs de voir uniquement les plages de dates regroupées dans la suite de rapports virtuelle.
7. Cochez la case « Activer le report de traitement du temps », qui active plusieurs autres options, notamment Analyses entre appareils.
8. Cochez la case « Visites des utilisateurs agrafés selon les appareils ».
9. Cliquez sur Continuer, terminez la configuration de la suite de rapports virtuelle, puis cliquez sur Enregistrer.

![Case à cocher Analyses entre appareils](assets/cda-checkbox.png)

## Ajouts et modifications apportés aux suites de rapports virtuelles sur plusieurs appareils

Lorsque les analyses entre appareils sont activées sur une suite de rapports virtuelle, notez les modifications suivantes :

* Une nouvelle icône interpériphérique apparaît en regard du nom de la suite de rapports virtuelle. Cette icône est réservée aux suites de rapports virtuelles sur plusieurs appareils.
* Une nouvelle dimension intitulée [État identifié](../dimensions/identified-state.md) est disponible. Cette dimension détermine si l’Experience Cloud ID sur cet accès est connu par le graphique de l’appareil à ce moment.
* De nouvelles mesures intitulées [Personnes](../metrics/people.md) et [Appareils uniques](../metrics/unique-devices.md) sont disponibles.
* La mesure [Visiteurs uniques](../metrics/unique-visitors.md) n’est pas disponible, car elle est remplacée par « Personnes » et « Appareils uniques ».
* Lors de la création de segments, le conteneur de segments « Visiteur » est remplacé par un conteneur « Personne ».
