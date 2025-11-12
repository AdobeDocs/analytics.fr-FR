---
title: Exportation navigateur
description: L’exportation du navigateur vous permet d’exporter des données de classification dans un fichier délimité par des tabulations.
feature: Classifications
exl-id: f4c709b2-f707-4e3c-82ba-6b43def3e698
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 60%

---

# Exportation navigateur (héritée)

{{classification-importer-deprecation}}

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
| Filtrer par date de réception | (Facultatif) Filtrez les données selon la date de réception. Indiquez la période pour laquelle vous souhaitez télécharger les données. |
| Appliquer un filtre de données | (Facultatif) Filtrez le jeu de données selon des critères de données. Vous pouvez filtrer le téléchargement pour inclure des lignes de données contenant une valeur spécifique ou des valeurs de colonnes non attribuées (classification). Tenez compte des problèmes suivants lors de l’application des filtres de données :<ul><li>Vous pouvez utiliser des caractères génériques lors de la définition du filtre de données. Utilisez un astérisque pour mettre en correspondance zéro ou plusieurs caractères ou un point d’interrogation `?` pour ne mettre en correspondance qu’un seul caractère. Utilisez `?*` pour mettre en correspondance un ou plusieurs caractères.</li><li>En règle générale, lors de l’application des deux types de filtres de données à un téléchargement, seules les lignes correspondant aux deux règles sont téléchargées. Toutefois, les exceptions suivantes s’appliquent :<ul><li>Si Lignes avec colonne vides = Toutes les colonnes, toutes les colonnes vides à l’exception de celle qui est indiquée dans la première règle sont passées en revue. Cette exception garantit que le système télécharge toute ligne avec une colonne correspondant à la première règle dont toutes les autres colonnes sont vides.</li><li>Lors du téléchargement de lignes de données sur la base de colonnes vides, toutes les colonnes vides, à l’exception de celles spécifiées dans la première règle, sont vérifiées.</li><li>Si la même colonne est spécifiée pour les deux règles de filtrage (il est presque impossible de répondre aux deux critères), seules les lignes correspondant à la première règle sont téléchargées.</li></ul></ul> |
| Filtre de données | (Facultatif) Filtrez les données par données de campagne. Vous pouvez télécharger uniquement les données des campagnes actives ou sélectionner les campagnes qui ont commencé (ou se sont terminées) à une période spécifique.<br>**Important** : cette option n’est pas disponible pour les suites de rapports activées pour la nouvelle architecture de classification. |
| Exporter Numérique 2 | Vous pouvez importer les classifications numériques 2 dans le système à l’aide de l’importateur. Les classifications numériques 2 s’avèrent utiles lorsque les variables de différents articles changent de temps à autre, comme les valeurs de coût et de budget pour le rapport Canal marketing. Voir Classifications numériques 2 pour plus d’informations sur le chargement de données utilisant les classifications numériques 2. |
| Encodage | Sélectionnez le codage des caractères pour le fichier de données. Le format de codage par défaut est soit UTF-8, soit ISO-8859-1, selon le code qui a été téléchargé pour la classification. UTF-8 vers UTF-16 convertit les classifications codées UTF-8 en codage UTF-16. La norme ISO-8859-1 en UTF-16 convertit vos classifications codées ISO-8859-1 en codage UTF-16.<br>**Remarque :** si vous choisissez de convertir au format UTF-16, le codage source doit correspondre au codage du chargement d’origine, faute de quoi vous risquez d’obtenir des résultats inattendus. Nous vous recommandons de coder tous les fichiers chargés au format UTF-8 sans nomenclature. |
| Sortie de devis | Spécifie la version 2.1 du fichier de classification. Ce paramètre place les caractères spéciaux entre guillemets pour garantir que les exportations s’effectuent dans Excel lorsque les valeurs eVar contiennent un saut de ligne. Vous pouvez déterminer si un fichier de classification est la version 2.1 en ouvrant le fichier téléchargé. La version v2.1 s’affiche dans l’en-tête. Par exemple : `## SC SiteCatalyst SAINT Import File v:2.1` |

## Exporter des données de classification à l’aide du navigateur

1. Cliquez sur [!UICONTROL Admin] > [!UICONTROL Importateur de classifications].
1. Cliquez sur l’onglet [!UICONTROL Exportation navigateur].
1. Spécifiez les détails du jeu de données.
1. Cliquez sur [!UICONTROL Exporter un fichier].
1. Enregistrez le jeu de données sur votre système local.
