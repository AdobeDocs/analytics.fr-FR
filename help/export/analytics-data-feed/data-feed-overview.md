---
description: Les données qui sont collectées sur des sites web ou sur des applications mobiles, ou qui sont chargées à l’aide de sources de données ou d’API de services web, sont traitées et stockées dans Data Warehouse d’Adobe. Ces données brutes constituent le jeu de données utilisé par Adobe Analytics.
keywords: clickstream;data feed;datafeed;Data Feed
title: Flux de données Analytics - Aperçu
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Flux de données Analytics - Aperçu

Les flux de données constituent un moyen puissant d’obtenir des données brutes à partir d’Adobe Analytics. Ces données brutes peuvent être utilisées sur d’autres plates-formes en dehors d’Adobe à la discrétion de votre entreprise. Les données sont fournies par lots horaires à la fin de chaque heure, ou par lots quotidiens à la fin de chaque journée.

## Conditions préalables

Veillez à respecter toutes les exigences suivantes avant d’utiliser des flux de données.

* Utilisez un site FTP et des informations d’identification. Les flux de données peuvent uniquement être envoyés vers une destination serveur. Votre entreprise fournit généralement des informations d’identification FTP. Adobe peut fournir un emplacement FTP avec un volume de stockage modeste à votre demande. Contactez le service à la clientèle pour demander une destination FTP pour les flux de données.
* Implémentation opérationnelle qui envoie des données aux serveurs de collecte de données Adobe. Voir [Validation et publication d’une mise en oeuvre dans Lancement](../../implement/implement-with-launch/validate-publish-prod.md) dans le guide de l’utilisateur Mise en oeuvre.
* Votre compte est un administrateur de produit Analytics ou votre compte appartient à un profil de produit avec accès aux flux de données.

## Procédure de prise en main

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur l’icône à 9 carrés dans l’angle supérieur droit, puis sur le logo Analytics coloré.
3. Dans la barre de navigation supérieure, accédez à Admin &gt; Flux de données.
4. Cliquez sur [!UICONTROL Ajouter]. Une nouvelle page s’affiche avec trois catégories principales : Informations [!UICONTROL sur]le flux, [!UICONTROL destination]et définitions des colonnes de [!UICONTROL données].
5. Renseignez les champs Informations [!UICONTROL sur le] flux.
   * Nom : Nom souhaité, tel que "Tester le flux de données".
   * Suite de rapports : Sélectionnez une suite de rapports.
   * Courrier électronique une fois terminé : Entrez votre adresse électronique.
   * Intervalle de flux : Sélectionnez l’intervalle souhaité (horaire ou quotidien).
   * Retard du traitement : Peut être laissé comme [!UICONTROL Pas de délai].
   * Dates de début et de fin : Sélectionnez une date de début d’il y a plusieurs jours et aujourd’hui la date de fin.
6. Renseignez les champs [!UICONTROL Destination] .
   * Type : FTP
   * Hôte : Entrez l’URL de destination FTP de votre choix. Par exemple : `ftp://ftp.omniture.com`.
   * Chemin : Peut être laissé vide
   * Nom d'utilisateur : Entrez le nom d'utilisateur pour vous connecter au site FTP.
   * Mot de passe et mot de passe de confirmation : Entrez le mot de passe de connexion au site FTP.
7. Renseignez les définitions [!UICONTROL des colonnes de]données.
   * Sélectionnez le dernier modèle Toutes les colonnes Adobe dans la liste déroulante.
   * Format de compression : Gzip
   * Type d’assemblage : Plusieurs fichiers
   * Manifeste : Aucun fichier
8. Cliquez sur [!UICONTROL Enregistrer] dans le coin supérieur droit.
9. Une fois enregistré, le traitement des données historiques commence. Lorsque le traitement des données est terminé pour une journée, le fichier est placé sur le site FTP.
10. Connectez-vous au site FTP à l’aide de l’Explorateur Windows ou d’un client FTP dédié.
11. Téléchargez le fichier de flux de données compressé sur votre ordinateur local.
12. Décompressez le fichier compressé à l’aide d’un programme prenant en charge les extensions de `.tar.gz` fichier.
13. Ouvrez le `hit_data.tsv` fichier dans votre tableur ou application de base de données de votre choix pour afficher les données brutes pour cette journée.

## Étapes suivantes

Une fois que vous avez compris le processus de base d’obtention des flux de données, vous pouvez travailler avec des équipes de votre entreprise pour stocker ou assimiler des données brutes dans une base de données.

* [Créez un flux](create-feed.md)de données : Détails techniques pour la création d’un flux de données, expliquant plus en détail les champs individuels
* [Gérer les flux](df-manage-feeds.md)de données : En savoir plus sur la navigation dans l’interface du flux de données
* [Contenu](c-df-contents/datafeeds-contents.md)du flux de données : Comprendre le contenu du fichier compressé
* [Définitions](c-df-contents/datafeeds-reference.md)des colonnes de données : Liste exhaustive de toutes les colonnes disponibles

## Ressources supplémentaires

Navigation vidéo dans l’interface du flux de données :

> [!VIDEO](https://www.youtube.com/watch?v=m_fb--gNtR4)
