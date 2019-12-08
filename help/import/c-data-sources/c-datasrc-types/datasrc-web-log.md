---
description: Ces sources de données vous permettent d’importer des fichiers journaux de serveur Web standard.
subtopic: Data sources
title: Journal web
topic: Developer and implementation
uuid: a0efed57-6d1b-43d8-97ce-dc31009805e0
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Journal web

Ces sources de données vous permettent d’importer des fichiers journaux de serveur Web standard.

Les types courants suivants de journaux de serveur Web sont pris en charge :

| Nom de la colonne | Description |
|--- |--- |
| Journal courant NCSA | Valeur Apache par défaut |
| NCSA étendu (combiné) | Apache |
| Journal étendu W3C | Utilisé par IIS 4.0 et versions ultérieures |
| Journal Microsoft IIS | Utilisé par IIS 3.0 et versions antérieures |

Les principaux champs de fichier journal traités par la fonctionnalité Sources de données sont les suivants : adresse IP, date/heure de la requête et URL. Dans certains cas (format NCSA étendu, par exemple), la fonctionnalité Sources de données traite également les champs Référent et Agent utilisateur. 

Vous pouvez afficher les données du journal Web à l’aide des rapports marketing standard pour les pages vues, les visites et les visiteurs. Les mesures des rapports reposent principalement sur les cookies et les journaux de serveur Web sur l’adresse IP ; par conséquent, il est conseillé d’importer les journaux de serveur Web dans une suite de rapports distincte, spécifiquement prévue à cet effet.

Pour en savoir plus sur vos fichiers journaux de serveur Web, consultez la documentation de votre serveur Web.
