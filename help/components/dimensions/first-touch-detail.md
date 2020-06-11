---
title: Détails du canal Première touche
description: Détails du premier canal marketing dans l’expiration de l’engagement du visiteur.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---


# Détails du canal Première touche

La dimension &quot;Détails du canal Première touche&quot; rapporte les détails relatifs au premier canal marketing auquel un visiteur correspond au cours de la période d’engagement de cet visiteur (30 jours par défaut). Cette dimension est utile pour comprendre ce qui a contribué à la correspondance des accès avec un canal marketing. Par exemple, si un visiteur est arrivé sur votre site et a fait une correspondance avec le canal marketing &quot;Recherche payée&quot;, vous pouvez utiliser les détails du canal pour identifier le moteur de recherche utilisé ou le mot-clé recherché.

## Renseigner cette dimension avec des données

Cette dimension copie les valeurs d’autres variables. La variable utilisée référence la valeur de canal dans chaque règle [de traitement du canal](/help/admin/admin/marketing-channels-admin.md)marketing. Lorsqu’un accès correspond à une règle de traitement du canal marketing, la dimension canal [](last-touch-channel.md) Dernière touche est définie sur le nom du canal et cette dimension est définie sur la valeur de canal définie dans la règle.

Pour définir cette dimension sur une valeur spécifique, procédez comme suit :

* Assurez-vous que la valeur de dimension souhaitée se trouve dans un attribut d’accès ou une variable personnalisée.
* Définissez une règle de traitement du canal marketing qui contient les critères de votre choix pour l’accès.
* Sélectionnez une valeur de liste déroulante sous [!UICONTROL Définir la valeur] du canal dans la règle de traitement du canal marketing.
* L’visiteur qui a accédé à votre site doit correspondre aux critères décrits dans la règle de traitement du canal marketing __ et doit être la première valeur du canal marketing à le faire au cours de la période d’engagement du visiteur.

Si un accès ultérieur correspond à des critères sous un autre canal marketing, cette dimension n’est pas remplacée par le nouveau canal marketing.

## Valeurs de dimension

Les valeurs de dimension dépendent de la liste déroulante des valeurs de canal. Par exemple, si vous définissez la valeur de canal sur &quot;URL de page&quot;, les valeurs de dimension incluent les URL de page sur votre site. Si vous définissez la valeur du canal sur Domaine référent, les valeurs de dimension incluent les domaines sur lesquels les visiteurs ont cliqué pour accéder à votre site. Cette dimension agrégat toutes les valeurs de dimension détaillées, quel que soit le canal dans lequel elles se trouvent.

Adobe recommande de définir des valeurs de canal liées au canal marketing pour obtenir des informations détaillées sur les canaux.
