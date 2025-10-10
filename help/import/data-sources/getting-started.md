---
title: Prise en main des sources de données
description: Chargez les données d’exemple dans une suite de rapports de développement.
exl-id: d9f74f55-abbb-4ceb-b4db-8d3c32aacd4a
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---

# Prise en main des sources de données

Vous pouvez suivre les étapes suivantes pour charger facilement des données d’exemple dans une suite de rapports de développement afin de voir le workflow en action. Une fois que vous avez compris le processus, vous pouvez l’étendre et l’adapter spécifiquement à la mise en œuvre de votre entreprise.

>[!IMPORTANT]
>
>Suivez ces étapes à l’aide d’une suite de rapports de développement ou de test. Les données chargées par le biais des sources de données sont **permanentes**. Cela a un impact sur les données des suites de rapports de production si elles y sont chargées.

1. Connectez-vous à Adobe Analytics via [https://experience.adobe.com](https://experience.adobe.com).
1. Accédez à **[!UICONTROL Admin]** > **[!UICONTROL Tous les administrateurs]** > **[!UICONTROL Sources de données]**.
1. Sélectionnez une suite de rapports de développement dans la liste déroulante située en haut à droite.
1. Cliquez sur le bouton **[!UICONTROL Créer]** en haut à gauche.
1. Sous [!UICONTROL Sélectionner une catégorie], choisissez « [!UICONTROL Générique] », et sous [!UICONTROL Sélectionner un type], choisissez « [!UICONTROL Source de données générique (données récapitulatives uniquement)] ».
1. Cliquez sur **[!UICONTROL Activer]**. Une fenêtre contextuelle s’ouvre, affichant l’[!UICONTROL Assistant d’activation du Source de données].
   1. Étape 1 : donnez un nom à la source de données, puis cochez la case clause de non-responsabilité.
   1. Étape 2 : cette étape était plus utile dans les versions précédentes d’Adobe Analytics. Cochez une case, puis saisissez une valeur dans le champ de texte en regard.
   1. Étape 3 : choisissez la mesure à inclure dans votre fichier de modèle de source de données. Sélectionnez « Événement 1 » dans la liste déroulante.
   1. Étape 4 : cette étape était plus utile dans les versions précédentes d’Adobe Analytics. Cochez une case, puis saisissez une valeur dans le champ de texte en regard.
   1. Étape 5 : choisissez la dimension à inclure dans votre fichier de modèle de source de données. Sélectionnez « eVar1 » dans la liste déroulante.
   1. Étape 6 : consulter le résumé, affichant les dimensions et les mesures incluses dans le fichier de modèle.
   1. Étape 7 : cliquez sur le bouton **[!UICONTROL Télécharger]** pour télécharger le fichier de modèle de sources de données. Notez également les informations de connexion au site FTP, car elles sont utilisées sous peu.
1. La source de données est maintenant créée ; l’étape suivante consiste à lui donner des données à traiter. Ouvrez le fichier téléchargé dans l’éditeur de texte de votre choix.
1. Le fichier modèle contient trois lignes ; deux lignes de commentaire (commençant par « `#` ») et une ligne d’en-tête :

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #    eVar1    event1
   Date    Evar 1    Event 1
   ```

1. Saisissez dans plusieurs lignes de données, en séparant chaque entrée par un onglet. N’utilisez pas d’espaces ni de virgules pour séparer les valeurs.
   * La première colonne correspond à la date au format suivant : `MM/DD/YYYY/HH/mm/SS`.
   * La deuxième colonne correspond à la valeur de texte que vous souhaitez inclure dans eVar1.
   * La troisième colonne correspond au montant que vous souhaitez augmenter pour l’événement 1.

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #    eVar1    event1
   Date    Evar 1    Event 1
   09/07/YYYY/11/23/00    Data source example value    3
   09/07/YYYY/15/59/00    Another data source value    18
   ```

1. Enregistrez le fichier. Vous pouvez éventuellement lui donner un nom de fichier différent. Une fois le fichier enregistré, vous pouvez fermer l’éditeur de texte.
1. Dans l’Explorateur Windows, le Finder ou le client FTP de votre choix, accédez à [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. Lorsque vous êtes invité à fournir vos informations de connexion, utilisez le nom d’utilisateur et le mot de passe fournis à la dernière étape de l’assistant de création de source de données. Vous pouvez y faire à nouveau référence en accédant à [!UICONTROL Sources de données] et en cliquant sur **[!UICONTROL Infos FTP]** en regard de la source de données que vous avez créée.
1. Une fois authentifié, faites glisser le fichier que vous avez modifié dans la fenêtre du FTP authentifié.
1. Créez un fichier texte vide à n’importe quel emplacement en dehors de la fenêtre FTP. Donnez-lui le même nom de fichier que le fichier des sources de données que vous avez chargé sur le site FTP, à une exception près. Au lieu d’un type de fichier `.txt`, donnez-lui un type de fichier `.fin`. Assurez-vous que les paramètres de votre système d’exploitation vous permettent d’afficher et de modifier les types de fichiers.
1. Faites glisser le fichier `.fin` vide vers le même emplacement FTP que le fichier source de données. La présence du fichier `.fin` indique à Adobe que le fichier de source de données est entièrement chargé et prêt à être ingéré.
1. Au bout de quelques minutes, le fichier disparaît de l’emplacement FTP et est visible dans les rapports.
1. Actualisez la page Sources de données et vérifiez que le fichier a bien été ingéré.
1. Accédez à Analysis Workspace et créez un projet.
1. Faites glisser eVar1 en tant que dimension vers la zone de travail de l’espace de travail et l’événement 1 en tant que mesure. Assurez-vous que la période Workspace inclut les dates que vous avez fournies dans la source de données.

   ![&#x200B; Exemple de rapport &#x200B;](assets/success-report.png)

## Étapes suivantes

[Format de fichier](file-format.md) : découvrez les détails de la création d’un fichier de sources de données adapté à votre organisation.
