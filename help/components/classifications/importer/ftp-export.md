---
title: Exportation des données de classification par FTP
description: L’exportation FTP offre davantage de flexibilité avec les téléchargements d’ensemble de données, notamment le téléchargement de données à partir de plusieurs suites de rapports et le téléchargement de fichiers d’ensemble de données de plus de 50 000 lignes de données.
source-git-commit: 32196fc76b2743679516a00f86c4912fac0bb3cf
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 76%

---


# Exportation des données de classification par FTP

L’option FTP offre davantage de souplesse lors du téléchargement des jeux de données. Elle permet notamment de télécharger des données provenant de plusieurs suites de rapports et des fichiers de jeu de données contenant plus de 50 000 lignes. Avant de télécharger des données de classification via FTP, vous devez créer un compte FTP.

Tenez compte des problèmes suivants lorsque vous appliquez des filtres de données :

* Vous pouvez utiliser des caractères génériques lors de la définition du filtre des données. Utilisez un astérisque `*` pour faire correspondre zéro ou plusieurs caractères et un point d’interrogation `?` pour correspondre exactement à un caractère. Utilisez `?*` pour faire correspondre un ou plusieurs caractères.
* En règle générale, lorsque vous appliquez les deux types de filtres de données, seules les lignes qui répondent aux deux règles sont téléchargées. Les exceptions suivantes s’appliquent toutefois :
   * Si Lignes avec colonne vides = Toutes les colonnes, toutes les colonnes vides à l’exception de celle qui est indiquée dans la première règle sont passées en revue. Cette exception permet de s’assurer que l’outil télécharge une ligne avec une colonne correspondant à la première règle et dont toutes les autres colonnes sont vides.
   * Lorsque vous téléchargez des lignes de données sur la base de colonnes vides, toutes les colonnes, à l’exception de celles qui sont indiquées dans la première règle, sont passées en revue.
   * Si la même colonne est spécifiée dans les deux règles de filtre (il est pratiquement impossible de respecter les deux critères), seules les colonnes correspondant à la première règle sont téléchargées.
   * Les exportations FTP sont limitées à 30 colonnes.

## Exporter des classifications via FTP

Ces étapes décrivent comment exporter (télécharger) des classifications d’Adobe Analytics via FTP.

1. Créer un compte FTP.
1. Accédez à [!UICONTROL Admin] > [!UICONTROL Importateur de classifications].
1. Cliquez sur l’onglet **[!UICONTROL Importation FTP]** .
1. Configurez les champs de l’exportation FTP.
1. Cliquez sur **[!UICONTROL Exporter un fichier]**.
1. Enregistrez le jeu de données sur votre système local.

## Descriptions des champs

| Élément | Descriptions |
| --- | --- |
| [!UICONTROL Sélectionner une suite de rapports] | Sélectionnez la suite de rapports à partir de laquelle vous souhaitez exporter les données de rapport. |
| [!UICONTROL Données à classer ] | Dans le menu déroulant, sélectionnez le jeu de données à classer. |
| [!UICONTROL Sélectionner le nombre de lignes] | Indiquez le nombre de lignes de données à exporter.<ul><li>Sélectionnez **[!UICONTROL Tous]** pour télécharger toutes les données de rapport.</li><li>Sélectionnez **[!UICONTROL Limiter les lignes de données à]** si vous voulez indiquer un nombre spécifique de lignes à télécharger.</li></ul> |
| [!UICONTROL Filtrer par date de réception] | (Facultatif) Filtrez les données en fonction de la date de réception. Spécifiez, dans ce cas, la plage de dates pour laquelle vous voulez télécharger les données. |
| [!UICONTROL Appliquer un filtre de données] | (Facultatif) Filtrez le jeu de données selon certains critères. Vous pouvez filtrer le téléchargement pour inclure des lignes de données contenant une valeur spécifique ou des valeurs de colonnes non affectées (classification). |
| [!UICONTROL Filtre de date] | (Facultatif) Filtrez les données par données de campagne. Vous pouvez télécharger uniquement les données des principales campagnes ou sélectionner les campagnes qui commencent (ou se terminent) dans une période spécifique. |
| [!UICONTROL Exporter Numérique 2] | Vous pouvez importer des classifications numériques 2 dans le système à l’aide de l’importateur. Les classifications numériques 2 s’avèrent utiles lorsque les variables de différents articles changent de temps à autre, comme les valeurs de coût et de budget pour le rapport Canal marketing. |
| [!UICONTROL Compte FTP] | Spécifiez les informations du serveur FTP où Adobe doit télécharger le fichier de données, dont le nom d’hôte et le port, le chemin d’accès au répertoire de destination, le nom d’utilisateur et le mot de passe. |
| [!UICONTROL Notification] | Indiquez l’adresse de courriel à laquelle doivent être envoyées les notifications concernant ce téléchargement FTP. |
| [!UICONTROL Encodage] | Sélectionnez le codage des caractères pour le fichier de données. Le format de codage par défaut est soit UTF-8, soit ISO-8859-1, selon le code qui a été téléchargé pour la classification. UTF-8 vers UTF-16 convertit les classifications codées UTF-8 en codage UTF-16. ISO-8859-1 vers UTF-16 convertit les classifications codées ISO-8859-1 en codage UTF-16.<br>**Remarque :** Si vous choisissez de convertir en UTF-16, le codage source doit correspondre au codage du téléchargement d’origine. Sinon, vous pourriez obtenir des résultats inattendus. Nous vous recommandons de coder tous les fichiers téléchargés en UTF-8 sans nomenclature. |

