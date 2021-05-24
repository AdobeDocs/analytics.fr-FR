---
title: Validation de la mise en œuvre d’un développement et publication en production
description: Découvrez comment utiliser Adobe Experience Platform Launch pour déployer Adobe Analytics dans votre environnement de production.
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '645'
ht-degree: 100%

---

# Validation de la mise en œuvre d’un développement et publication en production

Une fois que votre bibliothèque Adobe Experience Platform Launch est envoyée en production, votre organisation peut commencer à utiliser Adobe Analytics pour extraire des rapports de base.

## Conditions préalables

[Déployez votre mise en œuvre d’Analytics dans votre environnement de développement](deploy-dev.md) : une mise en œuvre d’Analytics doit être publiée dans votre environnement de développement pour suivre cette page.

## Validez votre mise en œuvre de développement à l’aide du débogueur Experience Cloud.

Le débogueur Experience Cloud est un plug-in Chrome qui affiche toutes les balises Experience Cloud présentes sur une page.

1. Ouvrez [le navigateur web Chrome](https://www.google.com/intl/fr/chrome/) et accédez à [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) sur le Chrome Web Store pour installer l’extension.
2. Accédez à votre site web de développement sur lequel vous avez mis en œuvre Launch.
3. Cliquez sur l’icône d’Adobe Experience Cloud Debugger dans l’angle supérieur droit de Chrome.
4. Si tout est correctement mis en œuvre, le contenu doit s’afficher dans Adobe Analytics, dans Adobe Experience Platform Launch et dans le service d’identification des visiteurs d’Adobe Experience Cloud :

![débogueur][assets/debugger.png]

## Déployez votre mise en œuvre de développement vers l’évaluation/la production

Une fois que vous avez validé les données affichées, vous pouvez transmettre votre mise en œuvre à la version en direct de votre site.

1. Accédez à [Adobe Experience Platform Launch](https://launch.adobe.com) et connectez-vous si vous y êtes invité.
2. Cliquez sur la propriété Launch que vous prévoyez de mettre en œuvre sur votre site.
3. Cliquez sur l’onglet Publication et recherchez votre bibliothèque dans la colonne de développement.
4. Cliquez sur la liste déroulante de la bibliothèque, puis sélectionnez Envoyer pour approbation. Cliquez sur Envoyer dans la fenêtre modale.
5. Cliquez à nouveau sur la liste déroulante de la bibliothèque (à présent dans la colonne Envoyer), puis sélectionnez Créer pour l’évaluation.
6. Après quelques instants, la lumière jaune de la bibliothèque devient verte, ce qui indique une création réussie.
7. Cliquez à nouveau sur la liste déroulante de la bibliothèque, puis sélectionnez Approuver pour publication.
8. Cliquez à nouveau sur la liste déroulante de la bibliothèque (à présent dans la colonne Approuvé), puis sélectionnez Créer et Publier en production.
9. Accédez à l’onglet Environnements, puis cliquez sur Environnement de production.
10. Copiez le code d’en-tête de production + de pied de page et communiquez-le aux propriétaires de votre site web. Demandez-leur de mettre en œuvre ce code dans l’environnement de production de votre site.

## Validation de votre mise en œuvre de production

Confirmez que vous voyez des données sur la version en direct de votre site et commencez la collecte officielle des données pour Adobe Analytics.

1. Une fois que vous avez confirmé auprès des propriétaires de votre site web qu’ils ont envoyé le code de Launch en production, accédez à la page d’accueil de votre site web dans Chrome et ouvrez le débogueur Adobe Experience Cloud.
2. Si tout fonctionne correctement, vous devriez voir des données similaires à vos tests dans votre environnement de développement. À ce stade, vous collectez maintenant des données sur votre site et vous pouvez maintenant commencer à utiliser Adobe Analytics pour la création de rapports.

## Résolution des problèmes

**Aucune donnée n’apparaît dans le débogueur**.

Sur votre site, ouvrez la console de développement du navigateur (généralement F12). Examinez le code source de la page et assurez-vous que les conditions suivantes sont remplies :

* Il n’y a aucune erreur JavaScript dans la console. Consultez les propriétaires du site web de votre organisation pour vous assurer que toutes les erreurs JS sont résolues.
* Le code d’en-tête est correctement mis en œuvre : assurez-vous que le code d’en-tête se trouve à l’intérieur de la balise `<head>` et que le fichier existe.
* La bibliothèque AppMeasurement existe : accédez directement à la source JS pour vous assurer que le fichier JS contient du code. Dans le cas contraire, assurez-vous que chaque environnement est créé et que la bibliothèque est publiée dans son environnement respectif.
* Plug-ins d’interférence : certains plug-ins Chrome peuvent empêcher les demandes d’images de s’exécuter. Désactivez les plug-ins susceptibles d’empêcher l’envoi de données aux serveurs d’Adobe.

## Étapes suivantes

Maintenant qu’une implémentation de base est configurée, votre rôle au sein de votre organisation peut influencer le chemin sur lequel vous souhaitez davantage d’informations :

* [Création d’un document de conception de solution](../prepare/solution-design.md) : planifier l’utilisation des variables personnalisées, puis les intégrez à votre mise en œuvre
* [Prise en main de l’utilisation d’Analysis Workspace](/help/analyze/analysis-workspace/home.md) : passer directement à Adobe Analytics à l’aide de la fonctionnalité phare de l’outil.
