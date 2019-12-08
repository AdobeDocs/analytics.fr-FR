---
description: Si une erreur survient, elle est indiquée dans la colonne État de la tâche.
keywords: Data Feed;job;troubleshooting;error;ftp;chdir;connect;login;put
title: Résolution des problèmes liés aux tâches
uuid: 8fbb914e-03db-434e-b4d3-8594144ff2b7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Résolution des problèmes liés aux tâches

Si vous rencontrez des problèmes lors de l’affichage d’un flux de données sur votre site FTP, utilisez cette page pour comprendre pourquoi.

## Codes d’erreur

Si une erreur survient, elle est indiquée dans la colonne État de la tâche.

### Erreur de chdir FTP

Le flux ne peut pas accéder au dossier spécifié ni y écrire. Assurez-vous que le dossier de destination existe sur le site FTP et que les informations d’identification fournies disposent des autorisations de lecture/écriture appropriées sur ce dossier.

### Erreur de connexion FTP

Le flux ne peut pas se connecter à la destination FTP. Assurez-vous que la destination FTP est correcte et valide.

### Erreur FTP

Erreur générique dans laquelle le flux ne peut pas écrire le fichier sur le site FTP. Cette erreur peut provenir du fait que le disque du serveur FTP est saturé ou que le quota est dépassé. L'erreur peut également provenir d'une défaillance du réseau ou du serveur de destination.

### Erreur de connexion FTP

Le flux ne peut pas se connecter à l’aide des informations d’identification fournies. Assurez-vous que le nom d’utilisateur et le mot de passe FTP sont corrects.

### Erreur de configuration FTP

Le flux ne peut pas écrire de fichiers sur le site FTP. Assurez-vous que la connexion FTP dispose des autorisations appropriées pour lire et écrire des données sur votre site FTP. Cette erreur peut également provenir d’un disque complet ou d’un quota de disque dépassé sur le serveur FTP.

## Procédure de dépannage

Connectez-vous à votre site FTP et téléchargez n’importe quel fichier vers celui-ci. Dans la plupart des cas, vous pouvez déterminer le point d’échec à l’aide de ces étapes.

1. Connectez-vous à votre site FTP à l’aide de l’Explorateur de fichiers (Windows) ou du Finder (Mac). Veillez à utiliser le protocole FTP (`ftp://`). Si vous ne parvenez pas à accéder au site FTP, vous pouvez demander au propriétaire du site FTP de déterminer la destination appropriée.

   ![Explorateur de fichiers](assets/file_explorer.png)

2. Une fenêtre contextuelle demandant un nom d’utilisateur et un mot de passe s’affiche. Entrez vos informations d’identification d’authentification. Si les informations d’identification sont acceptées, la fenêtre affiche le contenu actuel sur le site FTP. Si les informations d’identification ne sont pas acceptées, vous pouvez travailler avec le propriétaire FTP pour vous assurer que le nom d’utilisateur et le mot de passe sont corrects.
3. Téléchargez un fichier sur le site FTP en le faisant glisser dans la fenêtre authentifiée. Toute image ou document texte est approprié. Si vous obtenez une erreur en tentant de placer un fichier sur le site FTP, demandez au propriétaire FTP de vérifier qu’il y a suffisamment d’espace disque et que le nom d’utilisateur dispose d’autorisations d’écriture sur le site FTP.
4. Une fois que vous avez confirmé que le fichier se trouve sur le site FTP, vous pouvez supprimer le fichier téléchargé à l’étape précédente.
5. Si toutes les étapes ci-dessus fonctionnent et que vous obtenez toujours une erreur FTP, demandez à un délégué du service à la clientèle de contacter le service d’assistance clientèle.
