---
description: Les données qui sont collectées sur des sites Web ou sur des applications mobiles, ou qui sont chargées à l’aide de sources de données ou d’API de services Web, sont traitées et stockées dans Data Warehouse d’Adobe. Ces données brutes constituent le jeu de données utilisé par Adobe Analytics.
keywords: clickstream;data feed;datafeed;Data Feed
title: Flux de données Analytics - Aperçu
uuid: 6bdbe90c-e6ed-4bb0-b5be-24fd795adde4
translation-type: ht
source-git-commit: 984d6034d14cc4256d93bd4f7d1a7f01b63b71e9

---


# Flux de données Analytics - Aperçu

Les flux de données sont un moyen puissant d’extraire des données brutes d’Adobe Analytics. Il est possible d’utiliser ces données brutes sur d’autres plateformes en dehors d’Adobe à la discrétion de votre entreprise. Les données sont diffusées sous la forme de lots horaires à la fin de chaque heure ou sous la forme de lots quotidiens à la fin de chaque jour.

## Conditions préalables

Assurez-vous de respecter l’ensemble des exigences suivantes avant d’utiliser les flux de données.

* Ayez un site FTP et des identifiants à portée de main. Les flux de données peuvent être envoyés uniquement vers une destination de serveur. Votre entreprise fournit généralement les identifiants au FTP. Adobe peut fournir un emplacement FTP avec une quantité modeste de stockage à votre demande. Contactez l’assistance clientèle pour demander une destination FTP pour les flux de données.
* Une implémentation opérationnelle qui envoie des données vers les serveurs de collecte de données Adobe. Consultez [Valider et publier une implémentation dans Launch](/help/implement/launch/validate-publish-prod.md) dans le guide de l’utilisateur d’implémentation.
* Votre compte est un compte administrateur produit Analytics ou il appartient à un profil produit ayant accès aux flux de données.

## Procédure de démarrage

1. Connectez-vous à [experiencecloud.adobe.com](https://experiencecloud.adobe.com) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur l’icône à 9 carrés dans l’angle supérieur droit, puis sur le logo Analytics coloré.
3. Dans la barre de navigation en haut de l’écran, accédez à Admin > Flux de données.
4. Cliquez sur [!UICONTROL Ajouter]. Une nouvelle page comportant les trois catégories principales apparaît : [!UICONTROL Informations sur le flux], [!UICONTROL Destination], et [!UICONTROL Définitions des colonnes de données].
5. Remplissez les champs [!UICONTROL Informations sur le flux].
   * Nom : le nom que vous souhaitez, par exemple « Flux de données de test ».
   * Suite de rapports : sélectionnez la suite de rapports souhaitée.
   * Envoyer par courrier électronique une fois terminé : saisissez votre adresse électronique.
   * Intervalle du flux : sélectionnez l’intervalle souhaité (horaire ou quotidien).
   * Traitement du délai : peut être laissé sur [!UICONTROL pas de délai].
   * Dates de début et de fin : sélectionnez une date de début quelques jours auparavant et aujourd’hui comme date de fin.
6. Remplissez les champs [!UICONTROL Destination].
   * Type : FTP
   * Hôte : saisissez l’URL de destination FTP de votre choix. Par exemple : `ftp://ftp.omniture.com`.
   * Chemin d’accès : peut être laissé vide
   * Nom d’utilisateur : saisissez le nom d’utilisateur pour vous connecter au site FTP.
   * Mot de passe et mot de passe de confirmation : saisissez le mot de passe de connexion au site FTP.
7. Remplissez les [!UICONTROL définitions des colonnes de données].
   * Sélectionnez le dernier modèle « Toutes les Adobe columns » dans le menu déroulant.
   * Format de compression : Gzip
   * Type de groupement : plusieurs fichiers
   * Manifeste : aucun fichier
8. Cliquez sur [!UICONTROL Enregistrer] en haut à droite.
9. Une fois enregistré, le traitement des données historiques commence. Une fois le traitement des données terminé pour une journée, le fichier est placé sur le site FTP.
10. Connectez-vous au site FTP en utilisant Windows Explorer ou un client FTP dédié.
11. Téléchargez le fichier de flux de données compressé sur votre machine locale.
12. Décompressez le fichier comprimé à l’aide d’un programme qui prend en charge les extensions de fichier `.tar.gz`.
13. Ouvrez le fichier `hit_data.tsv` dans votre application de tableur ou de base de données de votre choix pour afficher les données brutes pour cette journée.

## Étapes suivantes

Une fois que vous avez compris le flux de travail de base permettant d’obtenir des flux de données, vous pouvez travailler avec des équipes au sein de votre entreprise pour stocker ou ingérer les données de base dans une base de données.

* [Créer un flux de données](create-feed.md) : informations techniques relatives à la création d’un flux de données, expliquant les champs individuels de manière plus détaillée
* [Gérer les flux de données](df-manage-feeds.md) : découvrez-en plus sur la navigation dans l’interface des flux de données
* [Contenu du flux de données](c-df-contents/datafeeds-contents.md) : comprendre ce qui se trouve dans le fichier compressé
* [Définitions des colonnes de données](c-df-contents/datafeeds-reference.md) : une liste complète de l’ensemble des colonnes disponibles

## Ressources supplémentaires

Vidéo relative à la navigation dans l’interface des flux de données :

> [!VIDEO](https://www.youtube.com/watch?v=m_fb--gNtR4)
