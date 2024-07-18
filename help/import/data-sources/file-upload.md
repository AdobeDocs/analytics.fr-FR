---
title: Transfert du fichier de sources de données vers Adobe
description: Processus de téléchargement d’un fichier de sources de données vers Adobe Analytics en vue de l’ingestion.
exl-id: 64e3cd70-b511-4c4e-abd0-94eb36bc3519
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 1%

---

# Transfert du fichier de sources de données vers Adobe

L’envoi d’un fichier de sources de données à l’Adobe implique un processus FTP authentifié type. Vous pouvez utiliser l’Explorateur Windows, le Finder ou un client FTP dédié pour télécharger les fichiers de votre choix vers l’emplacement FTP de l’Adobe.

Recherchez les informations d’identification FTP dans le [gestionnaire de sources de données](manage.md). Chaque source de données comporte un lien vers son **[!UICONTROL FTP Info]**. Chaque emplacement FTP est dédié à cette source de données spécifique ; vous ne pouvez pas utiliser le même emplacement FTP pour plusieurs sources de données.

Pour des raisons de sécurité, les emplacements FTP sans activité pendant plus de 30 jours sont désactivés.

## Le fichier `.fin`

L’inclusion d’un fichier `.fin` est un élément essentiel de l’ingestion réussie d’un fichier de sources de données. Ce fichier indique que le fichier de données est prêt pour le traitement. Si vous chargez un fichier de sources de données sans fichier `.fin` correspondant, Adobe ne traite jamais ces données.

Le fichier `.fin` possède les propriétés suivantes :

* Le fichier a une extension `.fin`. Assurez-vous que votre système d’exploitation vous permet d’afficher et de modifier des types de fichiers.
* Le fichier est vide. Ne stockez pas de données dans le fichier `.fin`.
* Le fichier porte exactement le même nom que le fichier de sources de données. Par exemple, si vous téléchargez un fichier de sources de données nommé `example.txt`, le fichier `.fin` **doit** être nommé `example.fin`. S’ils ne portent pas le même nom, Adobe ne traite jamais le fichier de sources de données.

Une fois que le fichier de source de données et le fichier `.fin` sont transférés sur le site FTP, Adobe traite le fichier. Ne téléchargez pas le fichier `.fin` tant que le fichier de sources de données n’a pas été entièrement transféré. Si le fichier `.fin` est téléchargé de manière prématurée, Adobe récupère et ingère le fichier partiellement téléchargé, ce qui peut entraîner des erreurs.

## Ordre de traitement

Si vous transférez plusieurs fichiers en même temps sur le site FTP, Adobe les ingère par ordre alphanumérique. Si votre entreprise nécessite l’ingestion de fichiers dans un ordre spécifique, assurez-vous que leurs noms de fichiers sont nommés de manière alphanumérique.

## Durée du traitement

Pour assurer le traitement des fichiers le plus rapide, Adobe recommande d’agréger les données de mesure sur une seule ligne par date. Par exemple, ce fichier de sources de données, bien qu’il soit valide, serait traité plus lentement :

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | | `1` | |
| `07/24/YYYY` | `red` | | | `1` |

Ce fichier sera traité plus rapidement, qui contient les mêmes données :

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `2` | `1` | `1` |
