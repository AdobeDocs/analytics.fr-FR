---
title: Création ou modification d’un flux de données
description: Découvrez comment créer ou modifier un flux de données.
translation-type: ht
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Création ou modification d’un flux de données

La création d’un flux de données permet à Adobe de savoir où envoyer les fichiers de données brutes et les éléments que vous souhaitez inclure dans chaque fichier. Cette page répertorie les paramètres individuels que vous pouvez personnaliser lorsque vous créez un flux de données.

Il est recommandé de posséder des connaissances élémentaires des flux de données avant de lire cette page. Consultez l’[aperçu des flux de données](data-feed-overview.md) pour vous assurer de répondre aux exigences en matière de création des flux de données.

## Champs d’informations sur les flux

* **Nom** : le nom du flux de données. Doit être unique au sein de la suite de rapports sélectionnée et peut comporter jusqu’à 255 caractères.
* **Suite de rapports :** la suite de rapports sur laquelle le flux de données est basé. Si plusieurs flux de données sont créés pour une même suite de rapports, ils doivent avoir des définitions de colonne différentes. Seules les suites de rapports source prennent en charge les flux de données ; les suites de rapports virtuelles ne sont pas prises en charge.
* **Envoyer par courrier électronique une fois terminé** : l’adresse électronique vers laquelle envoyer une notification lorsque le traitement d’un flux est terminé. L’adresse électronique doit être correctement formatée.
* **Intervalle du flux** : les flux horaires contiennent l’équivalent d’une seule heure de données. Les flux quotidiens contiennent l’équivalent d’une journée complète de données.
* **Traitement du délai** : patientez un certain temps avant de traiter un fichier de flux de données. Il peut être utile de mettre en place un délai pour donner aux appareils hors ligne la possibilité de se connecter et d’envoyer leurs données dans le cadre d’implémentations mobiles. Il est également possible d’utiliser un délai pour adapter les processus côté serveur de votre entreprise en ce qui concerne la gestion des fichiers traités précédemment. Dans la plupart des cas aucun délai n’est nécessaire. Un flux peut être se voir attribuer un délai pouvant aller jusqu’à 120 minutes.
* **Dates de début et de fin** : la date de début indique la première date pour laquelle vous souhaitez un flux de données. Définissez cette date dans le passé pour commencer immédiatement à traiter les flux de données des données historiques. Le traitement du flux se poursuit jusqu’à ce que la date de fin soit atteinte.
* **Flux continu** : cette case à cocher supprime la date de fin et permet à un flux de s’exécuter indéfiniment. Lorsqu’un flux termine le traitement de données historiques, un flux attend la fin de la collecte des données pour une heure ou un jour donné. Une fois l’heure ou le jour en question terminé, le traitement commence après le délai indiqué.

## Champs de destination

Les champs disponibles dans les champs de destination dépendent du type de destination.

### FTP

Les informations de flux de données peuvent être distribuées vers un emplacement FTP hébergé par Adobe ou par le client. Nécessite un hôte FTP, un nom d’utilisateur et un mot de passe. Utilisez le champ Chemin d’accès pour placer les fichiers de flux dans un dossier. Les dossiers doivent déjà exister ; les fichiers lancent une erreur si le chemin d’accès précisé n’existe pas.

![Infos FTP](assets/dest-ftp.jpg)

### SFTP

La prise en charge SFTP des flux de données est disponible. Nécessite un hôte SFTP, un nom d’utilisateur et un site de destination contenant une clé publique RSA ou DSA. Vous pouvez télécharger la clé publique appropriée à la création du flux.

![Infos SFTP](assets/dest-sftp.jpg)

### S3

Il est possible d’envoyer des flux directement vers des compartiments Amazon S3. Nécessite un nom de compartiment, un identifiant de clé d’accès et une clé secrète. Consultez les [conditions d’attribution de noms pour des compartiments Amazon S3](https://docs.aws.amazon.com/fr_fr/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html) dans les documents Amazon S3 pour plus d’informations.

![Informations S3](assets/dest-s3.jpg)

Les 11 régions standard AWS suivantes sont prises en charge (en utilisant l’algorithme de signature approprié si nécessaire) :

* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* eu-central-1
* eu-west-1
* sa-east-1

> [!NOTE] La région cn-north-1 n’est pas prise en charge.

### Azure Blob

Les flux de données prennent en charge les destinations Azure Blob. Nécessite un conteneur, un compte et une clé. Amazon chiffre automatiquement les données au repos. Les données que vous téléchargez sont automatiquement déchiffrées. Pour en savoir plus, consultez [Création d’un compte Azure Storage](https://docs.microsoft.com/fr-fr/azure/storage/common/storage-account-create?tabs=azure-portal#view-and-copy-storage-access-keys) dans la documentation Microsoft Azure.

![Informations sur Azure](assets/azure.png)

> [!NOTE] Vous devez mettre en œuvre votre propre processus pour gérer l’espace disque sur la destination de flux. Adobe ne supprime pas les données du serveur.

## Définitions des colonnes de données

Toutes les colonnes sont disponibles qu’elles contiennent des données ou non. Un flux de données doit inclure au moins une colonne.

* **Supprimer les caractères avec échappement** : au cours d’une collecte de données, certains caractères (comme les sauts de lignes) peuvent occasionner des erreurs. Cochez cette case si vous souhaitez retirer ces caractères des fichiers de flux.
* **Format de compression** : le type de compression utilisé. Fichiers de sortie Gzip au format `.tar.gz`. Fichiers de sortie Zip au format `.zip`.
* **Type de groupement** : un fichier unique sort le fichier `hit_data.tsv` dans un fichier unique pouvant être volumineux. La fonction plusieurs fichiers met en page vos données par blocs de 2 Go (non compressés). Si vous avez sélectionné plusieurs fichiers, mais que la taille des données non compressées pour la fenêtre de création de rapports est inférieure à 2 Go, un seul fichier est envoyé. Adobe recommande d’utiliser plusieurs fichiers pour la plupart des flux de données.
* **Modèles de colonnes** : lorsque vous créez plusieurs flux de données, Adobe vous recommande de créer un modèle de colonnes. La sélection d’un modèle de colonnes inclut automatiquement les colonnes indiquées dans le modèle. Adobe fournit également plusieurs modèles par défaut.
* **Colonnes disponibles** : Toutes les colonnes de données disponibles dans Adobe Analytics. Cliquez sur [!UICONTROL Toujours ajouter] pour inclure toutes les colonnes d’un flux de données.
* **Colonnes incluses** : les colonnes à inclure à un flux de données. Cliquez sur [!UICONTROL Tout supprimer] pour supprimer toutes les colonnes d’un flux de données.
* **Télécharger un fichier CSV** : télécharge un fichier CSV contenant toutes les colonnes incluses.
