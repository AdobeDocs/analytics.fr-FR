---
title: Chargement du fichier des sources de données vers Adobe
description: Processus de chargement d’un fichier de sources de données vers Adobe Analytics pour ingestion.
exl-id: 64e3cd70-b511-4c4e-abd0-94eb36bc3519
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 1%

---

# Chargement du fichier des sources de données vers Adobe

L’envoi d’un fichier de sources de données à Adobe implique un workflow FTP authentifié standard. Vous pouvez utiliser l’Explorateur Windows, le Finder ou un client FTP dédié pour charger les fichiers souhaités vers l’emplacement FTP d’Adobe.

Recherchez les informations d’identification FTP dans le [Gestionnaire des sources de données](manage.md). Chaque source de données possède un lien vers ses **[!UICONTROL informations FTP]**. Chaque emplacement FTP est dédié à cette source de données spécifique. Vous ne pouvez pas utiliser le même emplacement FTP pour plusieurs sources de données.

Pour des raisons de sécurité, les emplacements FTP sans activité pendant plus de 30 jours sont désactivés.

## Le fichier `.fin`

L’inclusion d’un fichier `.fin` est essentielle pour réussir l’ingestion d’un fichier de sources de données. Ce fichier indique à Adobe que le fichier de données est prêt à être traité. Si vous téléchargez un fichier de sources de données sans fichier `.fin` correspondant, Adobe ne traite jamais ces données.

Le fichier `.fin` possède les propriétés suivantes :

* Le fichier a une extension `.fin`. Assurez-vous que votre système d’exploitation vous permet d’afficher et de modifier les types de fichiers.
* Le fichier est vide. Ne stockez pas de données dans le fichier `.fin`.
* Le fichier porte exactement le même nom que le fichier de sources de données. Par exemple, si vous téléchargez un fichier de sources de données nommé `example.txt`, le fichier `.fin` **doit** doit être nommé `example.fin`. S’ils ne portent pas le même nom, Adobe ne traite jamais le fichier de sources de données.

Une fois le fichier de source de données et le fichier `.fin` chargés sur le site FTP, Adobe traite le fichier. Ne chargez pas le fichier `.fin` tant que le fichier des sources de données n’a pas été entièrement chargé. Si le fichier `.fin` est chargé prématurément, Adobe récupère et ingère le fichier partiellement chargé, générant ainsi d’éventuelles erreurs.

## Ordre de traitement

Si vous chargez plusieurs fichiers simultanément sur le site FTP, Adobe les ingère dans l’ordre alphanumérique. Si votre entreprise exige que les fichiers soient ingérés dans un ordre spécifique, assurez-vous que leurs noms de fichier sont nommés par ordre alphanumérique.

## Durée du traitement

Pour garantir le traitement le plus rapide des fichiers, Adobe recommande d’agréger les données de mesure en une seule ligne par date. Par exemple, ce fichier de sources de données, bien que valide, serait traité plus lentement :

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | | `1` | |
| `07/24/YYYY` | `red` | | | `1` |

Ce fichier est traité plus rapidement et contient les mêmes données :

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `2` | `1` | `1` |
