---
title: Déploiement d’Adobe Analytics dans un environnement de développement
description: Découvrez comment utiliser les balises pour déployer Adobe Analytics dans votre environnement de développement.
feature: Launch Implementation
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: f4b495b11bcbd55bc8448f2c9c09268547fb9750
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 47%

---

# Déploiement d’une mise en œuvre d’Analytics dans un environnement de développement

Une fois que vous avez créé et configuré une propriété de balise, les bibliothèques sont prêtes à être déployées et le code est implémenté sur votre site.

## Conditions préalables

[Créer et configurer une propriété de balise pour Adobe Analytics](create-analytics-property.md) : accédez à l’outil et créez un espace pour votre implémentation Analytics.

## Création d’adaptateurs et d’environnements

Les balises prennent en charge de nombreux workflows organisationnels pour le déploiement de code. Pour créer le minimum de composants nécessaires à une mise en œuvre Analytics, procédez comme suit. En tant qu’administrateur de balises, vous pouvez travailler au sein de votre organisation pour établir le workflow approprié au déploiement de solutions Adobe.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise que vous prévoyez d’implémenter sur votre site.
3. Cliquez sur **[!UICONTROL Hôtes]**, puis cliquez sur **[!UICONTROL Ajouter un hôte]**.
4. Nommez-le `"Adobe managed"`, puis sélectionnez **[!UICONTROL Géré par Adobe]** dans la liste déroulante de type . Cliquez sur Enregistrer.
5. Accédez à **[!UICONTROL Environnements]**, puis cliquez sur **[!UICONTROL Ajouter un environnement]**.
6. Sélectionner **[!UICONTROL Développement]**, nommez-le `"Dev Environment"`, puis sélectionnez l’hôte géré par l’Adobe dans la liste déroulante. Cliquez sur **[!UICONTROL Enregistrer]**.
7. Une fenêtre modale s’affiche, affichant les instructions d’installation Web. Nous retournerons à cette fenêtre ultérieurement ; click **[!UICONTROL Fermer]** pour le moment.
8. Cliquez sur **[!UICONTROL Ajouter un environnement]**, sélectionnez **[!UICONTROL Évaluation]**, nommez-le `"Staging Environment"`, puis sélectionnez l’hôte géré par l’Adobe. Cliquez sur **[!UICONTROL Créer]**, puis fermez la fenêtre modale des instructions d’installation.
9. Cliquez sur **[!UICONTROL Ajouter un environnement]** à nouveau, sélectionnez **[!UICONTROL Production]**, nommez-le `"Production Environment"`, puis sélectionnez l’hôte géré par l’Adobe. Cliquez sur **[!UICONTROL Créer]**, puis fermez la fenêtre modale des instructions d’installation.

## Création d’une bibliothèque de développement

Malgré toutes les modifications et configurations apportées jusqu’à présent, aucun code n’a été publié. La création d’une bibliothèque, grossièrement traduite en un ensemble de modifications, permet la publication de code à utiliser sur votre site.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise que vous prévoyez d’implémenter sur votre site.
3. Cliquez sur le bouton **[!UICONTROL Flux de publication]** , puis cliquez sur **[!UICONTROL Ajouter une bibliothèque]**. Voir [Présentation de la publication](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) dans la documentation Balises pour plus d’informations sur cette page.
4. Nommer la bibliothèque `'Initial changes'`, puis sélectionnez votre environnement de développement.
5. Cliquez sur **[!UICONTROL Ajouter toutes les ressources modifiées]**, qui répertorie automatiquement Adobe Analytics, Identity Service et Core.
6. Cliquez sur **[!UICONTROL Enregistrer]**.
7. De retour dans l’écran du processus de publication, cliquez sur la liste déroulante en regard de votre nouvelle bibliothèque, puis cliquez sur **[!UICONTROL Créer pour le développement]**. Au bout de quelques secondes, le point jaune de la bibliothèque devient vert, ce qui indique que la version a réussi.
8. Accédez à **[!UICONTROL Environnements]**, puis cliquez sur l’icône d’installation à droite de votre environnement de développement. Cette action affiche à nouveau la fenêtre modale Instructions d’installation web .
9. Copiez le ou les blocs de code et fournissez-les aux propriétaires du site web de votre entreprise.

## Installation de balises dans l’environnement de développement de votre site web

Si vous contrôlez le code de votre site web, implémentez chaque bloc de code à leur emplacement respectif :

* La balise principale se trouve dans la variable `<head>` balise sur votre site.
* Si vous choisissez de charger les balises de manière synchrone, vous devez également inclure un second bloc de code juste sous la balise de fermeture `</body>` balise sur votre site. Vous pouvez choisir de charger les balises de bibliothèque de manière synchrone en faisant basculer le **[!UICONTROL Chargement asynchrone de la bibliothèque]** dans les instructions d’installation Web.

Le code de balise est généralement placé dans le modèle global du site. Une page vierge contenant uniquement le code de mise en œuvre se présenterait comme suit :

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example page</title>
  <script src="//assets.adobedtm.com/launch-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx-development.min.js"></script>
</head>
<body>
   <p>This is a test page.</p>
   <!-- Only include this extra code if you load tags synchronously -->
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Résolution des problèmes

**La tentative de création échoue.**

Une raison fréquente est que des éléments existent déjà dans d’autres bibliothèques envoyées vers l’évaluation ou la production. Lors de la création initiale des bibliothèques, assurez-vous que seules les ressources modifiées sont ajoutées à la bibliothèque.

## Étapes suivantes

[Validation de votre mise en œuvre d’Analytics et publication en production](validate-publish-prod.md) : commencer à tirer parti d’Adobe Analytics.
