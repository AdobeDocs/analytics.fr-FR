---
title: Déploiement d’Adobe Analytics dans un environnement de développement
description: Découvrez comment utiliser les balises pour déployer Adobe Analytics dans votre environnement de développement.
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: ea6812c8e596773abb8a05bbdb37bc641967c9b8
workflow-type: ht
source-wordcount: '594'
ht-degree: 100%

---

# Déploiement d’une mise en œuvre d’Analytics dans un environnement de développement

Une fois que vous avez créé et configuré une propriété de balise, les bibliothèques sont prêtes à être déployées et le code est implémenté sur votre site.

>[!NOTE]
>Adobe Experience Platform Launch est désormais une suite de technologies destinées à la collecte de données dans Experience Platform. Plusieurs modifications terminologiques ont par conséquent été apportées à la documentation du produit. Reportez-vous au [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=fr) suivant pour consulter une référence consolidée des modifications terminologiques.

## Conditions préalables

[Créer et configurer une propriété de balise pour Adobe Analytics](create-analytics-property.md) : accédez à l’outil et créez un espace pour votre implémentation Analytics.

## Création d’adaptateurs et d’environnements

Les balises prennent en charge de nombreux workflows organisationnels pour le déploiement de code. Pour créer le minimum de composants nécessaires à une mise en œuvre Analytics, procédez comme suit. En tant qu’administrateur de balises, vous pouvez travailler au sein de votre organisation pour établir le workflow approprié au déploiement de solutions Adobe.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise que vous prévoyez d’implémenter sur votre site.
3. Cliquez sur l’onglet Adaptateurs, puis sur Ajouter un adaptateur.
4. Nommez-le « Akamai », puis sélectionnez Akamai dans la liste déroulante de types. Cliquez sur Enregistrer.
5. Accédez à l’onglet Environnements, puis cliquez sur Créer un environnement.
6. Sélectionnez Développement, donnez-lui le nom « Environnement de développement », puis sélectionnez l’adaptateur Akamai dans la liste déroulante. Cliquez sur Créer, puis sur Fermer.
7. Cliquez sur Ajouter un environnement, sélectionnez Évaluation, donnez-lui le nom « Environnement d’évaluation », puis sélectionnez l’adaptateur Akamai. Cliquez sur Créer, puis sur Fermer.
8. Cliquez à nouveau sur Ajouter un environnement, sélectionnez Production, donnez-lui le nom « Environnement de production », puis sélectionnez l’adaptateur Akamai. Cliquez sur Créer, puis sur Fermer.

## Création d’une bibliothèque de développement

Malgré toutes les modifications et configurations apportées jusqu’à présent, aucun code n’a été publié. La création d’une bibliothèque, grossièrement traduite en un ensemble de modifications, permet la publication de code à utiliser sur votre site.

1. Connectez-vous à l’[interface utilisateur de la collecte de données](https://experience.adobe.com/data-collection) à l’aide de vos identifiants Adobe ID.
2. Cliquez sur la propriété de balise que vous prévoyez d’implémenter sur votre site.
3. Cliquez sur l’onglet Publication, puis sur Ajouter une nouvelle bibliothèque.
4. Nommez la bibliothèque « Modifications initiales », puis sélectionnez votre environnement de développement.
5. Cliquez sur Ajouter toutes les ressources modifiées, ce qui permet de répertorier automatiquement Adobe Analytics, Identity Service et Core.
6. Cliquez sur Enregistrer.
7. Dans l’écran du processus de publication, cliquez sur la liste déroulante en regard de votre nouvelle bibliothèque, puis sur Créer pour le développement. Au bout de quelques secondes, le point jaune de la bibliothèque devient vert, ce qui indique que la compilation a réussi.
8. Accédez à l’onglet Environnements, puis cliquez sur votre environnement de développement.
9. Sous « Installer les balises », copiez les blocs de code et communiquez-les aux propriétaires du site web de votre organisation.

## Installation de balises dans l’environnement de développement de votre site web

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

- [Guide de démarrage rapide](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=fr) : découvrez le workflow de base d’implémentation des balises.
- [Présentation de la publication](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=fr) : en savoir plus sur la publication et les environnements.

## Étapes suivantes

[Validation de votre mise en œuvre d’Analytics et publication en production](validate-publish-prod.md) : commencer à tirer parti d’Adobe Analytics.
