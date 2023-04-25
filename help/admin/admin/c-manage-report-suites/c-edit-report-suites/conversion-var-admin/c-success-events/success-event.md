---
description: Les événements de succès sont des actions dont le suivi peut être effectué. Il vous appartient de déterminer ce qu’est un événement de succès. Par exemple, si un visiteur achète un article, l’achat peut être considéré comme un événement de succès..
keywords: événement
title: Événements de succès - Aperçu
feature: Event
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 100%

---

# Événements de succès - Aperçu

Les événements de succès (également appelés événements de conversion ou événements personnalisés) sont des actions dont le suivi peut être effectué. Il vous appartient de déterminer ce qu’est un événement de succès. Par exemple, si un visiteur achète un article, l’achat peut être considéré comme un événement de succès..

Voici une présentation vidéo :

>[!VIDEO](https://video.tv.adobe.com/v/28764/?quality=12)

Accédez à la page Événements de succès dans les paramètres de la suite de rapports :

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur l’icône à neuf carrés en haut de l’écran, puis sur [!UICONTROL Analytics].
3. Accédez à [!UICONTROL Admin] > [!UICONTROL Suites de rapports]
4. Sélectionnez la suite de rapports de votre choix, puis accédez à [!UICONTROL Modifier les paramètres] > [!UICONTROL Conversion] > [!UICONTROL Événements de succès].

Il existe de nombreux types d’événements de succès en fonction du type de votre site web. En voici quelques exemples :

* **Vente au détail** : consultation produit, passage en caisse, achat
* **Média** : inscription, inscription à des concours, pages vues, affichage de vidéos
* **Finance** : envoi d’applications, connexion, utilisation d’outils en libre-service
* **Voyage** : réservation (achat), campagne interne (clic publicitaire), recherche (prix, itinéraires)
* **Télécommunications** : achat, pistes, utilisation d’outils en libre-service
* **Haute technologie** : téléchargement de livres blancs, appels d’offres, remplissage de formulaires, demandes d’assistance
* **Automobile** : envoi de pistes, demande de devis, téléchargement de brochures

La variable [s.events](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=fr) définit un événement de succès.

## Page Événements de succès – Descriptions {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Conversion]** > **[!UICONTROL Événements de succès]**

La page Événements de succès vous permet de configurer les variables Événements utilisées sur votre site. Vous pouvez ajouter jusqu’à 1 000 événements de succès. Les événements 81 à 1 000 fonctionnent uniquement avec le code H22 ou supérieur.

| Élément | Description |
|--- |--- |
| Événement | Nom original de l’événement. |
| Nom | Attribuez des noms explicites aux événements de succès utilisés sur votre site. Par exemple, si événement1 est utilisé pour effectuer le suivi des inscriptions, renommez-le pour qu’il apparaisse en tant que mesure « Inscriptions » dans tous les rapports de conversion. |
| Type | Le Type sélectionné détermine si l’événement est de type compteur (standard), numérique ou monétaire. Les événements numériques et monétaires vous permettent d’incrémenter les mesures de plus d’une unité.  Les événements de compteur permettent d’enregistrer un événement dans le temps, alors que les événements de devise enregistrent un nombre décimal, comme une taxe ou des frais d’expédition. La valeur transmise aux événements de devise est convertie depuis la devise de la page vers la devise de base de la suite de rapports dès réception. Pour plus d’informations sur l’utilisation d’événements de devise, contactez un représentant Adobe. Les événements numériques sont utilisés pour établir des rapports sur des valeurs non monétaires, telles que le nombre de bons d’achat utilisés dans une commande. Les événements monétaires sont utilisés pour le suivi des impôts et des frais d’expédition. Les événements utilisés dans le type standard de Sources de données doivent être numériques ou monétaires. |
| Polarité | La polarité permet d’indiquer si Adobe Analytics doit considérer comme un point positif ou négatif le fait qu’un événement personnalisé donné (mesure) augmente. Adobe Analytics pourra alors présenter des indicateurs de direction (flèches) pour diverses mesures afin d’ajouter du contexte (par exemple, comparaisons d’une semaine à l’autre).  Exemple : si l’événement « Bogues envoyés » augmente d’une semaine à l’autre, Adobe Analytics doit-il considérer cela comme un facteur positif ou négatif ? Une augmentation des inscriptions au publipostage est probablement bénéfique. En revanche, une augmentation des erreurs de soumission de formulaire est probablement mauvais signe.  Dans Analysis Workspace, la polarité est appliquée à : mise en forme conditionnelle de table de forme libre, visualisations de changement récapitulatives et modèle de couleur positif / négatif de la visualisation de mappage. |
| Description | Brève description de l’objet et de l’usage d’un événement. |
| Enregistrement d’événement unique | **Enregistrer une fois par visite** : Lie l’événement donné à la session du visiteur. Les comptes suivants effectués sur un événement donné au cours d’une même visite sont ignorés. Ce type de sérialisation d’événement ne nécessite aucune modification de l’implémentation.<br>**Utiliser l’ID d’événement :** Lie l’événement donné à un ID personnalisé. Les comptes suivants effectués sur un événement donné avec le même ID d’événement sont ignorés. Ce type de sérialisation d’événement nécessite un identifiant personnalisé dans les accès pour dédupliquer les valeurs. Voir [Sérialisation des ID d’événements](/help/implement/vars/page-vars/events/event-serialization.md) dans le guide d’utilisation de la mise en œuvre. |
| Participation | Accorde un crédit d’attribution complet à tous les éléments de dimension de la visite. |
| Avertissement (événement de devise) | Lorsque vous définissez un événement sur le type monétaire ou définissez ce type d’événement sur un autre, un message s’affiche pour vous informer que les données historiques ne sont pas disponibles dans les rapports.  Les différents types d’événement utilisent des tableaux de données distincts, et ne peuvent pas être utilisés simultanément. Certaines données historiques peuvent être restaurées si l’utilisateur rétablit le type d’événement. Cependant, les données collectées après la modification initiale ne sont pas disponibles. Soyez prudent lorsque vous changez un type d’événement. |
