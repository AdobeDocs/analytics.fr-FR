---
title: Configuration des analyses entre appareils
description: Configurez une suite de rapports virtuelle pour activer les analyses entre appareils.
translation-type: tm+mt
source-git-commit: da4f4d843e02865c006df2190d19a85306dbf2d0
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 68%

---


# Configuration des analyses entre appareils

Une fois toutes les conditions préalables remplies, procédez comme suit pour activer les analyses entre appareils. Vous devez appartenir à un groupe d’administrateurs de profil de produit ou disposer de droits d’administrateur dans Adobe Analytics pour suivre cette procédure.

>[!IMPORTANT]
>
>Toutes les conditions préalables doivent être remplies avant de suivre cette procédure. Si toutes les conditions préalables ne sont pas remplies, la fonction n’est pas disponible ou ne fonctionne pas. Pour connaître les conditions préalables et les limites, consultez la [page d’aperçu](overview.md) et la méthode de regroupement souhaitée ([Regroupement basé sur les champs](field-based-stitching.md) ou [Graphique d’appareil](device-graph.md), respectivement).

## Contactez votre gestionnaire de succès client pour que l’ACD soit configuré sur votre suite de rapports sur plusieurs périphériques.

L’ADC est configuré sur votre suite de rapports sur plusieurs périphériques par ingénierie d’Adobe. Contactez votre responsable de succès client avec les informations suivantes :

* Votre identifiant d’organisation Adobe Experience Cloud (chaîne alphanumérique se terminant par @AdobeOrg)
* Identifiant de la suite de rapports pour la suite de rapports sur plusieurs périphériques que vous souhaitez activer avec CDA
* Quelle méthode d&#39;ADC utiliser (assemblage sur le terrain, graphique privé d&#39;Adobe ou graphique de coopération d&#39;Adobe)
* Si vous envisagez d’utiliser l’assemblage basé sur des champs, la prop ou l’eVar qui contient l’ID utilisateur

Une fois que vous avez fourni ces informations à votre CSM, il travaille avec l&#39;ingénierie d&#39;Adobe pour activer la suite de rapports choisie pour le traitement de l&#39;ACD.

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
* Une nouvelle dimension nommée [état identifié](../dimensions/identified-state.md) est disponible. Cette dimension détermine si l’Experience Cloud ID sur cet accès est connu par le graphique de l’appareil à ce moment.
* De nouvelles mesures intitulées [Personnes](../metrics/people.md) et [Périphériques uniques](../metrics/unique-devices.md) sont disponibles.
* La mesure [Visiteurs uniques](../metrics/unique-visitors.md) n&#39;est pas disponible, car elle est remplacée par &quot;Personnes&quot; et &quot;Périphériques uniques&quot;.
* Lors de la création de segments, le conteneur de segments « Visiteur » est remplacé par un conteneur « Personne ».
