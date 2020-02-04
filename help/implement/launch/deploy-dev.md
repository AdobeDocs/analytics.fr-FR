---
title: Déploiement d’Adobe Analytics dans un environnement de développement
description: Découvrez comment utiliser Adobe Experience Platform Launch pour déployer Adobe Analytics dans votre environnement de développement.
translation-type: tm+mt
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# Déploiement d’une mise en œuvre d’Analytics dans un environnement de développement

Une fois qu’une propriété a été créée et configurée dans Launch, les bibliothèques sont prêtes à être déployées et le code est prêt à être mis en œuvre sur votre site.

## Conditions préalables

[Créez et configurez une propriété pour Adobe Analytics dans Launch](create-analytics-property.md) : accédez à l’outil et créez un espace pour votre mise en œuvre Analytics.

## Création d’adaptateurs et d’environnements

Launch prend en charge de nombreux processus organisationnels pour le déploiement de code. Pour créer le minimum de composants nécessaires à une mise en œuvre Analytics, procédez comme suit. En tant qu’administrateur Launch, vous pouvez travailler au sein de votre organisation pour établir le processus approprié pour le déploiement de solutions Adobe.

1. Accédez à [Adobe Experience Platform Launch](https://launch.adobe.com) et connectez-vous si vous y êtes invité.
2. Cliquez sur la propriété Launch que vous prévoyez de mettre en œuvre sur votre site.
3. Cliquez sur l’onglet Adaptateurs, puis sur Ajouter un adaptateur.
4. Nommez-le « Akamai », puis sélectionnez Akamai dans la liste déroulante de types. Cliquez sur Enregistrer.
5. Accédez à l’onglet Environnements, puis cliquez sur Créer un environnement.
6. Sélectionnez Développement, donnez-lui le nom « Environnement de développement », puis sélectionnez l’adaptateur Akamai dans la liste déroulante. Cliquez sur Créer, puis sur Fermer.
7. Cliquez sur Ajouter un environnement, sélectionnez Évaluation, donnez-lui le nom « Environnement d’évaluation  », puis sélectionnez l’adaptateur Akamai. Cliquez sur Créer, puis sur Fermer.
8. Cliquez à nouveau sur Ajouter un environnement, sélectionnez Production, donnez-lui le nom « Environnement de production », puis sélectionnez l’adaptateur Akamai. Cliquez sur Créer, puis sur Fermer.

## Création d’une bibliothèque de développement

Malgré toutes les modifications et configurations apportées jusqu’à présent, aucun code n’a été publié. La création d’une bibliothèque, grossièrement traduite en un ensemble de modifications, permet la publication de code à utiliser sur votre site.

1. Accédez à [Adobe Experience Platform Launch](https://launch.adobe.com) et connectez-vous si vous y êtes invité.
2. Cliquez sur la propriété Launch que vous prévoyez de mettre en œuvre sur votre site.
3. Cliquez sur l’onglet Publication, puis sur Ajouter une nouvelle bibliothèque.
4. Nommez la bibliothèque « Modifications initiales », puis sélectionnez votre environnement de développement.
5. Cliquez sur Ajouter toutes les ressources modifiées, ce qui permet de répertorier automatiquement Adobe Analytics, Identity Service et Core.
6. Cliquez sur Enregistrer.
7. Dans l’écran du processus de publication, cliquez sur la liste déroulante en regard de votre nouvelle bibliothèque, puis sur Créer pour le développement. Au bout de quelques secondes, le point jaune de la bibliothèque devient vert, ce qui indique que la compilation a réussi.
8. Accédez à l’onglet Environnements, puis cliquez sur votre environnement de développement.
9. Sous « Installer Launch », copiez les blocs de code et communiquez-les aux propriétaires du site web de votre organisation.

## Installation de Launch dans l’environnement de développement de votre site web

Si vous contrôlez le code de votre site web, mettez en œuvre les deux blocs de code dans leurs emplacements respectifs (dans la balise `<head>` et juste au-dessus de la balise de fermeture `</body>`) sur chaque page de votre site. Ce code est généralement placé dans le modèle global du site. Une page vierge contenant uniquement le code de mise en œuvre se présenterait comme suit :

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
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Résolution des problèmes

**La tentative de création échoue.**

Une raison fréquente est que des éléments existent déjà dans d’autres bibliothèques envoyées vers l’évaluation ou la production. Lors de la création initiale des bibliothèques, assurez-vous que seules les ressources modifiées sont ajoutées à la bibliothèque.

## Documentation et ressources supplémentaires

- [Prise en main du lancement](https://docs.adobelaunch.com/getting-started): Découvrez le flux de travail de base du lancement
- [Lancer l’administration](https://docs.adobelaunch.com/administration): En savoir plus sur les adaptateurs et les environnements

## Étapes suivantes

[Validation de votre mise en œuvre d’Analytics et publication en production](validate-publish-prod.md) : commencer à tirer parti d’Adobe Analytics.
