---
title: Visites
description: Découvrez la mesure Visites dans Analytics. Découvrez comment elle est calculée, les comportements qui l’affectent, comment modifier sa définition, etc.
feature: Metrics
exl-id: 4f78f2b5-f958-44fe-876a-83f07980beec
source-git-commit: 5f80d1f56fb8a95780ff2daf18644ac5ffb548d6
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 85%

---

# Visites

La [mesure](overview.md) « Visites » indique le nombre de sessions parmi l’ensemble des visiteurs et visiteuses de votre site.

## Méthode de calcul de cette mesure

Une visite est toujours associée à une période afin que vous sachiez si vous comptabilisez ou non une nouvelle visite si la même personne revient sur votre site. Une visite commence lorsque l’utilisateur arrive pour la première fois sur votre site. Une visite se termine lorsque l’un des critères suivants est rempli :

* **30 minutes d’inactivité** : pratiquement toutes les sessions se terminent de cette manière. Si plus de 30 minutes s’écoulent entre les accès, une nouvelle session commence.
* **12 heures d’activité** : si un utilisateur déclenche des demandes d’image en continu sans intervalle de 30 minutes sur une période de plus de 12 heures, une nouvelle visite commence automatiquement.
* **2 500 accès** : si un utilisateur génère un grand nombre d’accès sans nouvelle session, une nouvelle visite est comptabilisée après 2 500 demandes d’image.
* **100 accès en 100 secondes** : si une visite comporte plus de 100 accès au cours des 100 premières secondes, la visite se termine automatiquement. Ce comportement indique généralement des robots et cette restriction s’applique afin d’augmenter les performances des rapports.

Une visite ne coïncide pas nécessairement avec une session de navigateur en raison des critères ci-dessus. L’une des différences les plus courantes concerne le cas où un visiteur accède à votre site, laisse l’onglet ouvert pendant plus de 30 minutes, puis reprend la navigation. Bien que cette action fasse techniquement partie d’une même session de navigation, Adobe considère cette action comme deux visites distinctes.

## Comportements affectant les visites

Une nouvelle visite commence si le visiteur :

* Supprime leurs cookies en milieu de session et continue à parcourir votre site.
* Laisse votre site ouvert dans un onglet pendant plus de 30 minutes, puis poursuit la navigation.
* Ouvre un autre navigateur et accède à votre site depuis le même ordinateur.
* Consulte votre site depuis un autre appareil

Tant qu’il s’écoule moins de 30 minutes entre les accès consécutifs, une nouvelle visite n’est **pas** comptabilisée si l’utilisateur :

* Ferme son navigateur, puis accède à nouveau à votre site.
* Redémarre son ordinateur, ouvre le même navigateur et accède à nouveau à votre site.
* Change de réseau, par exemple en passant d’un réseau câblé à un réseau sans fil.
* Navigue sur votre site dans plusieurs onglets. Si un visiteur bascule d’un onglet à l’autre, chaque accès est comptabilisé comme faisant partie de la même visite.

## Modification de la définition d’une visite

Vous pouvez modifier le délai de 30 minutes dans la définition d’une visite.

* Pour les [suites de rapports virtuelles](../vrs/vrs-about.md), vous pouvez modifier le délai de visite (délai entre les accès qui entraîne le démarrage d’une nouvelle visite) à l’aide de la liste déroulante [!UICONTROL Délai de visite]. Vous pouvez définir le délai d’expiration de la visite sur n’importe quelle valeur raisonnable.
* Pour les suites de rapports standard, contactez l’assistance clientèle pour demander que le délai de visite (délai entre les accès qui entraîne le démarrage d’une nouvelle visite) soit raccourci pour une suite de rapports donnée. Le délai d’expiration des visites pour les suites de rapports standard ne peut pas dépasser 30 minutes. Vous ne pouvez donc que le raccourcir.

## Visites s’étendant au-delà d’une limite de date

Une visite compte pour chaque période impliquée. Par exemple, si un visiteur commence la navigation sur votre site le lundi à 23 h 45, puis envoie sa dernière demande d’image le mardi à 00 h 10, une visite est comptabilisée le lundi et une autre le mardi. Cependant, la mesure du total de visites est dédupliquée, n’affichant qu’une visite pour la période du projet.

## Visites sur une dimension par rapport au nombre total de visites

Dans le contexte d’une dimension (par exemple, un [canal marketing](../dimensions/marketing-channel.md)), les visites indiquent le nombre de visites qui contenaient un élément de dimension spécifique à tout moment. Il est fréquent que plusieurs éléments de dimension existent sur différents accès au cours d’une même visite. Il n’est généralement pas logique de tenter d’additionner les visites qui génèrent des rapports sur les éléments de dimension.

## Visites - Tous les visiteurs (Data Warehouse)

La mesure « Visites - Tous les Visiteurs » est disponible dans Data Warehouse en plus de la mesure Visites. La mesure « Visites - Tous les Visiteurs » est comparable à la mesure « Visites » dans dʼautres outils Analytics. La mesure « Visites » dans Data Warehouse exclut les visiteurs qui nʼont pas de cookies persistants. Adobe recommande dʼutiliser « Visites - Tous les Visiteurs » dans les demandes de Data Warehouse lorsque les visites sont souhaitées comme mesure.
