---
title: Configuration des analyses entre appareils
description: Découvrez comment configurer les analyses entre appareils une fois que vous avez satisfait aux conditions préalables.
translation-type: tm+mt
source-git-commit: d847fb9dc1427727a0162be993ddc4a73c52f192
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 63%

---


# Configuration des analyses entre appareils

Une fois toutes les conditions préalables remplies, procédez comme suit pour activer les analyses entre appareils. Vous devez appartenir à un groupe d’administrateurs de profil de produit ou disposer de droits d’administrateur dans Adobe Analytics pour suivre cette procédure.

>[!IMPORTANT] Toutes les conditions préalables doivent être remplies avant de suivre cette procédure. Si toutes les conditions préalables ne sont pas remplies, la fonction n’est pas disponible ou ne fonctionne pas. Pour connaître les conditions préalables et les limites, reportez-vous à la section [Analyses entre appareils](cda-home.md).

## Choisissez la suite de rapports entre appareils qui sera activée pour les analyses entre appareils.

Lorsque votre entreprise est configurée pour utiliser les analyses entre appareils, vous choisissez la suite de rapports à utiliser. Ce choix peut être communiqué par l’intermédiaire de votre gestionnaire de compte Adobe. Adobe active ensuite la suite de rapports choisie pour le traitement des analyses entre appareils

## Créer une suite de rapports virtuelle sur plusieurs appareils pour afficher la vue sur plusieurs appareils

Les administrateurs ayant accès à la création de suites de rapports virtuelles peuvent créer des suites de rapports virtuelles des analyses entre appareils comme suit :

1. Accédez à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) et connectez-vous à l’aide de vos identifiants Adobe ID.
2. Cliquez sur l’icône à neuf grilles en haut de l’écran, puis sur Analytics.
3. Passez la souris sur Composants en haut de l’écran, puis cliquez sur Suites de rapports virtuelles.
4. Cliquez sur Ajouter.
5. Saisissez le nom de votre suite de rapports virtuelle et assurez-vous que la suite de rapports compatible avec les analyses entre appareils est sélectionnée.
6. (Facultatif) Appliquez un segment à la suite de rapports virtuelle. Par exemple, vous pouvez appliquer un segment qui limite la suite de rapports virtuelle aux dates suivant l’activation des analyses entre appareils et le début du regroupement. Ce segment permet aux utilisateurs de voir uniquement les plages de dates regroupées dans la suite de rapports virtuelle.
7. Cochez la case « Activer le report de traitement du temps », qui active plusieurs autres options, notamment Analyses entre appareils.
8. Cochez la case « Regrouper les visites de l’utilisateur sur plusieurs appareils ».
9. Cliquez sur Continuer, terminez la configuration de la suite de rapports virtuelle, puis cliquez sur Enregistrer.

![Case à cocher Analyses entre appareils](assets/cda-checkbox.png)

## Ajouts et modifications apportés aux suites de rapports virtuelles sur plusieurs appareils

Lorsque les analyses entre appareils sont activées sur une suite de rapports virtuelle, notez les modifications suivantes :

* Une nouvelle icône interpériphérique apparaît en regard du nom de la suite de rapports virtuelle. Cette icône est réservée aux suites de rapports virtuelles sur plusieurs appareils.
* Une nouvelle dimension intitulée &quot;État identifié&quot; est disponible. Cette dimension détermine si l’ID Experience Cloud sur cet accès est connu par le graphique du périphérique à ce moment.
* De nouvelles mesures intitulées « Personnes » et « Appareils uniques » sont disponibles.
* La mesure &quot;Visiteurs uniques&quot; n’est pas disponible, car elle est remplacée par &quot;Personnes&quot; et &quot;Périphériques uniques&quot;.
* Lors de la création de segments, le conteneur de segments « Visiteur » est remplacé par un conteneur « Personne ».

## Modèle Espace de travail CDA

Adobe offre un modèle pour afficher les données de performances vitales sur plusieurs périphériques.

1. Accédez à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) et connectez-vous à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’icône à neuf grilles en haut de l’écran, puis sur Analytics.
1. Click [!UICONTROL Workspace] at the top, then click [!UICONTROL Create New Project].
1. Localisez le &quot;Journey IQ : Modèle Analytics sur plusieurs périphériques, puis cliquez sur [!UICONTROL Créer].
1. Si vous y êtes invité, remplacez la suite de rapports par une suite prenant en charge CDA.

Un projet Analyse Workspace est créé et contient plusieurs panneaux. Dans la partie supérieure, une table des matières et une introduction s’affichent, permettant de replacer le contexte du rapport et de naviguer jusqu’aux rapports individuels. Cliquez sur un lien dans la table des matières ou développez l’accordéon d’un panneau pour vue de ces rapports.

<!-->The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md<-->

* **Note spéciale à l&#39;intention des membres du graphique** Co-op : Indique la partie de votre suite de rapports qui contient des visiteurs dans les régions où le graphique coopératif est pris en charge et les régions où il n’est pas pris en charge.
* **Identification des utilisateurs**: Indique la fréquence à laquelle les visiteurs de votre site sont identifiés à l’aide de méthodes basées sur les analyses multipériphériques.
* **Mesure de la taille** des audiences : Affiche une comparaison entre &quot;Périphériques uniques&quot; et &quot;Personnes&quot;. La proportion de ces deux nombres est connue sous le nom de &quot;compression multipériphériques&quot;, une mesure calculée visible dans ce panneau. Cette mesure de compression dépend d’un large éventail de facteurs :
   * Utilisation du graphique Co-op ou du graphique Privé : en général, les entreprises qui utilisent le Device Co-op ont tendance à voir de meilleurs taux de compression que les celles qui utilisent le graphique Privé.
   * Taux de connexion : plus les utilisateurs se connectent sur votre site, plus Adobe est en mesure d’identifier et de regrouper les visiteurs entre plusieurs appareils. Les sites qui présentent un faible taux de connexion ont aussi de faibles taux de compression.
   * Couverture d’Experience Cloud ID : seuls les visiteurs avec un ECID peuvent être regroupés. Un pourcentage plus faible de visiteurs qui accèdent à votre site en utilisant un ECID correspond à des taux de compression plus faibles.
   * Utilisation de plusieurs appareils : si les visiteurs qui se rendent sur votre site n’utilisent pas plusieurs appareils, les taux de compression sont plus faibles.
   * Granularité des rapports : la compression par jour est généralement plus petite que la compression par mois ou par année. Les chances qu’une personne utilise plusieurs appareils sont moindres au cours d’un seul jour qu’au cours d’un mois entier. La segmentation, le filtrage ou l’utilisation de dimensions de ventilation peuvent également indiquer un taux de compression plus faible.
* **Segments** basés sur les personnes : Contient une liste déroulante de segments qui vous permet de vue des données spécifiques au périphérique. Ce panneau encourage l’expérimentation de segments afin de déterminer comment l’inclusion ou l’exclusion de types de périphérique affectent les rapports.
* **Analyse du parcours** sur plusieurs périphériques : Fournit des rapports de flux et d&#39;abandons en fonction du type de périphérique.
* **Attribution** sur plusieurs périphériques : Combinez les fonctionnalités de QI de voyage et QI d&#39;attribution.
* **Autres conseils et astuces**: Rubriques utiles sur l&#39;ADC qui vous permettent de mieux les utiliser.
