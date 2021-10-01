---
description: Comment créer une Fiche d’évaluation des tableaux de bord Analytics
title: Création d’une Fiche d’évaluation
feature: Analytics Dashboards
role: User, Admin
source-git-commit: 5c9502536c96bc43288adfa259f1b60e6fd078c0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Configurer les utilisateurs en charge de l’exécution avec l’application

Dans certains cas, les utilisateurs en charge de l’exécution peuvent avoir besoin d’aide pour accéder à l’application et l’utiliser. Cette section fournit des informations pour vous aider à apporter cette aide.

## Vérifiez que les utilisateurs de l&#39;application ont accès à Adobe Analytics

1. Configurez de nouveaux utilisateurs dans le [Admin Console Experience Cloud](/help/admin/admin-console/permissions/product-profile.md).

1. Pour pouvoir partager des fiches d’évaluation, vous devez accorder aux utilisateurs de l’application les autorisations nécessaires pour accéder aux composants de la fiche d’évaluation, tels qu’Analysis Workspace, aux suites de rapports sur lesquelles les fiches d’évaluation sont basées, ainsi qu’aux segments, aux mesures et aux dimensions.

## Configuration requise pour les utilisateurs de l’application

Pour vous assurer que les utilisateurs en charge de l’exécution ont accès à vos fiches d’évaluation sur l’application, assurez-vous que :

* Les spécifications minimales en matière de systèmes d’exploitation mobile sur leurs appareils sont la version 10 ou ultérieure d’iOS ou la version 4.4 (KitKat) ou ultérieure d’Android.
* Ils possèdent des identifiants de connexion valides à Adobe Analytics..
* Vous avez correctement créé des Fiches d’évaluation mobiles pour eux et partagé ces Fiches d’évaluation avec eux.
* Ils ont accès aux composants que la fiche d’évaluation inclut. Notez que vous pouvez sélectionner une option lors du partage de vos fiches d’évaluation sur **[!UICONTROL Partager les composants incorporés]**.

## Aide les cadres à télécharger et à installer l’application

**Pour les utilisateurs en charge de l’exécution sur iOS :**

Cliquez sur le lien suivant (il est également disponible dans Analytics sous **[!UICONTROL Outils]** > **[!UICONTROL Tableaux de bord Analytics (application mobile)]**) et suivez les invites pour télécharger, installer et ouvrir l’application :

`[iOS link](https://apple.co/2zXq0aN)`

**Pour les utilisateurs en charge de l’exécution sur Android :**

Cliquez sur le lien suivant (il est également disponible dans Analytics sous **[!UICONTROL Outils]** > **[!UICONTROL Tableaux de bord Analytics (application mobile)]**) et suivez les invites pour télécharger, installer et ouvrir l’application :

`[Android link](https://bit.ly/2LM38Oo)`

Une fois l’application téléchargée et installée, les utilisateurs en charge de l’exécution peuvent se connecter à l’application en utilisant leurs informations d’identification Adobe Analytics existantes. Nous prenons en charge aussi bien les Adobe ID que les Enterprise/Federated ID.

![Écran de bienvenue de l’application](assets/welcome.png)

## Aide les cadres à accéder à votre fiche d’évaluation

1. Demandez aux utilisateurs en charge de l’exécution de se connecter à l’application.

   L’écran **[!UICONTROL Choisir une société]** s’affiche. Cet écran répertorie les entreprises connectées auxquelles l’utilisateur en charge de l’exécution appartient.

1. Demandez-leur d’appuyer sur le nom de la société de connexion ou de l’organisation Experience Cloud qui s’applique à la fiche d’évaluation que vous avez partagée.

   La liste de Fiche d’évaluation affiche ensuite toutes les Fiches d’évaluation qui ont été partagées avec l’exécutif sous cette société de connexion.

1. Demandez-leur de trier cette liste par **[!UICONTROL Modifié le plus récemment]**, le cas échéant.

1. Demandez-leur d’appuyer sur le nom de la Fiche d’évaluation pour l’afficher.

   ![Choisissez une entreprise](assets/accesscard.png)


### Explication de l’interface utilisateur de la Fiche d’évaluation

Expliquez à l’utilisateur en charge de l’exécution comment les mosaïques apparaissent dans les fiches d’évaluation que vous partagez.

![Explication des mosaïques](assets/newexplain.png)

![Exemple de Fiche d’évaluation](assets/intro_scorecard.png)

Informations supplémentaires sur les mosaïques :

* La granularité des graphiques sparkline dépend de la longueur de la période :
* Une tendance horaire s’affiche pour les plages d’une journée.
   * Une tendance quotidienne s’affiche pour les plages comprises entre une journée et un an.
   * Une tendance hebdomadaire s’affiche pour les plages supérieures à un an.
   * La formule de modification de la valeur de pourcentage est calculée de la manière suivante : total de la mesure (période en cours) - total de la mesure (période de comparaison)/total de la mesure (période de comparaison).
   * Vous pouvez tirer l’écran vers le bas pour actualiser la Fiche d’évaluation.


1. Appuyez sur une mosaïque pour afficher comment fonctionne une ventilation détaillée sur la mosaïque.

   ![Vue Ventilation](assets/sparkline.png)

   * Appuyez sur n’importe quel point d’un graphique sparkline pour afficher les données associées à ce point sur la ligne.

   * Un tableau est inclus pour afficher les données des dimensions ajoutées à la mosaïque. Appuyez sur la flèche vers le bas pour sélectionner les dimensions. Si aucune dimension n’a été ajoutée à la mosaïque, le tableau affiche les données de graphique.

1. Pour modifier les périodes de votre carte de performance, appuyez sur l’en-tête de date et sélectionnez la combinaison de période de comparaison et de période principale que vous voulez afficher.

   ![Modifier les dates](assets/changedate.png)

## Modification des préférences de l’application

Pour modifier les préférences, appuyez sur l’option **[!UICONTROL Préférences]** affichée ci-dessus. Dans les préférences, vous pouvez activer la connexion biométrique ou définir l’application pour le mode sombre comme illustré ci-dessous :

![Mode sombre](assets/darkmode.png)

## Résolution des problèmes

Si l’utilisateur en charge de l’exécution se connecte et qu’un message s’affiche indiquant que rien n’a été partagé :

![Rien n’a été partagé](assets/nothing.png)

* L’utilisateur en charge de l’exécution peut avoir sélectionné la mauvaise instance Analytics, ou
* La fiche d’évaluation n’a peut-être pas été partagée avec l’utilisateur en charge de l’exécution.

Vérifiez que l’utilisateur en charge de l’exécution peut se connecter à la bonne instance Adobe Analytics et que la fiche d’évaluation a été partagée.

### Signaler un bogue

Appuyez sur l’option, puis choisissez une sous-catégorie de bogue. Dans le formulaire de signalement d’un bogue, indiquez votre adresse électronique dans le champ supérieur et votre description du bogue dans le champ qui suit. Une capture d’écran des informations de votre compte est jointe automatiquement au message, mais vous pouvez la supprimer en appuyant sur le **X** dans l’image de la pièce jointe. Vous disposez également d’options pour effectuer un enregistrement de l’écran, ajouter davantage de captures d’écran ou joindre des fichiers. Pour envoyer le rapport, appuyez sur l’icône en forme d’avion en papier en haut à droite du formulaire.

![Signaler un bogue](assets/newbug.png)

### Laisser un commentaire

1. Appuyez sur l’icône des paramètres en haut à droite de l’écran de l’application.
1. Sur l’écran **[!UICONTROL Paramètres]**, appuyez sur l’option **[!UICONTROL Commentaires]**.
1. Appuyez pour afficher les options permettant de laisser un commentaire.

   ![Écran Paramètres](assets/settings.png)

### Suggérer une amélioration

Appuyez sur l’option et choisissez une sous-catégorie de suggestion. Dans le formulaire de suggestion, indiquez votre adresse électronique dans le champ supérieur et votre description de la suggestion dans le champ qui suit. Une capture d’écran des informations de votre compte est jointe automatiquement au message, mais vous pouvez la supprimer en appuyant sur le **X** dans l’image de la pièce jointe. Vous disposez également d’options pour effectuer un enregistrement de l’écran, ajouter davantage de captures d’écran ou joindre des fichiers. Pour envoyer la suggestion, appuyez sur l’icône en forme d’avion en papier en haut à droite du formulaire.

### Poser une question

Appuyez sur l’option et indiquez votre adresse électronique dans le champ supérieur et votre question dans le champ qui suit. Une capture d’écran est jointe automatiquement au message, mais vous pouvez la supprimer en appuyant sur le **X** dans l’image de la pièce jointe. Vous disposez également d’options pour effectuer un enregistrement de l’écran, ajouter davantage de captures d’écran ou joindre des fichiers. Pour envoyer la question, appuyez sur l’icône en forme d’avion en papier en haut à droite du formulaire.

>[!IMPORTANT]
>
>Depuis octobre 2020, Adobe déploie progressivement une série d’améliorations destinées à optimiser les performances de l’application « Tableaux de bord Adobe Analytics ». Ces améliorations portent principalement sur la mise en cache des données Analytics historiques utilisées pour remplir les fiches d’évaluation avec des dates (à l’exception du jour en cours). Ces données seront mises en cache pendant 24 heures maximum dans un compte de stockage cloud public Microsoft Azure sécurisé. Veuillez contacter votre CSM si vous souhaitez vous désabonner de ces fonctionnalités d’amélioration des performances.
