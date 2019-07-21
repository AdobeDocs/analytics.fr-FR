---
title: Déploiement d'Adobe Analytics dans un environnement de développement
seo-title: Déploiement d'Adobe Analytics dans un environnement de développement
description: Découvrez comment utiliser Adobe Experience Platform Launch pour déployer Adobe Analytics dans votre environnement de développement.
seo-description: Découvrez comment utiliser Adobe Experience Platform Launch pour déployer Adobe Analytics dans votre environnement de développement.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Validation d'une implémentation de développement et publication en production

Une fois la bibliothèque Adobe Experience Platform Launch placée en production, votre organisation peut commencer à utiliser Adobe Analytics pour extraire des rapports de base.

## Conditions préalables

[Déployez votre implémentation Analytics dans votre environnement de développement](deploy-dev.md): Une mise en œuvre Analytics doit être publiée dans votre environnement de développement pour suivre cette page.

## Validation de votre implémentation de développement à l'aide du débogueur Experience Cloud

Le débogueur Experience Cloud est un module externe Chrome qui affiche toutes les balises Experience Cloud présentes sur une page.

1. Open [Chrome Web Browser](https://www.google.com/chrome/) and go to [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) on the Chrome Web Store to install the extension.
2. Accédez à votre site Web de développement auquel vous avez implémenté le lancement.
3. Cliquez sur l'icône Débogueur Adobe Experience Cloud dans le coin supérieur droit de Chrome.
4. Si tout est correctement mis en œuvre, vous devriez voir le contenu dans Adobe Analytics, Adobe Experience Platform Launch et le service d'identification des visiteurs Adobe Experience Cloud :

![débogueur][assets/debugger.png]

## Déploiement de votre implémentation de développement sur évaluation/prod

Une fois que vous avez validé les données, vous pouvez pousser votre implémentation vers la version en ligne de votre site.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Cliquez sur la propriété Lancer que vous souhaitez implémenter sur votre site.
3. Cliquez sur l'onglet Publication et localisez votre bibliothèque dans la colonne de développement.
4. Cliquez sur la liste déroulante dans la bibliothèque, puis sélectionnez Envoyer pour approbation. Cliquez sur Envoyer dans la fenêtre modale.
5. Cliquez de nouveau sur la liste déroulante de la bibliothèque (dans la colonne Envoyée), puis sélectionnez Créer pour l'évaluation.
6. Après quelques instants, la lumière jaune de couleur sur la bibliothèque devient verte, indiquant une création réussie.
7. Cliquez de nouveau sur la liste déroulante de la bibliothèque, puis sélectionnez Approuver pour publication.
8. Cliquez de nouveau sur la liste déroulante de la bibliothèque (dans la colonne Approuvé) et sélectionnez Créer et publier en production.
9. Accédez à l'onglet Environnements, puis cliquez sur Environnement de production.
10. Copiez le code d'en-tête + code de pied de page et fournissez-le aux propriétaires de votre site Web. Demandez qu'ils implémentent ce code dans l'environnement de production de votre site.

## Validation de l'implémentation de production

Vérifiez que vous visualisez les données sur la version en ligne de votre site et commencez la collecte de données officielles pour Adobe Analytics.

1. Une fois que vous avez confirmé que les propriétaires de votre site Web ont transféré le code de lancement en production, accédez à la page d'accueil de votre site Web dans Chrome et ouvrez le débogueur Adobe Experience Cloud.
2. Si tout fonctionne, vous devriez voir des données similaires à vos tests dans votre environnement de développement. À ce stade, vous collectez maintenant des données sur votre site et pouvez maintenant commencer à utiliser Adobe Analytics pour la création de rapports.

## Résolution des problèmes

**Aucune donnée n'apparaît dans le débogueur.**

Sur votre site, ouvrez la console développeur du navigateur (généralement F 12). Examinez le code source de la page et vérifiez que les éléments suivants sont satisfaits :

* La console ne contient aucune erreur JavaScript. Travaillez avec les propriétaires de votre site Web pour vous assurer que toutes les erreurs JS sont résolues.
* Header code is properly implemented: Make sure the header code is inside the `<head>` tag, and that the file exists.
* La bibliothèque appmeasurement existe : Accédez directement à la source JS pour vous assurer que le fichier JS contient du code. Dans le cas contraire, assurez-vous que chaque environnement est créé et que la bibliothèque est publiée dans son environnement respectif.
* Interférences des modules externes : Certains modules externes Chrome peuvent empêcher le déclenchement des demandes d'image. Désactivez tous les modules externes susceptibles d'empêcher l'envoi des données aux serveurs d'Adobe.

## Étapes suivantes

Maintenant qu'une implémentation de base a été configurée, votre rôle au sein de votre organisation peut influencer le chemin d'accès à en savoir plus sur :

* [Création d'un document de conception de solution](../prepare/solution-design.md): déterminer comment utiliser les variables personnalisées, puis les inclure dans votre implémentation
* [Prise en main d'Analysis Workspace](../../analyze/analysis-workspace/home.md): Plongez dans Adobe Analytics à l'aide de la fonctionnalité phare de l'outil.
