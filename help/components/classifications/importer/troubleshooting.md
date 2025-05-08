---
title: Résolution des problèmes de l’importateur de classifications
description: Problèmes de chargement courants lors de l’utilisation de l’importateur de classifications.
feature: Classifications
exl-id: de3e9eca-9264-4711-b73a-4a1a3dd16715
source-git-commit: 04c626b1159be3e61569e462bf9d12957bd2a333
workflow-type: tm+mt
source-wordcount: '875'
ht-degree: 96%

---

# Résolution des problèmes de l’importateur de classifications

Les problèmes les plus courants lors du chargement de données de classification vers Adobe.

## Format ou extension de fichier incorrect

Les classifications nécessitent un type de fichier et un format spécifiques pour un chargement réussi. S’il n’est pas enregistré correctement, il génère une erreur et ne traite aucune ligne. L’erreur renvoyée est souvent *« La première colonne doit être la clé »*, mais le nombre d’erreurs peut varier. Assurez-vous de vérifier les éléments suivants :

* **Téléchargement dʼune feuille de calcul (.xlsx) au lieu dʼun fichier .tab ou .txt** : vous pouvez obtenir le message dʼerreur *« La première colonne doit être la clé »* lorsque vous téléchargez des fichiers de classification dans un format incorrect. Lʼimportateur de classifications ne sait pas comment gérer les fichiers .xls ou .xlsx. Dans la boîte de dialogue « Enregistrer sous » d’Excel, définissez le type Enregistrer sous adéquat :
   * Sous Windows, utilisez le format de fichier `Text (Tab delimited) (*.txt)`
   * Sous Mac, utilisez le format de fichier `Windows Formatted Text`.
* **Modification de l’extension de nom de fichier après son enregistrement en tant que classeur** : tenter de renommer directement une extension de fichier génère un classeur non valide. N’utilisez que la fonction Enregistrer sous d’Excel ou modifiez les classifications dans un éditeur de texte tel que Notepad++.
* **Utilisation d’extensions en majuscules** : les extensions en majuscules (telles que `fileupload.TXT`) ne fonctionnent pas. Renommez le fichier afin que son extension soit en minuscules (`fileupload.txt`).
* **Encodage de caractères discordants** : veillez à ce que l’encodage du transfert de classification enregistré corresponde à l’encodage d’origine lors du téléchargement du modèle. Si vous chargez un fichier UTF-16 alors que celui-ci était à l’origine encodé en UTF-8, les chargements produisent des résultats inattendus. Adobe recommande de charger des fichiers au format UTF-8 sans marque d’ordre d’octet.

## Contenu du fichier non valide

Si le fichier téléchargé est correctement formaté, le chargeur tente d’importer autant de lignes valides que possible. Problèmes courants liés aux données de classification :

* **Lignes déjà classées** : lors de la tentative de chargement de lignes déjà classées avec la même valeur, l’importateur renvoie des lignes sans effet. Ce résultat est attendu, car les classifications ne reclassent pas une valeur clé avec la même classification. Il s’agit d’une notification et non d’une erreur. Ne vous inquiétez pas si vous ne modifiez pas toutes les lignes d’un fichier d’exportation. Adobe recommande de charger uniquement les lignes modifiées.
* **L’en-tête ne correspond pas à la variable en cours de transfert** : si vous téléchargez un modèle de classification pour la dimension Code de suivi et tentez de le transférer dans une classification eVar, il échoue. N’utilisez que des fichiers d’exportation pour les variables spécifiques à partir desquelles ils ont été exportés.
* **Une valeur de clé ou de classification contient la valeur 0** : les classifications ne peuvent pas différencier la valeur 0 d’une cellule vide. Elles ne peuvent donc pas classer cette valeur. Consultez la [FAQ sur l’importateur de classifications](importer-faq.md) pour plus d’informations.
* **Le fichier de classification contient des virgules ou des caractères spéciaux** : consultez la [FAQ sur l’importateur de classifications](importer-faq.md) pour plus d’informations sur la manière d’échapper les valeurs.
* **Des tabulations supplémentaires dans le fichier chargé** : parfois, lors de la modification de fichiers de classification, une tabulation supplémentaire peut être accidentellement insérée. Chaque ligne nécessite un nombre identique de tabulations pour un traitement correct. Pour rechercher des tabulations supplémentaires dans le fichier, mettez en surbrillance tout le texte d’un éditeur de texte brut et assurez-vous qu’aucune ligne ne contient d’espace supplémentaire à la fin.
* **Des valeurs de clé en double existent dans le fichier** : chaque valeur de clé ne peut avoir qu’une seule classification par colonne. Si vous tentez de classer la même valeur plusieurs fois, l’importateur renvoie une erreur.
* **Des sous-classifications existent et sont mal configurées** : si des sous-classifications existent, vérifiez les points suivants :
   * Toutes les valeurs de sous-classification disposent d’une valeur de classification parente
   * Deux sous-classifications ne font pas référence à la même valeur de classification parente
* **Incohérence du nombre de colonnes** : vous pouvez obtenir le message dʼerreur *« La clé à la ligne comporte trop de colonnes »* sʼil y a un nombre non valide de colonnes sur une ligne donnée. Par exemple, votre téléchargement de classification comporte 3 colonnes et la variable nʼa quʼune seule classification. Validez votre fichier de téléchargement pour vous assurer que le nombre de colonnes nʼest pas supérieur au nombre de classifications configurées pour cette variable.

## Résolution des problèmes d’importation FTP

Voici les causes courantes pour lesquelles les classifications FTP ne traitent pas les fichiers chargés :

* **Fichier .fin manquant** : créez un document de texte vide sur votre bureau et renommez l’extension de nom de fichier en remplaçant .txt par .fin. Le nom de ce fichier .fin doit correspondre au nom du fichier de classification en question. Par exemple, si le nom du fichier FTP est `fileupload.tab`, nommez votre fichier .fin `fileupload.fin`. Une fois le fichier .fin chargé, les deux fichiers disparaissent.
* **Chargement du fichier .fin avant le fichier de classification** : il arrive qu’un fichier .fin soit créé avant que le fichier de classifications ne soit chargé sur le site FTP. Le traitement peut échouer lorsque les fichiers sont chargés dans le mauvais ordre. Supprimez les deux fichiers, ajoutez d’abord le fichier de classification, puis le fichier .fin une fois le fichier de classification entièrement chargé.
* **La taille du fichier est trop importante** : Adobe recommande de limiter au maximum la taille des fichiers de classification afin d’assurer un traitement rapide.
* **Fichiers existants déjà en traitement** : si plusieurs fichiers sont chargés pour la même variable et la même suite de rapports, le traitement de l’ancien fichier est suspendu au profit du nouveau fichier. Si vous chargez des classifications à l’aide de plusieurs fichiers, attendez la confirmation que le traitement des fichiers existants est terminé avant d’en charger de nouveaux.
* **Fichiers chargés qui ne sont pas placés dans le répertoire racine** : les fichiers chargés sur le site FTP d’Adobe doivent être placés dans le répertoire racine. Si des fichiers d’importation de classification sont placés dans des sous-dossiers, ils ne sont ni sélectionnés ni traités.

Si vous rencontrez encore des problèmes lors du chargement d’un fichier de classification, contactez l’assistance clientèle d’Adobe.
