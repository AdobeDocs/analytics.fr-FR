---
title: Modèle CDA Workspace
description: Décrit chaque champ du modèle CDA dans Analysis Workspace.
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 96%

---

# Modèle CDA Workspace

Adobe offre un modèle pour afficher les données de performances vitales entre appareils.

1. Accédez à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) et connectez-vous à l’aide de vos identifiants Adobe ID.
1. Cliquez sur l’icône à neuf grilles en haut de l’écran, puis sur Analytics.
1. Cliquez sur [!UICONTROL Workspace] en haut de l’écran, puis sur [!UICONTROL Créer un projet].
1. Localisez le modèle « Analyses entre appareils », puis cliquez sur [!UICONTROL Créer].
1. Si vous y êtes invité, remplacez la suite de rapports par une suite prenant en charge CDA (les Analyses entre appareils).

Un projet Analysis Workspace est créé et contient plusieurs panneaux. Dans la partie supérieure, une table des matières et une introduction s’affichent, permettant de replacer le contexte du rapport et de naviguer jusqu’aux rapports individuels. Cliquez sur un lien dans la table des matières ou développez l’accordéon d’un panneau pour afficher ces rapports.

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **Identification des utilisateurs** : Indique la fréquence à laquelle les visiteurs de votre site sont identifiés à l’aide de méthodes basées sur les analyses entre appareils.
* **Mesure de la taille des audiences** : Affiche une comparaison entre « Appareils uniques » et « Personnes ». La proportion entre ces deux nombres est connue sous le nom de « Compression entre appareils », une mesure calculée visible dans ce panneau. Cette mesure de compression dépend d’un large éventail de facteurs :
   * Taux de connexion : plus les utilisateurs se connectent sur votre site, plus Adobe est en mesure d’identifier et de regrouper les visiteurs entre plusieurs appareils. Les sites qui présentent un faible taux de connexion ont aussi de faibles taux de compression.
   * Couverture d’Experience Cloud ID : seuls les visiteurs avec un ECID peuvent être regroupés. Un pourcentage plus faible de visiteurs qui accèdent à votre site en utilisant un ECID correspond à des taux de compression plus faibles.
   * Utilisation de plusieurs appareils : si les visiteurs qui se rendent sur votre site n’utilisent pas plusieurs appareils, les taux de compression sont plus faibles.
   * Granularité des rapports : la compression par jour est généralement plus petite que la compression par mois ou par année. Les chances qu’une personne utilise plusieurs appareils sont moindres au cours d’un seul jour qu’au cours d’un mois entier. La segmentation, le filtrage ou l’utilisation de dimensions de répartition peuvent également indiquer un taux de compression plus faible.
* **Segments basés sur les personnes**: Contient une liste déroulante de segments qui vous permet d’afficher des données spécifiques à l’appareil. Ce panneau encourage l’expérimentation de segments afin de déterminer comment l’inclusion ou l’exclusion de types d’appareil affectent les rapports.
* **Analyse du parcours entre appareils** : Fournit des rapports de flux et d’abandons en fonction du type d’appareil.
* **Attribution entre appareils** : Combinez les fonctionnalités Journey IQ et Attribution IQ.
* **Autres conseils et astuces** : Rubriques utiles sur les Analyses entre appareils qui vous permettent de mieux l’utiliser.
