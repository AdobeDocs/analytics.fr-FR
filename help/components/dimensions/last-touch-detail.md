---
title: Détails du canal Dernière touche
description: Détails du dernier canal marketing au sein de l’expiration de l’engagement du visiteur.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 0%

---


# Détails du canal Dernière touche

La dimension &quot;Détails du canal Dernière touche&quot; rapporte les détails relatifs au dernier canal marketing auquel un visiteur fait une correspondance au cours de la période d’engagement de cet visiteur (30 jours par défaut). Cette dimension est utile pour comprendre ce qui a contribué à la correspondance des accès avec un canal marketing. Par exemple, si un visiteur est arrivé sur votre site et a fait une correspondance avec le canal marketing &quot;Recherche payée&quot;, vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.

## Renseigner cette dimension avec des données

Cette dimension copie les valeurs d’autres variables. La variable utilisée référence la valeur de canal dans chaque règle [de traitement du canal](/help/admin/admin/marketing-channels-admin.md)marketing. Lorsqu’un accès correspond à une règle de traitement du canal marketing, la dimension canal [](last-touch-channel.md) Dernière touche est définie sur le nom du canal et cette dimension est définie sur la valeur de canal définie dans la règle.

Pour définir cette dimension sur une valeur spécifique, procédez comme suit :

* Assurez-vous que l’élément de dimension souhaité se trouve dans un attribut d’accès ou une variable personnalisée.
* Définissez une règle de traitement du canal marketing qui contient les critères de votre choix pour l’accès.
* Sélectionnez une valeur de liste déroulante sous [!UICONTROL Définir la valeur] du canal dans la règle de traitement du canal marketing.
* L’visiteur qui a accédé à votre site doit correspondre aux critères décrits dans la règle de traitement du canal marketing.

## Éléments de dimension

Les éléments de dimension dépendent de la liste déroulante des valeurs de canal. Par exemple, si vous définissez la valeur du canal sur &quot;URL de page&quot;, les éléments de dimension incluent les URL de page sur votre site. Si vous définissez la valeur du canal sur Domaine référent, les éléments de dimension incluent les domaines sur lesquels les visiteurs ont cliqué pour accéder à votre site. Cette dimension agrégat tous les éléments de dimension détaillés, quel que soit le canal dans lequel ils se trouvent.

Adobe recommande de définir des valeurs de canal liées au canal marketing pour obtenir des informations détaillées sur les canaux.
