---
title: Déploiement d'Adobe Analytics dans un environnement de développement
seo-title: Déploiement d'Adobe Analytics dans un environnement de développement
description: Découvrez comment utiliser Adobe Experience Platform Launch pour déployer Adobe Analytics dans votre environnement de développement.
seo-description: Découvrez comment utiliser Adobe Experience Platform Launch pour déployer Adobe Analytics dans votre environnement de développement.
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Déploiement d'une implémentation Analytics dans un environnement de développement

Une fois qu'une propriété a été créée et configurée au lancement, les bibliothèques sont prêtes à être déployées et le code implémenté sur votre site.

## Conditions préalables

[Créez et configurez une propriété pour Adobe Analytics au lancement](create-analytics-property.md): Accédez à l'outil et créez un espace pour votre implémentation Analytics.

## Création de adaptateurs et d'environnements

Launch prend en charge de nombreux processus d'organisation du déploiement du code. Procédez comme suit pour créer les composants minimum nécessaires pour une mise en œuvre Analytics. En tant qu'administrateur de lancement, vous pouvez travailler dans votre organisation pour établir le flux de travaux approprié pour déployer les solutions Adobe.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Cliquez sur la propriété Lancer que vous souhaitez implémenter sur votre site.
3. Cliquez sur l'onglet Adapters, puis sur Ajouter un adaptateur.
4. Nommez-le Akamai, puis sélectionnez Akamai dans la liste déroulante Type. Cliquez sur Enregistrer.
5. Accédez à l'onglet Environnements, puis cliquez sur Créer un environnement.
6. Sélectionnez Développement, nommez-le, puis l'adaptateur Akamai dans la liste déroulante. Cliquez sur Créer, puis sur Fermer.
7. Cliquez sur Ajouter un environnement, sélectionnez Évaluation, nommez-le, puis sélectionnez l'adaptateur Akamai. Cliquez sur Créer, puis sur Fermer.
8. Cliquez de nouveau sur Ajouter un environnement, sélectionnez Production, nommez-le, puis l'adaptateur Akamai. Cliquez sur Créer, puis sur Fermer.

## Création d'une bibliothèque de développement

Malgré tous les changements et les configurations effectués jusqu'à présent, aucun code n'a été publié. La création d'une bibliothèque, traduite approximativement sous la forme d'un ensemble de modifications, permet d'utiliser la publication de code sur votre site.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Cliquez sur la propriété Lancer que vous souhaitez implémenter sur votre site.
3. Cliquez sur l'onglet Publication, puis sur Ajouter une nouvelle bibliothèque.
4. Nommez la bibliothèque « Modifications initiales » et sélectionnez votre environnement de développement.
5. Cliquez sur Ajouter toutes les ressources modifiées, qui répertorie automatiquement Adobe Analytics, le service d'identité et le noyau.
6. Cliquez sur Enregistrer.
7. Dans l'écran de processus de publication, cliquez sur la liste déroulante en regard de la nouvelle bibliothèque, puis cliquez sur Créer pour le développement. Après quelques secondes, le point jaune de la bibliothèque devient vert, indiquant que la création a réussi.
8. Accédez à l'onglet Environnements, puis cliquez sur votre environnement de développement.
9. Sous Installer le lancement, copiez les blocs de codes et fournissez-les aux propriétaires de votre site Web.

## Installation du lancement sur l'environnement de développement de votre site Web

If you control your website's code, implement the two blocks of code in their respective locations (in the `<head>` tag and just above the closing `</body>` tag) on every page of your site. Ce code est généralement placé dans le modèle principal du site. Une page vierge contenant uniquement le code de mise en œuvre ressemblerait à ce qui suit :

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

**La création d'une tentative échoue.**

Une raison courante est que des éléments existent déjà dans d'autres bibliothèques transférées vers un environnement d'évaluation ou de production. Lors de la création initiale de bibliothèques, assurez-vous que seules les ressources modifiées sont ajoutées à la bibliothèque.

## Documentation et ressources supplémentaires

- [Démarrage avec Launch](https://docs.adobelaunch.com/getting-started): Découvrez le flux de travaux de base du lancement
- [Lancer Administration](https://docs.adobelaunch.com/administration): En savoir plus sur les adaptateurs et les environnements

## Étapes suivantes

[Validez votre mise en œuvre Analytics et votre publication en production](validate-publish-prod.md): Commencez à obtenir la valeur d'Adobe Analytics.
