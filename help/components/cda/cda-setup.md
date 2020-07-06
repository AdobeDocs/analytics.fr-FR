---
title: Configuration des analyses entre appareils
description: Découvrez comment configurer les analyses entre appareils une fois que vous avez satisfait aux conditions préalables.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 100%

---


# Configuration des analyses entre appareils

Une fois toutes les conditions préalables remplies, procédez comme suit pour activer les analyses entre appareils. Vous devez appartenir à un groupe d’administrateurs de profil de produit ou disposer de droits d’administrateur dans Adobe Analytics pour suivre cette procédure.

>[!IMPORTANT]
>
>Toutes les conditions préalables doivent être remplies avant de suivre cette procédure. Si toutes les conditions préalables ne sont pas remplies, la fonction n’est pas disponible ou ne fonctionne pas. Pour connaître les conditions préalables et les limites, reportez-vous à la section [Analyses entre appareils](cda-home.md).

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
8. Cochez la case « Visites des utilisateurs agrafés selon les appareils ».
9. Cliquez sur Continuer, terminez la configuration de la suite de rapports virtuelle, puis cliquez sur Enregistrer.

![Case à cocher Analyses entre appareils](assets/cda-checkbox.png)

## Ajouts et modifications apportés aux suites de rapports virtuelles sur plusieurs appareils

Lorsque les analyses entre appareils sont activées sur une suite de rapports virtuelle, notez les modifications suivantes :

* Une nouvelle icône interpériphérique apparaît en regard du nom de la suite de rapports virtuelle. Cette icône est réservée aux suites de rapports virtuelles sur plusieurs appareils.
* Une nouvelle dimension intitulée « État identifié » est disponible. Cette dimension détermine si l’Experience Cloud ID sur cet accès est connu par le graphique de l’appareil à ce moment.
* De nouvelles mesures intitulées « Personnes » et « Appareils uniques » sont disponibles.
* La mesure « Visiteurs uniques » n’est pas disponible, car elle est remplacée par « Personnes »et « Appareils uniques ».
* Lors de la création de segments, le conteneur de segments « Visiteur » est remplacé par un conteneur « Personne ».

## Modèle CDA Workspace

Adobe offre un modèle pour afficher les données de performances vitales entre appareils.

1. Accédez à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) et connectez-vous à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’icône à neuf grilles en haut de l’écran, puis sur Analytics.
1. Cliquez sur [!UICONTROL Workspace] en haut de l’écran, puis sur [!UICONTROL Créer un projet].
1. Localisez le modèle « Journey IQ : Analyses entre appareils », puis cliquez sur [!UICONTROL Créer].
1. Si vous y êtes invité, remplacez la suite de rapports par une suite prenant en charge CDA (les Analyses entre appareils).

Un projet Analysis Workspace est créé et contient plusieurs panneaux. Dans la partie supérieure, une table des matières et une introduction s’affichent, permettant de replacer le contexte du rapport et de naviguer jusqu’aux rapports individuels. Cliquez sur un lien dans la table des matières ou développez l’accordéon d’un panneau pour afficher ces rapports.

<!-->The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md<-->

* **Note spéciale à l’intention des membres du graphique Co-op** : Affiche la partie de votre suite de rapports qui contient des visiteurs dans les régions où le graphique Co-op est pris en charge et les régions où il n’est pas pris en charge.
* **Identification des utilisateurs** : Indique la fréquence à laquelle les visiteurs de votre site sont identifiés à l’aide de méthodes basées sur les analyses entre appareils.
* **Mesure de la taille des audiences** : Affiche une comparaison entre « Appareils uniques » et « Personnes ». La proportion entre ces deux nombres est connue sous le nom de « Compression entre appareils », une mesure calculée visible dans ce panneau. Cette mesure de compression dépend d’un large éventail de facteurs :
   * Utilisation du graphique Co-op ou du graphique Privé : en général, les entreprises qui utilisent le Device Co-op ont tendance à voir de meilleurs taux de compression que les celles qui utilisent le graphique Privé.
   * Taux de connexion : plus les utilisateurs se connectent sur votre site, plus Adobe est en mesure d’identifier et de regrouper les visiteurs entre plusieurs appareils. Les sites qui présentent un faible taux de connexion ont aussi de faibles taux de compression.
   * Couverture d’Experience Cloud ID : seuls les visiteurs avec un ECID peuvent être regroupés. Un pourcentage plus faible de visiteurs qui accèdent à votre site en utilisant un ECID correspond à des taux de compression plus faibles.
   * Utilisation de plusieurs appareils : si les visiteurs qui se rendent sur votre site n’utilisent pas plusieurs appareils, les taux de compression sont plus faibles.
   * Granularité des rapports : la compression par jour est généralement plus petite que la compression par mois ou par année. Les chances qu’une personne utilise plusieurs appareils sont moindres au cours d’un seul jour qu’au cours d’un mois entier. La segmentation, le filtrage ou l’utilisation de dimensions de ventilation peuvent également indiquer un taux de compression plus faible.
* **Segments basés sur les personnes** : Contient une liste déroulante de segments qui vous permet d’afficher des données spécifiques à l’appareil. Ce panneau encourage l’expérimentation de segments afin de déterminer comment l’inclusion ou l’exclusion de types d’appareil affectent les rapports.
* **Analyse du parcours entre appareils** : Fournit des rapports de flux et d’abandons en fonction du type d’appareil.
* **Attribution entre appareils** : Combinez les fonctionnalités Journey IQ et Attribution IQ.
* **Autres conseils et astuces** : Rubriques utiles sur les Analyses entre appareils qui vous permettent de mieux l’utiliser.
