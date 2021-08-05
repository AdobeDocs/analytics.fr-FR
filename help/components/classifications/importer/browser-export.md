---
title: Exportation navigateur
description: L’exportation par navigateur vous permet d’exporter les données de classification vers un fichier délimité par des tabulations.
source-git-commit: 8a5c7309b5d4061b2e3241219d9bdb1521294535
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 74%

---


# Exportation navigateur

L’exportation par navigateur vous permet d’exporter les données de classification vers un fichier délimité par des tabulations.

Admin > Importateur de classifications

Le fichier d’ensemble de données est un fichier de données délimité par des tabulations (extension de nom de fichier .tab) qui est pris en charge par la plupart des tableurs.

>[!NOTE]
>Les exportations navigateur sont limitées à 30 colonnes.

## Descriptions des champs

| Élément | Descriptions |
| --- | --- |
| Sélectionner une suite de rapports | Sélectionnez la suite de rapports à partir de laquelle vous souhaitez exporter les données de rapport. |
| Données à classer  | Dans le menu déroulant, sélectionnez le jeu de données à classer. |
| Sélectionner le nombre de lignes | Indiquez le nombre de lignes de données à exporter.<ul><li>Sélectionnez **[!UICONTROL Toutes]** pour télécharger toutes les données de rapport (jusqu’à 50 000 lignes).</li><li>Sélectionnez **[!UICONTROL Limiter les lignes de données à]** si vous voulez indiquer un nombre spécifique de lignes à télécharger.</li></ul>Si vous souhaitez télécharger plus de 50 000 lignes de données, utilisez l’option de téléchargement FTP. |
| Filtrer par date de réception | (Facultatif) Filtrez les données en fonction de la date de réception. Spécifiez, dans ce cas, la plage de dates pour laquelle vous voulez télécharger les données. |
| Appliquer un filtre de données | (Facultatif) Filtrez le jeu de données selon certains critères. Vous pouvez filtrer le téléchargement pour inclure des lignes de données contenant une valeur spécifique ou des valeurs de colonnes non affectées (classification). Tenez compte des problèmes suivants lorsque vous appliquez des filtres de données :<ul><li>Vous pouvez utiliser des caractères génériques lors de la définition du filtre des données. Utilisez un astérisque pour ne faire correspondre aucun ou plusieurs caractères et un point d’interrogation `?` pour ne faire correspondre qu’un seul caractère. Utilisez `?*` pour faire correspondre un ou plusieurs caractères.</li><li>En règle générale, lorsque vous appliquez les deux types de filtres de données, seules les lignes qui répondent aux deux règles sont téléchargées. Les exceptions suivantes s’appliquent toutefois :<ul><li>Si Lignes avec colonne vides = Toutes les colonnes, toutes les colonnes vides à l’exception de celle qui est indiquée dans la première règle sont passées en revue. Cette exception permet de s’assurer que le système télécharge une ligne avec une colonne correspondant à la première règle et dont toutes les autres colonnes sont vides.</li><li>Lorsque vous téléchargez des lignes de données sur la base de colonnes vides, toutes les colonnes, à l’exception de celles qui sont indiquées dans la première règle, sont passées en revue.</li><li>Si la même colonne est spécifiée dans les deux règles de filtre (il est pratiquement impossible de respecter les deux critères), seules les colonnes correspondant à la première règle sont téléchargées.</li></ul></ul> |
| Filtre de données | (Facultatif) Filtrez les données par données de campagne. Vous pouvez télécharger uniquement les données des campagnes actives ou sélectionner des campagnes qui ont commencé (ou se sont terminées) à une date spécifique.<br>**Important** : Cette option n’est pas disponible pour les suites de rapports activées pour la nouvelle architecture de classification. |

