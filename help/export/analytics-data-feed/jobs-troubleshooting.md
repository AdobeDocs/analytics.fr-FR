---
description: Si une erreur survient, elle est indiquée dans la colonne État de la tâche.
keywords: Data Feed;job;troubleshooting;error;ftp;chdir;connect;login;put
title: Résolution des problèmes liés aux tâches
uuid: 8fbb914e-03db-434e-b4d3-8594144ff2b7
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Résolution des problèmes liés aux tâches

Si vous rencontrez des problèmes lors de l’affichage d’un flux de données sur votre site FTP, utilisez cette page pour en comprendre les raisons.

## Codes d’erreur

Si une erreur survient, elle est indiquée dans la colonne État de la tâche.

### Erreur liée au chdir FTP

Le flux ne parvient pas à accéder au dossier spécifié ni à y écrire. Assurez-vous que le dossier de destination existe sur le site FTP et que les identifiants fournis possèdent les autorisations de lecture ou d’écriture correctes pour ce dossier.

### Erreur de connexion FTP

Le flux ne parvient pas à se connecter à la destination FTP. Assurez-vous que la destination FTP est correcte et valide.

### Erreur FTP

Une erreur générique qui empêche à terme le flux d’écrire le fichier sur le site FTP. Cette erreur peut provenir potentiellement du fait que le disque du serveur FTP est plein ou que le quota est dépassé. L’erreur peut également provenir d’une défaillance du serveur réseau ou de destination.

### Erreur de connexion FTP

Le flux ne parvient pas à se connecter avec les identifiants fournis. Vérifiez que le nom d’utilisateur et le mot de passe FTP sont corrects.

### Erreur de configuration FTP

Le flux ne peut pas écrire de fichiers sur le site FTP. Assurez-vous que la connexion FTP possède les autorisations correctes pour à la fois lire et écrire les données sur votre site FTP. Cette erreur peut également potentiellement provenir d’un disque plein ou d’un quota d’espace disque dépassé sur le serveur FTP.

## Procédure de dépannage

Connectez-vous à votre site FTP et chargez n’importe quel fichier dessus. Dans la plupart des cas, cette procédure vous permettra de déterminer la défaillance.

1. Connectez-vous à votre site FTP à l’aide de l’explorateur de fichiers (sur Windows) ou de Finder (sur Mac). Assurez-vous d’utiliser le protocole FTP (`ftp://`). Si vous ne parvenez pas à atteindre le site FTP, vous pouvez travailler avec le propriétaire du site FTP pour déterminer la destination correcte.

   ![Explorateur de fichiers](assets/file_explorer.png)

2. Une fenêtre contextuelle vous demandant un nom d’utilisateur et un mot de passe s’affiche. Saisissez vos informations d’authentification. Si les identifiants sont acceptés, la fenêtre affiche les contenus actuels présents sur le site FTP. Si les identifiants ne sont pas acceptés, vous pouvez travailler avec le propriétaire FTP pour assurer que le nom d’utilisateur et le mot de passe sont corrects.
3. Chargez un fichier sur le site FTP en le faisant glisser sur la fenêtre authentifiée. Toute image ou tout document texte est approprié. Si vous recevez un message d’erreur lorsque vous tentez de placer un fichier sur le site FTP, travaillez avec le propriétaire FTP pour vérifier qu’il y a suffisamment d’espace disque et que le nom d’utilisateur possède les autorisations d’écriture sur le site FTP.
4. Lorsque vous avez confirmé que le fichier se trouve sur le site FTP, vous pouvez supprimer le fichier chargé à l’étape précédente.
5. Si toutes les étapes ci-dessous fonctionnent, mais que vous recevez toujours une erreur FTP, demandez à un employé du service clientèle de contacter l’assistance clientèle.
