---
title: Détails du canal Dernière touche
description: Détails du dernier canal marketing dans l’expiration de l’engagement du visiteur.
feature: Dimensions
exl-id: def03267-f3e5-4772-a707-5678c45eba6d
source-git-commit: ab0f0c80c13b9064b40511b59d03d9d899d20df1
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 100%

---

# Détails du canal Dernière touche

La dimension « Détails du canal Dernière touche » fournit des détails relatifs au dernier canal marketing auquel un visiteur correspond au cours de la période d’engagement de ce visiteur (30 jours par défaut). Cette dimension est utile pour comprendre ce qui a contribué à la correspondance des accès avec un canal marketing. Par exemple, si un visiteur arrive sur votre site et correspond au canal marketing « Référencement payant », vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.

## Renseignement de cette dimension avec des données

Cette dimension copie les valeurs d’autres variables. La variable utilisée fait référence à la valeur de canal dans chaque [règle de traitement des canaux marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels-admin.md). Lorsqu’un accès correspond à une règle de traitement des canaux marketing, la dimension [Canal Dernière touche](last-touch-channel.md) est définie sur le nom du canal et cette dimension est définie sur la valeur de canal définie dans la règle.

Pour définir une valeur spécifique sur cette dimension, procédez comme suit :

* Assurez-vous que l’élément de dimension souhaité se trouve dans un attribut d’accès ou une variable personnalisée.
* Définissez une règle de traitement des canaux marketing qui contient les critères de votre choix pour l’accès.
* Sélectionnez la valeur de liste déroulante souhaitée sous [!UICONTROL Définir la valeur du canal] dans la règle de traitement des canaux marketing.
* L’accès du visiteur à votre site doit correspondre aux critères décrits dans la règle de traitement des canaux marketing.

## Éléments de dimension

Les éléments de dimension dépendent de la liste déroulante des valeurs de canal. Par exemple, si vous définissez la valeur de canal sur « URL de page », les éléments de dimension comprennent les adresses URL de page sur votre site. Si vous définissez la valeur du canal sur Domaine référent, les éléments de dimension comprennent les domaines sur lesquels les visiteurs ont cliqué pour accéder à votre site. Cette dimension agrège tous les éléments de dimension détaillés, quel que soit le canal dans lequel ils se trouvent.

Adobe recommande de définir des valeurs de canal liées au canal marketing pour obtenir des informations détaillées sur les canaux.
