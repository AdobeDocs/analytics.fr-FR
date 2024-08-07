---
title: Prise en main des sources de données
description: Chargez des exemples de données dans une suite de rapports de développement.
exl-id: d9f74f55-abbb-4ceb-b4db-8d3c32aacd4a
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 0%

---

# Prise en main des sources de données

Vous pouvez suivre ces étapes pour télécharger facilement des exemples de données dans une suite de rapports de développement afin de voir le workflow en action. Une fois que vous avez compris le processus, vous pouvez le développer et l’adapter spécifiquement à la mise en oeuvre de votre entreprise.

>[!IMPORTANT]
>
>Suivez ces étapes à l’aide d’une suite de rapports de développement ou de test. Les données transférées par le biais des sources de données sont **permanentes**. Cela a un impact sur les données des suites de rapports de production si elles y sont chargées.

1. Connectez-vous à Adobe Analytics via [https://experience.adobe.com](https://experience.adobe.com).
1. Accédez à **[!UICONTROL Admin]** > **[!UICONTROL All Admin]** > **[!UICONTROL Data sources]**.
1. Sélectionnez une suite de rapports de développement à l’aide de la liste déroulante en haut à droite.
1. Cliquez sur le bouton **[!UICONTROL Créer]** en haut à gauche.
1. Sous [!UICONTROL Sélectionner une catégorie], choisissez &quot;[!UICONTROL Générique]&quot;, puis sous [!UICONTROL Sélectionner un type], sélectionnez &quot;[!UICONTROL Source de données générique (données récapitulatives uniquement)]&quot;.
1. Cliquez sur **[!UICONTROL Activer]**. Une fenêtre contextuelle s’ouvre, affichant l’[!UICONTROL Assistant d’activation de Data Source].
   1. Étape 1 : attribuez un nom à la source de données, puis cochez la case de non-responsabilité.
   1. Étape 2 : cette étape était plus utile dans les versions précédentes d’Adobe Analytics. Cochez une case, puis entrez une valeur dans le champ de texte en regard de celle-ci.
   1. Étape 3 : sélectionnez la mesure à inclure dans votre fichier de modèle de source de données. Sélectionnez &quot;Événement 1&quot; dans la liste déroulante.
   1. Étape 4 : cette étape était plus utile dans les versions précédentes d’Adobe Analytics. Cochez une case, puis entrez une valeur dans le champ de texte en regard de celle-ci.
   1. Étape 5 : sélectionnez la dimension à inclure dans votre fichier de modèle de source de données. Sélectionnez &quot;eVar1&quot; dans la liste déroulante.
   1. Étape 6 : passez en revue le résumé, en indiquant les dimensions et les mesures incluses dans le fichier de modèle.
   1. Étape 7 : cliquez sur le bouton **[!UICONTROL Télécharger]** pour télécharger le fichier de modèle de sources de données. Notez également les informations d’identification de connexion au site FTP, car elles sont utilisées sous peu.
1. La source de données est maintenant créée. L’étape suivante consiste à lui donner les données à traiter. Ouvrez le fichier téléchargé dans l’éditeur de texte de votre choix.
1. Le fichier de modèle contient trois lignes, deux lignes de commentaire (commençant par &quot;`#`&quot;) et une ligne d’en-tête :

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 2)
   #    eVar1    event1
   Date    Evar 1    Event 1
   ```

1. Saisissez plusieurs lignes de données, en séparant chaque entrée par un onglet. N’utilisez pas d’espaces ni de virgules pour séparer les valeurs.
   * La première colonne correspond à la date au format suivant : `MM/DD/YYYY/HH/mm/SS`.
   * La seconde colonne correspond à la valeur de texte que vous souhaitez inclure en eVar1.
   * La troisième colonne correspond au montant que vous souhaitez augmenter pour l’événement 1.

   ```text
   # Generic Data Source (Summary Data Only) template file (user: 123456789 ds_id: 5)
   #    eVar1    event1
   Date    Evar 1    Event 1
   09/07/YYYY/11/23/00    Data source example value    3
   09/07/YYYY/15/59/00    Another data source value    18
   ```

1. Enregistrez le fichier. Si vous le souhaitez, vous pouvez lui attribuer un nom de fichier différent. Une fois le fichier enregistré, vous pouvez fermer l’éditeur de texte.
1. Dans l’Explorateur Windows, le Finder ou votre client FTP de votre choix, accédez à [ftp://ftp.omniture.com](ftp://ftp.omniture.com).
1. Lorsque vous y êtes invité pour vous connecter, utilisez le nom d’utilisateur et le mot de passe fournis à la dernière étape de l’assistant de création de source de données. Vous pouvez le référencer à nouveau en accédant à [!UICONTROL Sources de données] et en cliquant sur **[!UICONTROL Infos FTP]** en regard de la source de données que vous avez créée.
1. Une fois que vous êtes authentifié, faites glisser le fichier que vous avez modifié dans la fenêtre FTP authentifié.
1. Créez un fichier texte vide à n’importe quel emplacement en dehors de la fenêtre FTP. Donnez-lui le même nom de fichier que le fichier de sources de données que vous avez téléchargé sur le site FTP, à une exception près. Au lieu d’un type de fichier `.txt`, attribuez-lui un type de fichier `.fin`. Assurez-vous que les paramètres de votre système d’exploitation vous permettent d’afficher et de modifier les types de fichiers.
1. Faites glisser le fichier `.fin` vide vers le même emplacement FTP que le fichier de source de données. La présence du fichier `.fin` indique à l’Adobe que le fichier de source de données est entièrement chargé et prêt à être ingéré.
1. Au bout de plusieurs minutes, le fichier disparaît de l’emplacement FTP et est visible dans les rapports.
1. Actualisez la page Sources de données et vérifiez que le fichier a bien été ingéré.
1. Accédez à Analysis Workspace et créez un projet.
1. Faites glisser eVar1 comme dimension sur le canevas de l’espace de travail, et événement 1 comme mesure. Assurez-vous que la période Workspace inclut les dates que vous avez fournies dans la source de données.

   ![Exemple de rapport](assets/success-report.png)

## Étapes suivantes

[Format de fichier](file-format.md) : découvrez les détails de la création d’un fichier de sources de données adapté à votre entreprise.
