---
title: Temps de traitement de l’importateur de classifications
description: Comprendre la période pendant laquelle l’Adobe traite les fichiers de classification et comment réduire le temps de traitement.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---


# Temps de traitement de l’importateur de classifications

Le temps de traitement d’un fichier de classification varie en fonction de la taille du fichier et du nombre total de fichiers traités par l’Adobe. Les classifications ne durent généralement pas plus de 72 heures. Cependant, les périodes de classification intensive utilisées par les organisations qui utilisent Adobe Analytics peuvent entraîner une durée de vie des fichiers supérieure à 72 heures. L&#39;Adobe voit une utilisation intensive des classifications dans les mois précédant la période des fêtes.

Pour savoir si un fichier de classification est terminé, procédez comme suit :

1. Connectez-vous à Adobe Analytics, puis accédez à **[!UICONTROL Admin]** > Importateur **[!UICONTROL de]** classifications.
2. Sélectionnez la suite de rapports et le jeu de données en question.
3. Si le traitement n’est pas encore terminé, l’un des messages suivants s’affiche :

   * ![Avis](assets/icon_notice_notice.gif) L&#39;état sélectionné a une importation de classification en cours de traitement.
   * ![Remarque](assets/icon_notice_notice.gif) Le rapport sélectionné contient des données de classification qui n&#39;ont pas encore été propagées à tous les serveurs.

Si vous souhaitez réduire le temps d’importation des classifications, l’Adobe recommande vivement de respecter les consignes suivantes :

* **Dans la mesure du possible**, utilisez le créateur de règles de classification : Le créateur de règles de classification traite les données différemment de l’importateur de classifications traditionnel. Si les données de classification suivent des modèles spécifiques, il est vivement recommandé d’utiliser cette fonctionnalité.
* **Télécharger uniquement les lignes** modifiées : Cette pratique réduit considérablement le temps nécessaire au traitement des fichiers de classification, puisqu’il n’est pas possible de trier les lignes inchangées. L’Adobe recommande vivement de ne charger que les lignes modifiées.
* **Prévision**: Début de transfert des données de classification dès que possible, en particulier si ces données sont utilisées pendant la période des fêtes.
* **Combiner des fichiers de classification lorsque cela est possible**: Si une variable unique comporte plusieurs classifications, téléchargez un fichier unique contenant toutes les classifications applicables. Evitez de télécharger plusieurs classifications pour la même variable.
* **Evitez de télécharger des fichiers de plus de 500 Mo**: Si vous traitez de grandes quantités de données de classification, l’Adobe recommande de diviser les fichiers en fichiers de 100 Mo à 500 Mo.
* **Evitez de télécharger de grandes quantités de fichiers sur FTP**: Si vous prévoyez de télécharger les mêmes fichiers dans de nombreuses suites de rapports par FTP, limitez le nombre de fichiers téléchargés à la fois. L’Adobe recommande que le nombre de fichiers multiplié par le nombre de suites de rapports applicables soit inférieur à 1 000. Si le téléchargement de 100 fichiers vers 100 suites de rapports est requis, le nombre total de fichiers est de 10 000. Plutôt que de télécharger les 100 fichiers à la fois, divisez-les en 10 groupes de 10 fichiers à la fois.
* **Téléchargez des petits fichiers via l’importateur** de navigateur : Si vous disposez d’un fichier de moins de 1 Mo (moins de 50 000 lignes), l’Adobe recommande d’utiliser l’importateur de navigateur. Les importations par navigateur sont presque toujours plus rapides que les importations par FTP.
