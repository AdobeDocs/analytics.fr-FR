---
title: Fichier journal
description: Procurez-vous un fichier journal à des fins de dépannage.
translation-type: tm+mt
source-git-commit: 5d96a2868bee48e2294ec2fb27e0340a3bcc50ae
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 5%

---


# Fichier journal

>[!IMPORTANT]
>
>L&#39;Adobe a mis Ad Hoc Analysis à la fin de sa vie le 1er mars 2021. [En savoir plus](https://adobe.ly/discoverworkspace)

Lors de la résolution des problèmes avec Ad Hoc Analysis, il est parfois nécessaire d’obtenir son fichier journal. L’Adobe peut utiliser le fichier journal pour localiser la cause du problème et fournir une résolution. Le `discover.log` fichier contient toutes les interactions utilisateur, les informations de chargement des rapports et les messages d’erreur Java pour toutes les sessions. Elle bloque toute information protégée, telle que le mot de passe de l’utilisateur. Les fichiers journaux volumineux sont divisés en incréments de 10 Mo. Lorsque vous fournissez un Adobe avec les fichiers journaux, assurez-vous que tous les fichiers sont sélectionnés.

## Windows

Procurez-vous le `discover.log` fichier pour Windows :

1. Cliquez sur le menu début et sélectionnez **Exécuter** ou appuyez sur `[Win]` + `[R]`.
2. Collez les éléments suivants dans le champ de texte, puis cliquez sur **OK**:

   ```text
   %appdata%/../Local/Adobe/Discover/log
   ```

3. Mettez en surbrillance tous les fichiers du dossier, puis cliquez avec le bouton droit de la souris et choisissez **Envoyer vers > Dossier** compressé.
4. Fournissez au représentant de l’Adobe le fichier .zip.

## Mac

Pour obtenir le `discover.log` fichier pour Mac OS, procédez comme suit :

1. Ouvrez le Finder et accédez à `/Users/your-user/.adobe/Discover/log`
2. Mettez en surbrillance tous les fichiers du dossier, puis cliquez avec le bouton droit de la souris et choisissez **Compresser**.
3. Fournissez au représentant de l’Adobe le fichier .zip.

Si la taille totale d’un fichier compressé dépasse 10 Mo, un représentant d’Adobe peut fournir un emplacement FTP temporaire.
