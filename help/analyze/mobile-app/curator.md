---
description: Instructions pour configurer les cartes de performance des applications mobiles.
title: Guide du conservateur d’application mobile Adobe Analytics
translation-type: tm+mt
source-git-commit: e01002d04560b6fe56a2ac2f4869d48f7604972d

---



# BETA : Guide du conservateur pour les applications mobiles Analytics


## Introduction

L’application mobile Adobe Analytics fournit des informations à tout moment et en tout lieu à partir d’Adobe Analytics.   L’application permet aux utilisateurs mobiles d’accéder à des cartes de performance intuitives, que vous créez et partagez à partir de l’interface utilisateur de bureau d’Adobe Analytics. Les tableaux de bord sont un ensemble de mesures clés et d’autres composants présentés dans une disposition en mosaïque que vous pouvez appuyer pour obtenir des ventilations plus détaillées et des rapports de tendances. Vous pouvez personnaliser les cartes de performance en fonction des données les plus importantes pour vous. L’application mobile est prise en charge sur les systèmes d’exploitation iOS et Android.

## À propos de ce guide

Ce guide a pour but d’aider les responsables de la configuration des données Adobe Analytics à configurer des cartes de performance pour leurs utilisateurs cadres dans l’application mobile Analytics. Les administrateurs peuvent être des administrateurs d’entreprise ou des personnes occupant d’autres rôles chargés de configurer des feuilles de calcul d’application, ce qui permet aux utilisateurs de visualiser rapidement et facilement un grand nombre de données de synthèse importantes sur leurs propres périphériques mobiles. Bien que les administrateurs soient les utilisateurs finaux de l’application mobile Analytics, ce guide aidera les gestionnaires de données à configurer l’application de manière efficace pour ces utilisateurs.


## Glossaire

Le tableau suivant décrit les termes permettant de comprendre l’audience, les fonctions et le fonctionnement de l’application mobile Analytics.

|Terme|Définition||—|—||Consommateur| Personnalité exécutive affichant les mesures clés et les informations d’Analytics sur un périphérique mobile||Curateur|Personnalité qui identifie et distribue les statistiques d’Analytics et configure les cartes de performance à afficher par le consommateur||Traitement|L'acte de créer ou de modifier une carte de performance mobile contenant les mesures, dimensions et autres composants appropriés pour le consommateur||Scorecard|Une vue d'application mobile contenant une ou plusieurs mosaïques||Mosaïque|Rendu d'une mesure dans une vue de carte de performance||Ventilation|Une vue secondaire accessible en appuyant sur une mosaïque dans la carte de performance. Cette vue s’étend sur la mesure affichée sur la mosaïque et génère éventuellement des rapports sur des dimensions de ventilation supplémentaires.||Période|Plage de dates principale pour les rapports sur les applications mobiles||Période de comparaison|Période comparée à la période principale|

 
## Création d’une carte de performance pour les utilisateurs cadres

Une carte de performance mobile affiche les visualisations de données clés pour les utilisateurs cadres dans une mise en page en mosaïque, comme illustré ci-dessous :


![Exemple de tableau de bord](/help/analyze/mobile-app/assets/intro_scorecard.png)


En tant que conservateur de cette carte de performance, vous pouvez utiliser le Créateur de cartes de performance pour configurer les mosaïques qui apparaissent sur la carte de performance pour votre consommateur. Vous pouvez également configurer la manière dont les vues détaillées, ou les ventilations, peuvent être ajustées une fois les mosaïques sur lesquelles vous appuyez. L’interface du créateur de cartes de performance est présentée ci-dessous :

![Générateur de cartes de performance](help/analyze/mobile-app/assets/scorecard_builder.png)


Pour créer la carte de performance, procédez comme suit :

1. Accédez au modèle de carte de performance mobile vierge.
2. Configurez la carte de performance avec des données et enregistrez-la.


### Accès au modèle de carte de performance mobile vierge

Vous pouvez accéder au modèle de carte de performance mobile vierge de l’une des manières suivantes :

**Créer un projet**

1. Ouvrez Adobe Analytics et cliquez sur l’onglet **Workspace** .
2. Cliquez sur le bouton **Créer un projet** et sélectionnez le modèle de projet **Carte de performance mobile** vierge.
3. Cliquez sur le bouton **Créer un**.

![Modèle Scorecard](help/analyze/mobile-app/assets/new_template.png)


*Remarque : Si vous ne voyez pas le modèle de carte de performance mobile vierge, comme illustré ci-dessous, votre entreprise n’a pas encore été activée pour la version bêta. Contactez votre responsable clientèle.*


**Ajout d’un projet**

Dans l’écran **Projets** , sous l’onglet **Composants** , cliquez sur le bouton **Ajouter** et sélectionnez Carte de performance **mobile.**

![Ajout de projets](help/analyze/mobile-app/assets/add_project.png)

**Utilisation des outils Analytics**

Dans Analytics, cliquez sur le menu **Outils** et sélectionnez Application **** mobile. Dans l’écran suivant, cliquez sur le bouton **Créer une carte de performance** .

### Configurez la carte de performance avec des données et enregistrez-la.

Pour mettre en oeuvre le modèle Scorecard :

1. Sous **Propriétés** (dans le rail droit), spécifiez une Report Suite **de** projet à partir de laquelle vous souhaitez utiliser les données.

   ![Sélection de suites de rapports](help/analyze/mobile-app/assets/properties_save.png)

2. Pour ajouter une nouvelle mosaïque à votre carte de performance, faites glisser une mesure depuis le panneau de gauche et déposez-la dans la zone **Faire glisser les mesures ici** . Vous pouvez également insérer une mesure entre deux mosaïques à l’aide d’un processus similaire.

   ![Ajout de mosaïques](help/analyze/mobile-app/assets/build_list.png)


   *Depuis chaque volet, vous pouvez accéder à une vue détaillée qui affiche des informations supplémentaires sur la mesure, telles que les principaux éléments d’une liste de dimensions connexes.*


3. Pour ajouter une dimension associée à une mesure, faites glisser une dimension depuis le panneau de gauche et déposez-la sur une mosaïque. Par exemple, vous pouvez ajouter des dimensions appropriées (comme la région **** DMA, dans cet exemple) à la mesure Visiteurs **** uniques en le faisant glisser sur la mosaïque ; les dimensions que vous ajoutez apparaissent sous la section de ventilation des **propriétés** spécifiques à la mosaïque. Vous pouvez ajouter plusieurs dimensions à chaque mosaïque.

   ![Ajout de dimensions](help/analyze/mobile-app/assets/layer_dimensions.png)

   *Remarque : Vous pouvez également ajouter une dimension à toutes les mosaïques en la faisant glisser sur le canevas Scorecard.*

   Lorsque vous cliquez sur une mosaïque dans le créateur de cartes de performance, le rail droit affiche les propriétés et les caractéristiques associées à cette mosaïque. Dans ce rail, vous pouvez fournir un nouveau **titre** pour la mosaïque et configurer la mosaïque en spécifiant les composants au lieu de les faire glisser depuis le rail gauche.


   En outre, si vous cliquez sur des mosaïques, une fenêtre contextuelle dynamique affiche l’affichage de la vue Ventilation pour l’utilisateur dans l’application. Si aucune dimension n’a été appliquée à la mosaïque, la dimension de ventilation sera **heure** ou **jours**, selon la plage de dates par défaut.

   ![Breakdown_view](help/analyze/mobile-app/assets/break_view.png)

   *Notez comment chaque dimension ajoutée à la mosaïque s’affiche dans une liste déroulante dans la vue détaillée de l’application. L’utilisateur exécutif peut alors choisir parmi les options répertoriées dans la liste déroulante.*

4. Pour appliquer des segments à des mosaïques individuelles, faites glisser un segment depuis le panneau de gauche et déposez-le directement au-dessus de la mosaïque. Si vous souhaitez appliquer le segment à toutes les mosaïques de la carte de performance, déposez la mosaïque au-dessus de la carte de performance.

5. De même, pour supprimer un composant appliqué à la totalité de la carte de performance, cliquez n’importe où sur la carte de performance en dehors des mosaïques, puis supprimez-le en cliquant sur la **croix** qui s’affiche lorsque vous passez la souris sur le composant, comme illustré ci-dessous pour le segment Clients **** mobiles :

   ![Remove_components](help/analyze/mobile-app/assets/new_remove.png)

6. Sous **Propriétés** du tableau de bord, vous pouvez également spécifier les éléments suivants :

   * Plage **de dates** par défaut. Les plages spécifiées ici seront les mêmes que celles appliquées au premier accès de l’utilisateur exécutif à la carte de performance dans son application.

   * Plage de dates **de comparaison**

   * Tout **segment** à appliquer à l’ensemble de la carte de performance

7. Pour nommer la carte de performance, cliquez sur l’espace de noms dans l’angle supérieur gauche de l’écran et saisissez le nouveau nom.

   ![Naming_scorecards](help/analyze/mobile-app/assets/new_name.png)

## Partage de la carte de performance

Pour partager la carte de performance avec un utilisateur exécutif :

1. Cliquez sur le menu **Partager** et sélectionnez **Partager la carte de performance**.

2. Dans le formulaire **Partager** , renseignez les champs en procédant comme suit :

   * Attribution du nom de la carte de performance
   * Description de la carte de performance
   * Ajout de balises appropriées
   * Spécification des destinataires de la carte de performance
   * Sélectionnez l’option **Partager les composants incorporés avec les destinataires** pour vous assurer que l’utilisateur exécutif a accès à tous les composants de la carte de performance.

3. Cliquez sur **Partager**.

![Share_Scorecards](help/analyze/mobile-app/assets/new_share.png)


Une fois que vous avez partagé une carte de performance, les destinataires peuvent y accéder sur leur application mobile Analytics. Si vous apportez des modifications ultérieures à la carte de performance dans le créateur de cartes de performance, elles seront automatiquement mises à jour dans la carte de performance partagée. Les utilisateurs de l’administration verront alors les modifications après avoir actualisé la carte de performance dans leur application.

*Remarque : Si vous mettez à jour la carte de performance en ajoutant de nouveaux composants, vous souhaiterez peut-être partager à nouveau la carte de performance (et cochez l’option Partager **automatiquement les composants incorporés avec les destinataires**) afin de vous assurer que vos cadres supérieurs ont accès à ces modifications.*

## Configuration des utilisateurs cadres avec l’application

Dans certains cas, les utilisateurs finaux peuvent avoir besoin d’une aide supplémentaire pour accéder à l’application et l’utiliser. Cette section fournit des informations pour vous aider à fournir cette aide.

### Aider les utilisateurs cadres à accéder à

Pour aider les cadres à accéder à vos cartes de performance dans l’application, assurez-vous que :

    * La configuration minimale requise pour les systèmes d’exploitation mobiles sur leurs appareils est iOS version 10 ou ultérieure, ou Android version 4.4 (KitKat) ou ultérieure
    * Ils disposent d’une connexion valide à Adobe Analytics
    * Vous avez correctement créé des cartes de performance mobiles pour eux et partagé ces cartes avec eux.
    * Ils ont accès à l’Espace de travail d’analyse et à la suite de rapports sur
    laquelle est basée la carte de performance*. Ils ont accès aux composants inclus dans la carte de performance. Remarque : Vous pouvez sélectionner une option lors du partage de vos cartes de performance vers **Partager automatiquement les composants incorporés avec les destinataires**.

### Aider les utilisateurs de l’application

Pendant la phase bêta, et avant que l’application ne soit dévoilée au public, vous pouvez contrôler qui a accès à l’application.

1. Aidez les utilisateurs à télécharger et installer l’application. Pour ce faire, suivez les étapes ci-après pour étendre l’accès à vos cadres, selon qu’ils utilisent un iOS ou un périphérique Android.

   **Pour les cadres supérieurs sur iOS :**

   1. Cliquez sur le lien public suivant (il est également disponible dans Analytics sous **Outils** &gt; Application **** mobile) :

      [Lien](https://testflight.apple.com/join/WtXMQxlI)iOS : `https://testflight.apple.com/join/WtXMQxlI`

      Après avoir cliqué sur le lien, l’écran Testflight suivant s’affiche :

      ![Ecran Testflight](help/analyze/mobile-app/assets/testflight1.png)

   2. Appuyez sur le lien **Afficher dans l’App Store** sur l’écran pour télécharger l’application Testflight.

   3. Après avoir installé l’application Testflight, recherchez et installez l’application mobile Adobe Analytics depuis Testflight, comme indiqué ci-dessous :
   ![Ecran Testflight](help/analyze/mobile-app/assets/testflight2.png)

   **Pour les cadres supérieurs sur Android :**

   1. Appuyez sur le lien Play Store suivant sur le périphérique de l’utilisateur (il est également disponible dans Analytics sous **Outils** &gt; Application **** mobile) :


      [Android](https://play.google.com/apps/testing/com.adobe.analyticsmobileapp): `https://play.google.com/apps/testing/com.adobe.analyticsmobileapp`

      Après avoir appuyé sur le lien, appuyez sur le lien Devenir un testeur dans l’écran suivant :

      ![Ecran Plate-forme](help/analyze/mobile-app/assets/play.png)

   2. Appuyez sur le lien **Télécharger sur Google Play** sur l’écran suivant :

      ![Lien de téléchargement](help/analyze/mobile-app/assets/playnext.png)

   3. Téléchargez et installez l’application.
   Une fois téléchargés et installés, les utilisateurs finaux peuvent se connecter à l’application à l’aide de leurs identifiants Adobe Analytics existants ; nous prenons en charge les ID Adobe et Enterprise/Federated.

   ![Ecran de bienvenue de l’application](help/analyze/mobile-app/assets/welcome.png)

2. Aidez-les à accéder à votre carte de performance. Une fois que les administrateurs se sont connectés à l’application, l’écran Choisir une société s’affiche. Cet écran répertorie les sociétés de connexion auxquelles appartient l’utilisateur exécutif. Pour les aider à accéder à Scorecard :

* Appuyez sur le nom de la société de connexion ou de l’organisation Experience Cloud qui s’applique à la carte de performance que vous avez partagée. La liste Scorecard affiche alors toutes les Scorecards qui ont été partagées avec le cadre exécutif sous cette société de connexion.
* Aidez-les à trier cette liste selon les dernières modifications, le cas échéant.
* Appuyez sur le nom de la carte de performance pour l’afficher.


1. Choisissez une société en appuyant dessus.
2. Appuyez sur une carte de performance dans la liste des cartes de performance.

   Remarque : Si l'utilisateur exécutif se connecte et voit un message disant que rien n'a été partagé :

   * L’utilisateur exécutif a peut-être sélectionné une instance Analytics incorrecte.
   * La carte de performance n’a pas été partagée avec l’utilisateur exécutif.

3. Montrez comment les mosaïques apparaissent dans la carte de performance que vous partagez.



   Informations supplémentaires sur les mosaïques :

       
 * La granularité des graphiques sparkline dépend de la longueur de la plage de dates :       * Un jour affiche une tendance
 horaire     * Plus d’une journée et moins d’une année affiche une tendance
 quotidienne* Un an ou plus montre une tendance     
     hebdomadaire* La formule de changement de valeur en pourcentage est le total de la mesure (période actuelle) - total de la mesure (période de comparaison) / total de la mesure (période de comparaison) (période de comparaison).
       * Vous pouvez descendre l’écran pour actualiser la carte de performance.
   

4. Appuyez sur une mosaïque pour afficher le fonctionnement d’un rapport de ventilation ou de tendance détaillé pour la mosaïque.


5. Pour modifier les plages de dates de votre carte de performance :



   *1. Appuyez sur l’en-tête Date. 2. Dans l’écran Plage de dates, appuyez sur la durée de travail.*

   Selon l’intervalle que vous touchez (Jour, Semaine, Mois ou Année), deux options s’affichent pour les plages de dates : soit la période actuelle, soit celle qui la précède immédiatement. Appuyez sur l’une de ces deux options pour sélectionner la première plage. Sous la liste COMPARER À, appuyez sur l’une des options présentées pour comparer les données de cette période avec la première période sélectionnée. Appuyez sur Terminé dans l’angle supérieur droit de l’écran. Le champ Plages de dates et les mosaïques Scorecard sont mis à jour avec les nouvelles données de comparaison des nouvelles plages sélectionnées.


6. Pour laisser vos commentaires sur cette application :


   1. Appuyez sur l’icône de l’utilisateur dans l’angle supérieur droit de l’écran de l’application.
   2. Dans l’écran Mon compte, appuyez sur l’option Commentaires.
   3. Appuyez sur pour afficher les options permettant de laisser un commentaire.



*Appuyez sur l’icône Utilisateur dans l’angle supérieur droit. 2. Appuyez sur le type de commentaire. 3. Appuyez sur l’option de commentaire applicable.*








Pour signaler un bogue :

Appuyez sur l’option et choisissez une sous-catégorie du bogue. Dans le formulaire pour signaler un bogue, indiquez votre adresse électronique dans le champ supérieur et votre description du bogue dans le champ situé en dessous. Une capture d’écran des informations de votre compte est automatiquement jointe au message, mais vous pouvez la supprimer si vous le souhaitez en appuyant sur le X dans l’image de la pièce jointe. Vous avez également la possibilité de prendre un enregistrement d’écran, d’ajouter d’autres captures d’écran ou de joindre des fichiers. Pour envoyer le rapport, appuyez sur l’icône du plan de papier dans l’angle supérieur droit du formulaire.














Pour suggérer une amélioration :

Appuyez sur l’option et choisissez une sous-catégorie pour la suggestion. Dans le formulaire de suggestion, indiquez votre adresse électronique dans le champ supérieur et votre description du bogue dans le champ situé en dessous. Une capture d’écran des informations de votre compte est automatiquement jointe au message, mais vous pouvez la supprimer si vous le souhaitez en appuyant sur le X dans l’image de la pièce jointe. Vous avez également la possibilité de prendre un enregistrement d’écran, d’ajouter d’autres captures d’écran ou de joindre des fichiers. Pour envoyer la suggestion, appuyez sur l’icône du plan de papier dans l’angle supérieur droit du formulaire.

Pour poser une question :

Appuyez sur l’option et indiquez votre adresse électronique dans le champ supérieur et votre question dans le champ situé en dessous. Une capture d’écran est automatiquement jointe au message, mais vous pouvez la supprimer si vous le souhaitez en appuyant sur le X dans l’image de la pièce jointe. Vous avez également la possibilité de prendre un enregistrement d’écran, d’ajouter d’autres captures d’écran ou de joindre des fichiers. Pour envoyer la question, appuyez sur l’icône du plan de papier dans l’angle supérieur droit du formulaire.
