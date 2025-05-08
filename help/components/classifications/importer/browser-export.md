---
title: Exportation navigateur
description: L’exportation du navigateur vous permet d’exporter des données de classification dans un fichier délimité par des tabulations.
feature: Classifications
exl-id: f4c709b2-f707-4e3c-82ba-6b43def3e698
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 99%

---

# Exportation navigateur (héritée)

L’exportation du navigateur vous permet d’exporter des données de classification dans un fichier délimité par des tabulations.

[!UICONTROL Admin] > [!UICONTROL Importateur de classifications]

Le fichier de jeu de données est un fichier de données délimité par des tabulations (extension de nom de fichier .tab) qui est pris en charge par la plupart des tableurs.

>[!NOTE]
>Les exportations de navigateur sont limitées à 30 colonnes.

## Descriptions des champs

| Élément | Descriptions |
| --- | --- |
| Sélectionner une suite de rapports | Sélectionnez la suite de rapports à partir de laquelle vous souhaitez exporter les données de rapport. |
| Données à classer  | Dans le menu déroulant, sélectionnez le jeu de données à classer. |
| Sélectionner le nombre de lignes | Indiquez le nombre de lignes de données à exporter.<ul><li>Sélectionnez **[!UICONTROL Toutes]** pour télécharger toutes les données de rapport (jusqu’à 50 000 lignes).</li><li>Sélectionnez **[!UICONTROL Limiter les lignes de données à]** si vous voulez indiquer un nombre spécifique de lignes à télécharger.</li></ul>Si vous voulez télécharger plus de 50 000 lignes de données, utilisez l’option de téléchargement FTP. |
| Filtrer par date de réception | (Facultatif) Filtrez les données en fonction de la date de réception. Spécifiez, dans ce cas, la plage de dates pour laquelle vous voulez télécharger les données. |
| Appliquer un filtre de données | (Facultatif) Filtrez le jeu de données selon certains critères. Vous pouvez filtrer le téléchargement pour inclure des lignes de données contenant une valeur spécifique ou des valeurs de colonnes non attribuées (classification). Tenez compte des problèmes suivants lorsque vous appliquez des filtres de données :<ul><li>Vous pouvez utiliser des caractères génériques lors de la définition du filtre des données. Utilisez un astérisque pour mettre en correspondance zéro ou plusieurs caractères ou un point d’interrogation `?` pour ne mettre en correspondance qu’un seul caractère. Utilisez `?*` pour mettre en correspondance un ou plusieurs caractères.</li><li>En règle générale, lorsque vous appliquez les deux types de filtres de données, seules les lignes qui répondent aux deux règles sont téléchargées. Les exceptions suivantes s’appliquent toutefois :<ul><li>Si Lignes avec colonne vides = Toutes les colonnes, toutes les colonnes vides à l’exception de celle qui est indiquée dans la première règle sont passées en revue. Cette exception permet de s’assurer que le système télécharge une ligne avec une colonne correspondant à la première règle et dont toutes les autres colonnes sont vides.</li><li>Lorsque vous téléchargez des lignes de données sur la base de colonnes vides, toutes les colonnes, à l’exception de celles qui sont indiquées dans la première règle, sont passées en revue.</li><li>Si la même colonne est spécifiée dans les deux règles de filtre (il est pratiquement impossible de respecter les deux critères), seules les colonnes correspondant à la première règle sont téléchargées.</li></ul></ul> |
| Filtre de données | (Facultatif) Filtrez les données par données de campagne. Vous pouvez télécharger uniquement les données des campagnes actives ou sélectionner des campagnes qui ont commencé (ou se sont terminées) à une date spécifique.<br>**Important** : cette option n’est pas disponible pour les suites de rapports activées pour la nouvelle architecture de classification. |
| Exporter Numérique 2 | Vous pouvez importer les classifications numériques 2 dans le système à l’aide de l’importateur. Les classifications numériques 2 s’avèrent utiles lorsque les variables de différents articles changent de temps à autre, comme les valeurs de coût et de budget pour le rapport Canal marketing. Voir Classifications numériques 2 pour plus d’informations sur le chargement de données utilisant les classifications numériques 2. |
| Encodage | Sélectionnez le codage des caractères pour le fichier de données. Le format de codage par défaut est soit UTF-8, soit ISO-8859-1, selon le code qui a été téléchargé pour la classification. UTF-8 vers UTF-16 convertit les classifications codées UTF-8 en codage UTF-16. ISO-8859-1 vers UTF-16 convertit les classifications codées ISO-8859-1 en codage UTF-16.<br>**Remarque :** Si vous choisissez de convertir en UTF-16, le codage source doit correspondre au codage du téléchargement d’origine. Sinon, vous pourriez obtenir des résultats inattendus. Nous vous recommandons de coder tous les fichiers téléchargés en UTF-8 sans nomenclature. |
| Production de devis | Indique la version 2.1 pour le fichier de classification. Ce paramètre place les caractères spéciaux entre guillemets pour garantir que les exportations s’effectuent dans Excel lorsque les valeurs eVar contiennent un saut de ligne. Vous pouvez identifier si un fichier de classification appartient à la version 2.1 en ouvrant le fichier téléchargé. v2.1 s’affiche dans l’en-tête. Par exemple : `## SC SiteCatalyst SAINT Import File v:2.1` |

## Exporter des données de classification à l’aide du navigateur

1. Cliquez sur [!UICONTROL Admin] > [!UICONTROL Importateur de classifications].
1. Cliquez sur l’onglet [!UICONTROL Exportation navigateur].
1. Spécifiez les détails du jeu de données.
1. Cliquez sur [!UICONTROL Exporter un fichier].
1. Enregistrez le jeu de données sur votre système local.
