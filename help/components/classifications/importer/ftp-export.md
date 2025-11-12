---
title: Exportation des données de classification via FTP
description: L’exportation FTP offre plus de flexibilité au niveau des téléchargements de jeux de données. Cela concerne notamment le téléchargement de données à partir de plusieurs suites de rapports et le téléchargement de fichiers de jeux de données comportant plus de 50 000 lignes de données.
feature: Classifications
exl-id: 6f97f0b2-1a04-407f-9df9-8715da52037d
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 68%

---

# Exportation FTP (héritée)

{{classification-importer-deprecation}}

L’option FTP offre davantage de souplesse lors du téléchargement des jeux de données. Elle permet notamment de télécharger des données provenant de plusieurs suites de rapports et des fichiers de jeu de données contenant plus de 50 000 lignes. Avant de télécharger des données de classification via FTP, vous devez créer un compte FTP.

Tenez compte des problèmes suivants lors de l’application des filtres de données :

* Vous pouvez utiliser des caractères génériques lors de la définition du filtre de données. Utilisez un astérisque `*` pour mettre en correspondance zéro ou plusieurs caractères ou un point d’interrogation `?` pour mettre en correspondance un caractère exactement. Utilisez `?*` pour mettre en correspondance un ou plusieurs caractères.
* En règle générale, lors de l’application des deux types de filtres de données à un téléchargement, seules les lignes correspondant aux deux règles sont téléchargées. Toutefois, les exceptions suivantes s’appliquent :
   * Si Lignes avec colonne vides = Toutes les colonnes, toutes les colonnes vides à l’exception de celle qui est indiquée dans la première règle sont passées en revue. Cette exception garantit que l’outil télécharge toute ligne avec une colonne correspondant à la première règle dont toutes les autres colonnes sont vides.
   * Lors du téléchargement de lignes de données sur la base de colonnes vides, toutes les colonnes vides, à l’exception de celles spécifiées dans la première règle, sont vérifiées.
   * Si la même colonne est spécifiée pour les deux règles de filtrage (il est presque impossible de répondre aux deux critères), seules les lignes correspondant à la première règle sont téléchargées.
   * Les exportations FTP sont limitées à 30 colonnes.

## Exporter des classifications via FTP

Ces étapes décrivent la procédure d’exportation (téléchargement) de classifications à partir d’Adobe Analytics via FTP.

1. Créer un compte FTP.
1. Accédez à [!UICONTROL Admin] > [!UICONTROL Importateur de classifications].
1. Cliquez sur l’onglet **[!UICONTROL Importation FTP]**.
1. Configurez les champs pour l’exportation FTP.
1. Cliquez sur **[!UICONTROL Exporter un fichier]**.
1. Enregistrez le jeu de données sur votre système local.

## Descriptions des champs

| Élément | Descriptions |
| --- | --- |
| [!UICONTROL Sélectionner une suite de rapports] | Sélectionnez la suite de rapports à partir de laquelle vous souhaitez exporter les données de rapport. |
| [!UICONTROL Données à classer ] | Dans le menu déroulant, sélectionnez le jeu de données à classer. |
| [!UICONTROL Sélectionner le nombre de lignes] | Indiquez le nombre de lignes de données à exporter.<ul><li>Sélectionnez **[!UICONTROL Tous]** pour télécharger toutes les données de rapport.</li><li>Sélectionnez **[!UICONTROL Limiter les lignes de données à]** si vous voulez indiquer un nombre spécifique de lignes à télécharger.</li></ul> |
| [!UICONTROL Filtrer par date de réception] | (Facultatif) Filtrez les données selon la date de réception. Indiquez la période pour laquelle vous souhaitez télécharger les données. |
| [!UICONTROL Appliquer un filtre de données] | (Facultatif) Filtrez le jeu de données selon des critères de données. Vous pouvez filtrer le téléchargement pour inclure des lignes de données contenant une valeur spécifique ou des valeurs de colonnes non attribuées (classification). |
| [!UICONTROL Filtre de date] | (Facultatif) Filtrez les données par données de campagne. Vous pouvez télécharger uniquement les données des campagnes actives ou sélectionner des campagnes qui commencent (ou se terminent) à une période spécifique. |
| [!UICONTROL Exporter Numérique 2] | Vous pouvez importer les classifications numériques 2 dans le système à l’aide de l’importateur. Les classifications numériques 2 s’avèrent utiles lorsque les variables de différents articles changent de temps à autre, comme les valeurs de coût et de budget pour le rapport Canal marketing. |
| [!UICONTROL Compte FTP] | Spécifiez les informations du serveur FTP où Adobe doit télécharger le fichier de données, dont le nom d’hôte et le port, le chemin d’accès au répertoire de destination, le nom d’utilisateur et le mot de passe. |
| [!UICONTROL Notification] | Indiquez l’adresse e-mail à laquelle doivent être envoyées les notifications concernant ce téléchargement FTP. |
| [!UICONTROL Encodage] | Sélectionnez le codage des caractères pour le fichier de données. Le format de codage par défaut est soit UTF-8, soit ISO-8859-1, selon le code qui a été téléchargé pour la classification. UTF-8 vers UTF-16 convertit les classifications codées UTF-8 en codage UTF-16. La norme ISO-8859-1 en UTF-16 convertit vos classifications codées ISO-8859-1 en codage UTF-16.<br>**Remarque :** si vous choisissez de convertir au format UTF-16, le codage source doit correspondre au codage du chargement d’origine, faute de quoi vous risquez d’obtenir des résultats inattendus. Nous vous recommandons de coder tous les fichiers chargés au format UTF-8 sans nomenclature. |
