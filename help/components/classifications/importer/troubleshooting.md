---
title: Dépannage de l’importateur de classifications
description: Problèmes de téléchargement courants lors de l’utilisation de l’importateur de classifications.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 12%

---


# Dépannage de l’importateur de classifications

Problèmes les plus courants lors du transfert de données de classification vers l’Adobe.

## Format ou extension de fichier incorrect

Les classifications nécessitent un type et un format de fichier spécifiques pour être transférées avec succès. S’il n’est pas enregistré correctement, il génère une erreur et ne traite aucune ligne. L’erreur renvoyée est souvent *&quot;La première colonne doit être la clé&quot;*, mais peut être n’importe quel nombre d’erreurs. Assurez-vous de vérifier les éléments suivants :

* **Téléchargement d’une feuille de calcul (.xlsx) au lieu d’un fichier**.tab ou .txt : Vous pouvez obtenir le message d’erreur *&quot;La première colonne doit être la clé&quot;* lorsque vous téléchargez des fichiers de classification dans un format incorrect. L’importateur de classifications ne sait pas comment gérer les fichiers .xls ou .xlsx. Dans la boîte de dialogue Enregistrer sous d&#39;Excel, définissez le type Enregistrer sous correct :
   * Sous Windows, utilisez le format de fichier `Text (Tab delimited) (*.txt)`
   * Sous Mac, utilisez le format de fichier `Windows Formatted Text`.
* **Modification de l’extension de nom de fichier après son enregistrement en tant que classeur**: La tentative de renommer directement une extension de fichier génère un classeur non valide. Utilisez uniquement la fonction Enregistrer sous d&#39;Excel ou modifiez les classifications dans un éditeur de texte tel que Notepad++.
* **Utilisation d’extensions** majuscules : Les extensions en majuscules (par exemple `fileupload.TXT`) ne fonctionnent pas. Rename the file to a lowercase extension (`fileupload.txt`).
* **Codage** de caractères non concordant : Assurez-vous que le codage du téléchargement de classification enregistré correspond au codage d’origine lorsque le modèle a été téléchargé. Si vous téléchargez un fichier UTF-16 alors qu’il était initialement codé en UTF-8, les téléchargements produisent des résultats inattendus. adobe recommande de télécharger des fichiers au format UTF-8 sans marque d’ordre des octets.

## Contenu du fichier non valide

Si le fichier téléchargé est correctement formaté, le chargeur tente d’importer autant de lignes valides que possible. Problèmes courants liés aux données de classification :

* **Lignes déjà classées**: Lorsque vous tentez de télécharger des lignes qui sont déjà classées avec la même valeur, l’importateur renvoie des lignes qui n’ont pas eu d’effet. Ce résultat est attendu car les classifications ne reclassent pas une valeur clé avec la même classification. Il s’agit d’une notification et non d’une erreur. Ne vous en inquiétez pas si vous ne modifiez pas toutes les lignes d’un fichier d’exportation. L’Adobe recommande de télécharger uniquement les lignes modifiées.
* **L’en-tête ne correspond pas à la variable en cours de téléchargement**: Si vous téléchargez un modèle de classification pour la dimension Code de suivi et tentez de le télécharger vers une classification d’eVar, il échoue. N’utilisez que des fichiers d’exportation pour les variables spécifiques à partir desquelles ils ont été exportés.
* **Une clé ou une valeur de classification contient la valeur 0**: Les classifications ne peuvent pas différencier la valeur 0 d’une cellule vide, de sorte qu’elle ne peut pas classer cette valeur. Voir FAQ [sur les](../faq.md)classifications.
* **Le fichier de classification contient des virgules ou des caractères** spéciaux : Voir FAQ [sur les](../faq.md)classifications.
* **Onglets supplémentaires dans le fichier** téléchargé : Parfois, lors de la modification de fichiers de classification, un onglet supplémentaire peut être glissé accidentellement. Chaque ligne nécessite un nombre identique de tabulations pour un traitement correct. Pour rechercher des onglets supplémentaires dans le fichier, mettez en surbrillance tout le texte d’un éditeur de texte brut et assurez-vous qu’aucune rangée ne dispose d’espace supplémentaire à la fin.
* **Le fichier** contient des valeurs de clé de duplicata : Chaque valeur de clé ne peut avoir qu&#39;une seule classification par colonne. Si vous tentez de classer la même valeur plusieurs fois, l’importateur renvoie une erreur.
* **Les sous-classifications existent et sont mal configurées**: S’il existe des sous-classifications, vérifiez les éléments suivants :
   * Toutes les valeurs de sous-classification disposent d’une valeur de classification parente
   * Deux sous-classifications ne font pas référence à la même valeur de classification parente
* **Incohérence** de colonne : Vous pouvez obtenir le message d&#39;erreur *&quot;La clé en ligne comporte trop de colonnes&quot;* s&#39;il y a un nombre non valide de colonnes sur une ligne donnée. Par exemple, votre téléchargement de classification comporte 3 colonnes et la variable n’a qu’une seule classification. Validez votre fichier de téléchargement pour vous assurer que le nombre de colonnes n’est pas supérieur au nombre de classifications configurées pour cette variable.

## Résolution des problèmes d&#39;importation FTP

Les causes courantes suivantes expliquent que les classifications FTP ne traitent pas les fichiers téléchargés :

* **Fichier**.fin manquant : Créez un document de texte vide sur votre bureau et renommez l’extension de nom de fichier de .txt en .fin. Le nom de ce fichier .fin doit correspondre au nom du fichier de classification en question. Par exemple, si le nom du fichier FTP est `fileupload.tab`, nommez votre fichier .fin `fileupload.fin`. Une fois le fichier .fin téléchargé, les deux fichiers disparaissent.
* **Téléchargement du fichier .fin avant le fichier** de classification : Il arrive qu’un fichier .fin soit créé avant que le fichier de classifications ne soit téléchargé sur le site FTP. Le traitement peut échouer lorsque les fichiers sont téléchargés dans le désordre. Supprimez les deux fichiers, ajoutez d’abord le fichier de classification, puis le fichier .fin une fois le fichier de classification entièrement téléchargé.
* **La taille du fichier est trop importante**: L&#39;Adobe recommande de conserver la taille des fichiers de classification aussi petite que possible afin d&#39;assurer un traitement rapide.
* **Fichiers existants déjà en traitement**: Si plusieurs fichiers sont téléchargés pour la même variable et la même suite de rapports, l’ancien fichier cesse de s’exécuter en faveur de la nouvelle. Si vous téléchargez des classifications à l’aide de plusieurs fichiers, attendez la confirmation que le traitement des fichiers existants est terminé avant d’en télécharger de nouveaux.
* **Fichiers téléchargés non placés dans le répertoire** racine : Les fichiers téléchargés sur le site FTP du Adobe doivent être placés dans le répertoire racine. Si des fichiers d’importation de classification sont placés dans des sous-dossiers, ils ne sont ni sélectionnés ni traités.

Si vous rencontrez toujours des problèmes pour télécharger un fichier de classification, contactez le service à la clientèle de l’Adobe.
