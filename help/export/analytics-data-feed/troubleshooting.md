---
title: Résolution des problèmes liés aux flux de données
description: Découvrez comment déterminer et résoudre les problèmes liés aux flux de données.
keywords: tâche;dépannage;erreur;ftp;chdir;connexion;connexion;mettre
exl-id: c082bc95-cdae-448b-86b5-695660fb2352
source-git-commit: b81ffba2f1e021888dd1c4b016c9b451448f47bb
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 29%

---

# Résolution des problèmes liés aux flux de données

Déterminer les raisons potentielles de l’échec du traitement ou de la diffusion d’une tâche.

## Dépannage d’un flux de données existant

Si un flux de données fonctionne correctement toutes les heures ou tous les jours, mais qu’il échoue récemment, vérifiez chacun des éléments suivants :

* Utilisez la variable [Outil Adobe Status](https://status.adobe.com/en/experience_cloud) pour déterminer s’il existe des fenêtres de maintenance planifiées ou des problèmes de disponibilité. En cas de problème connu à l’époque, Adobe traite automatiquement les flux de données planifiés une fois le service restauré.
* Assurez-vous que le site FTP dispose de suffisamment d’espace disponible. Si le site FTP manque d’espace disque, supprimez certains fichiers du serveur pour libérer de l’espace pour de nouveaux fichiers.
* S’il n’existe aucun problème connu et que le site FTP dispose de suffisamment d’espace disque, vous pouvez renvoyer le flux de données.

   1. Connectez-vous à Adobe Analytics et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Flux de données]**.
   2. Recherchez le ou les flux de données de votre choix, puis cochez la case en regard de chacun des flux que vous souhaitez réexécuter.
   3. Cliquez sur **[!UICONTROL Réexécuter]**.

   ![Réexécuter](assets/rerun.png)

Si vous ne recevez toujours pas les fichiers de flux de données après les avoir régénérés, contactez l’assistance clientèle.

## Dépannage d’un nouveau flux de données

Si un nouveau flux de données renvoie une erreur, résolvez le problème en chargeant manuellement un fichier de test sur le site FTP. Dans la plupart des cas, cette procédure vous permettra de déterminer la défaillance.

1. Connectez-vous à votre site FTP à l’aide de l’explorateur de fichiers (sur Windows) ou de Finder (sur Mac). Veillez à utiliser le protocole FTP (`ftp://`) et que vous autorisez [Adresses IP de l’Adobe](/help/technotes/ip-addresses.md) via le pare-feu de votre entreprise. Si vous ne parvenez pas à atteindre le site FTP, travaillez avec le propriétaire du site FTP pour déterminer la destination correcte.

   ![Explorateur de fichiers](assets/file_explorer.png)

2. Une fenêtre contextuelle vous demandant un nom d’utilisateur et un mot de passe s’affiche. Saisissez vos informations d’authentification. Si les identifiants sont acceptés, la fenêtre affiche les contenus actuels présents sur le site FTP. Si les informations d’identification ne sont pas acceptées, vérifiez auprès du propriétaire FTP que le nom d’utilisateur et le mot de passe sont corrects. Si vous utilisez le protocole SFTP, veillez à suivre chaque étape de la variable [Guide SFTP](../ftp-and-sftp/c-sftp/ftp-sftp.md). Notez que Adobe ne prend pas en charge tous les cas d’utilisation SFTP.
3. Chargez un fichier sur le site FTP en le faisant glisser sur la fenêtre authentifiée. Toute image ou tout document texte est approprié. Si vous recevez un message d’erreur lorsque vous tentez de placer un fichier sur le site FTP, travaillez avec le propriétaire FTP pour vérifier qu’il y a suffisamment d’espace disque et que le nom d’utilisateur possède les autorisations d’écriture sur le site FTP.
4. Lorsque vous avez confirmé que le fichier se trouve sur le site FTP, vous pouvez supprimer le fichier chargé à l’étape précédente.

Si toutes les étapes ci-dessus fonctionnent et que vous recevez toujours une erreur FTP, contactez l’assistance clientèle.
