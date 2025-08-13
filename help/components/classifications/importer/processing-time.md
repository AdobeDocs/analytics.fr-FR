---
title: Temps de traitement de l’importateur de classifications
description: Comprenez la période pendant laquelle Adobe traite les fichiers de classification et comment réduire le temps de traitement.
feature: Classifications
exl-id: 6b8b87f1-5dbc-46b8-9912-0e3086ff4b2a
source-git-commit: 4eea524bf95c9b6bc9ddc878c8c433bc1e60daee
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 100%

---

# Temps de traitement de l’importateur de classifications

{{classification-importer-deprecation}}

Le temps de traitement d’un fichier de classification varie en fonction de la taille du fichier et du nombre total de fichiers traités par Adobe. Les classifications ne durent généralement pas plus de 24 heures. Cependant, les périodes de classification intensive chez les organisations utilisant Adobe Analytics peuvent entraîner un temps de traitement supérieur à 24 heures. Adobe a remarqué une utilisation intensive de la classification dans les mois précédant la période des fêtes.

Pour vérifier si un fichier de classification est terminé, procédez comme suit :

1. Connectez-vous à Adobe Analytics, puis accédez à **[!UICONTROL Admin]** > **[!UICONTROL Importateur de classifications]**.
2. Sélectionnez la suite de rapports et le jeu de données en question.
3. Si le traitement n’est pas encore terminé, l’un des messages suivants apparaît :

   * ![Remarque](assets/icon_notice_notice.gif) Une importation de classifications est en cours de traitement pour le rapport sélectionné.
   * ![Remarque](assets/icon_notice_notice.gif) Le rapport sélectionné contient des données de classification qui n’ont pas encore été propagées vers tous les serveurs.

Si vous souhaitez réduire le temps d’importation des classifications, Adobe recommande vivement de respecter les consignes suivantes :

* **Utilisez le créateur de règles de classification dans la mesure du possible** : le créateur de règles de classification traite les données différemment de l’importateur de classifications traditionnel. Si les données de classification suivent des modèles spécifiques, il est vivement recommandé d’utiliser cette fonctionnalité.
* **Chargez uniquement les lignes modifiées** : cette pratique réduit considérablement le temps nécessaire au traitement des fichiers de classification, puisque les lignes inchangées sont écartées. Adobe recommande vivement de ne charger que les lignes modifiées.
* **Faites preuve de prévoyance** : commencez à charger les données de classification dès que possible, en particulier si ces données sont utilisées pendant la période des fêtes.
* **Combinez les fichiers de classification dans la mesure du possible** : si une variable unique comporte plusieurs classifications, téléchargez un seul fichier contenant toutes les classifications applicables. Évitez de charger plusieurs classifications pour une même variable.
* **Évitez de charger des fichiers de plus de 500 Mo** : si vous traitez de grandes quantités de données de classification, Adobe recommande de diviser les fichiers en fichiers de 100 Mo à 500 Mo.
* **Évitez de charger un grand nombre de fichiers sur FTP** : si vous prévoyez de charger les mêmes fichiers vers de nombreuses suites de rapports par FTP, limitez le nombre de fichiers chargés à la fois. Adobe recommande que le nombre de fichiers multiplié par le nombre de suites de rapports applicables soit inférieur à 1 000. En cas de chargement de 100 fichiers vers 100 suites de rapports, le nombre total de fichiers est de 10 000. Plutôt que de charger les 100 fichiers à la fois, divisez-les en 10 groupes de 10 fichiers à la fois.
* **Chargez les petits fichiers via l’importateur de navigateur** : si vous disposez d’un fichier de moins de 1 Mo (moins de 50 000 lignes), Adobe recommande d’utiliser l’importateur de navigateur. Les importations par navigateur sont généralement plus rapides que les importations par FTP.
